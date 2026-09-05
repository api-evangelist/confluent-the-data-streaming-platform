---
name: confluent-run-flink-sql
description: >-
  Submit an Apache Flink SQL statement to a Confluent Cloud compute pool, read its
  results, diagnose exceptions, and stop it. Use for stateful stream processing and for
  materializing transformed topics.
api: openapi/confluent-the-data-streaming-platform-cloud-apis-openapi.yml
base_url: https://api.confluent.cloud
operations:
  - listFcpmV2ComputePools
  - createSqlv1Statement
  - getSqlv1Statement
  - getSqlv1StatementResult
  - getSqlv1StatementExceptions
  - patchSqlv1Statement
  - deleteSqlv1Statement
---

# Run a Flink SQL statement

Paths in this group carry both scopes:
`/sql/v1/organizations/{organization_id}/environments/{environment_id}/statements`.

## Steps

1. `listFcpmV2ComputePools` — `GET /fcpm/v2/compute-pools`. A statement runs in a pool;
   pick one in the right environment and region.
2. `createSqlv1Statement` — `POST …/statements` with `name`, `spec.statement` (the SQL),
   `spec.compute_pool_id` and `spec.properties` (catalog/database defaults).
   A long-running statement bills continuously until it is deleted.
3. `getSqlv1Statement` — poll `status.phase`. `PENDING` → `RUNNING`, or `FAILED`.
4. `getSqlv1StatementResult` — page through results. Statements over an unbounded
   stream never "complete"; treat the result set as a cursor, not a final answer.
5. `getSqlv1StatementExceptions` — when the phase is `FAILED`, this is where the reason
   lives. Do not guess from the phase alone.
6. `deleteSqlv1Statement` — stops processing and stops the bill.

## Reversal

Deleting a statement stops FUTURE processing. It does not undo rows already written to a
sink table or topic. If the statement writes to a Tableflow/Iceberg target, the emitted
rows persist. There is no stated undo window — plan compensating SQL, not a rollback.

## Errors and limits

- `422` is a validation failure with the offending field in `errors[].source.pointer`.
- `429` on this group carries the rate-limit headers; the Kafka REST v3 group does not.
