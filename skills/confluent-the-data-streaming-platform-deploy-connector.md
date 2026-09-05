---
name: confluent-deploy-connector
description: >-
  Validate, deploy, monitor and safely roll back a fully managed Kafka Connect connector
  in Confluent Cloud. Use when wiring an external system into Kafka without writing a
  producer or consumer.
api: openapi/confluent-the-data-streaming-platform-cloud-apis-openapi.yml
base_url: https://api.confluent.cloud
operations:
  - listConnectv1ConnectorPlugins
  - validateConnectv1ConnectorPlugin
  - createConnectv1Connector
  - readConnectv1ConnectorStatus
  - getConnectv1ConnectorConfig
  - createOrUpdateConnectv1ConnectorConfig
  - pauseConnectv1Connector
  - resumeConnectv1Connector
  - restartConnectv1Connector
  - deleteConnectv1Connector
---

# Deploy a managed connector

Every path in this group is scoped by `{environment_id}` and `{kafka_cluster_id}`:
`/connect/v1/environments/{environment_id}/clusters/{kafka_cluster_id}/…`.

## Steps

1. `listConnectv1ConnectorPlugins` — discover the available plugin classes for the
   cluster. Do not hard-code a connector class name.
2. `validateConnectv1ConnectorPlugin` — `PUT …/connector-plugins/{plugin_name}/config/validate`.
   **Always validate before creating.** This is the dry-run this API offers, and it is
   the only one; the create call has no `?dry_run`.
3. `createConnectv1Connector` — `POST …/connectors` with `name` and `config`.
4. `readConnectv1ConnectorStatus` — poll until the connector and its tasks report
   `RUNNING`. `listConnectv1ConnectorTasks` gives per-task detail when one fails.
5. On failure, `restartConnectv1Connector`.

## Changing configuration safely

`createOrUpdateConnectv1ConnectorConfig` (`PUT …/config`) is a full replace.
**Read the current config with `getConnectv1ConnectorConfig` and keep it before you
write**, because Confluent stores no prior-version history you can restore from — the
saved copy IS your rollback.

## Reversal

- `pauseConnectv1Connector` ↔ `resumeConnectv1Connector` is a true round trip with no
  stated time limit.
- `deleteConnectv1Connector` is terminal.
- Records the connector already delivered downstream are not recalled by any of these.

## Notes for agents

Confluent's own MCP server exposes `get-connector-error-summary` and
`get-connector-fix-recommendations`, which have **no** REST equivalent — if you are
speaking MCP, prefer them for diagnosis; if you are speaking REST, you must reason from
`readConnectv1ConnectorStatus` yourself. See
`mcp/confluent-the-data-streaming-platform-tool-crosswalk.yml` → `mcp_only`.
