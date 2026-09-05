---
name: confluent-provision-kafka-cluster
description: >-
  Provision a Confluent Cloud environment and Kafka cluster, then mint a scoped API key
  for it, using the Confluent Cloud REST API. Use when an agent must stand up streaming
  infrastructure rather than call an existing cluster.
api: openapi/confluent-the-data-streaming-platform-cloud-apis-openapi.yml
base_url: https://api.confluent.cloud
operations:
  - listOrgV2Environments
  - createOrgV2Environment
  - createCmkV2Cluster
  - getCmkV2Cluster
  - createIamV2ApiKey
  - deleteCmkV2Cluster
---

# Provision a Confluent Cloud Kafka cluster

## Authenticate

HTTP Basic with a **Cloud API key**: the key ID is the username, the secret is the
password. Cloud API keys reach the management plane; a resource-specific key will not
work for `cmk/v2` or `org/v2`. OAuth 2.0 client credentials against
`https://api.confluent.cloud/sts/v1/oauth2/token` is the alternative.

## Steps

1. `listOrgV2Environments` — `GET /org/v2/environments`. Reuse an existing `env-*`
   before creating one. Paginate with `page_size` + `page_token`; the next link is in
   `metadata.next` and both must be treated as opaque.
2. `createOrgV2Environment` — `POST /org/v2/environments` only if none fits. Supply
   `display_name`.
3. `createCmkV2Cluster` — `POST /cmk/v2/clusters` with `spec.display_name`,
   `spec.availability`, `spec.cloud`, `spec.region`, `spec.config` (the cluster type —
   Basic, Standard, Enterprise, Freight) and `spec.environment.id`.
   **This is a billable, non-idempotent write.** There is no Idempotency-Key on this
   API; calling it twice creates two clusters. Confirm with a human first.
4. Poll `getCmkV2Cluster` — `GET /cmk/v2/clusters/{id}` until `status.phase` is
   `PROVISIONING` → `RUNNING`. The create response is 202-shaped intent, not final
   state. Do not treat a 2xx from step 3 as "the cluster is ready".
5. `createIamV2ApiKey` — `POST /iam/v2/api-keys` with `spec.owner` (a service account
   `sa-*`) and `spec.resource` pointing at the new `lkc-*`. **The secret is returned
   once and never again.** Store it before the response is discarded.

## Reversal

`deleteCmkV2Cluster` destroys the cluster and its data. There is no restore operation
in the contract. Treat it as terminal and require explicit human confirmation — see
`conventions/…-conventions.yml` → `reversibility.irreversible`.

## Errors and limits

- Envelope is `{"errors":[{"id","status","code","title","detail","source"}]}` — not
  RFC 9457. Quote `X-Request-Id` (or `errors[].id`) in any support escalation.
- `402` means over quota; Confluent documents a known issue where some quota errors
  still arrive as `400`.
- `429` carries `X-RateLimit-Reset` in **relative seconds**, not epoch. Sleep that many
  seconds; do not convert it to a date.
