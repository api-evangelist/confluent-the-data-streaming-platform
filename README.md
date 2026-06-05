# Confluent | the Data Streaming Platform (confluent-the-data-streaming-platform)

Confluent is a fully managed data streaming platform built by the original creators of Apache Kafka. It lets organizations stream, connect, process, and govern data in motion through a cloud-native service (Confluent Cloud) and the on-prem/self-managed Confluent Platform. Confluent's developer surface includes the Confluent Cloud REST API for managing clusters, environments, and access; the Kafka REST Proxy for producing and consuming events over HTTP; the Schema Registry REST API for governance of Avro, JSON Schema, and Protobuf schemas; the Kafka Connect REST API for managing connectors; the ksqlDB REST API for stream processing; and managed Apache Flink. Authentication is API-key based (Cloud) or HTTP/mTLS/OAuth (Platform).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/confluent-the-data-streaming-platform/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/confluent-the-data-streaming-platform/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Apache Flink
- Apache Kafka
- Confluent Cloud
- Connectors
- Data Streaming
- Event Streaming
- Kafka Connect
- ksqlDB
- Real-Time Data
- REST
- Schema Registry
- Stream Processing

## Timestamps

- **Created:** 2025-08-19
- **Modified:** 2026-04-28

## APIs

### Confluent Cloud REST API

The Confluent Cloud REST API is the management plane for Confluent Cloud. It is used to manage organizations, environments, Kafka and Flink clusters, service accounts, API keys, role bindings, networking, schema registry clusters, and connector instances. The API uses Cloud API keys for authentication and follows Confluent's resource-oriented v2 conventions.

- **Human URL:** [https://docs.confluent.io/cloud/current/api.html](https://docs.confluent.io/cloud/current/api.html)
- **Base URL:** `https://api.confluent.cloud`

#### Tags

- Confluent Cloud
- Management
- REST

#### Properties

- [Documentation](https://docs.confluent.io/cloud/current/api.html)
- [API Reference](https://docs.confluent.io/cloud/current/api.html)
- [Postman Collection](collections/confluent-the-data-streaming-platform.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/confluent-the-data-streaming-platform.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Confluent Kafka REST API

The Kafka REST API (Confluent REST Proxy in self-managed deployments, Kafka REST in Cloud) provides HTTP access to Apache Kafka topics, consumers, partitions, brokers, and ACLs. Clients without a native Kafka library can produce and consume records, manage topics, and inspect metadata over HTTP. Cloud variants additionally enforce RBAC and Confluent Cloud authentication.

- **Human URL:** [https://docs.confluent.io/platform/current/kafka-rest/api.html](https://docs.confluent.io/platform/current/kafka-rest/api.html)
- **Base URL:** `https://pkc-XXXXX.region.aws.confluent.cloud`

#### Tags

- Apache Kafka
- Producer
- Consumer
- REST

#### Properties

- [Documentation](https://docs.confluent.io/platform/current/kafka-rest/api.html)
- [Cloud  Documentation](https://docs.confluent.io/cloud/current/kafka-rest/index.html)
- [Postman Collection](collections/confluent-the-data-streaming-platform.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/confluent-the-data-streaming-platform.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Confluent Schema Registry REST API

The Schema Registry REST API stores and serves Avro, JSON Schema, and Protobuf schemas with versioning and compatibility enforcement. It is available both as a managed Confluent Cloud service and as a self-managed component of Confluent Platform. The full developer profile lives in the api-evangelist/confluent-schema-registry repository.

- **Human URL:** [https://docs.confluent.io/platform/current/schema-registry/develop/api.html](https://docs.confluent.io/platform/current/schema-registry/develop/api.html)
- **Base URL:** `https://psrc-XXXXX.region.aws.confluent.cloud`

#### Tags

- Avro
- JSON Schema
- Protobuf
- Schema Registry

#### Properties

- [Documentation](https://docs.confluent.io/platform/current/schema-registry/develop/api.html)
- [Companion  Repo](https://github.com/api-evangelist/confluent-schema-registry)
- [Postman Collection](collections/confluent-the-data-streaming-platform.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/confluent-the-data-streaming-platform.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Kafka Connect REST API

The Kafka Connect REST API manages connectors, tasks, and worker configuration. Operators use it to deploy, configure, pause, resume, and delete source and sink connectors, inspect task status, and restart failed tasks. In Confluent Cloud, managed connectors are provisioned through the Cloud REST API while runtime status is exposed via the Connect REST surface.

- **Human URL:** [https://docs.confluent.io/platform/current/connect/references/restapi.html](https://docs.confluent.io/platform/current/connect/references/restapi.html)
- **Base URL:** `https://localhost:8083`

#### Tags

- Connectors
- Kafka Connect
- REST

#### Properties

- [Documentation](https://docs.confluent.io/platform/current/connect/references/restapi.html)
- [Postman Collection](collections/confluent-the-data-streaming-platform.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/confluent-the-data-streaming-platform.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### ksqlDB REST API

The ksqlDB REST API exposes ksqlDB, Confluent's streaming SQL engine, over HTTP. Clients submit streaming SQL statements, query streams and tables (push and pull queries), and inspect server status.

- **Human URL:** [https://docs.ksqldb.io/en/latest/developer-guide/api/](https://docs.ksqldb.io/en/latest/developer-guide/api/)
- **Base URL:** `https://localhost:8088`

#### Tags

- ksqlDB
- REST
- Streaming SQL

#### Properties

- [Documentation](https://docs.ksqldb.io/en/latest/developer-guide/api/)
- [Postman Collection](collections/confluent-the-data-streaming-platform.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/confluent-the-data-streaming-platform.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Confluent Cloud for Apache Flink REST API

The Confluent Cloud for Apache Flink REST API manages Flink compute pools, statements, and workspaces for stateful stream processing on Confluent Cloud. It is part of the Confluent Cloud REST surface.

- **Human URL:** [https://docs.confluent.io/cloud/current/flink/index.html](https://docs.confluent.io/cloud/current/flink/index.html)
- **Base URL:** `https://flink.region.aws.confluent.cloud`

#### Tags

- Apache Flink
- Stream Processing

#### Properties

- [Documentation](https://docs.confluent.io/cloud/current/flink/index.html)
- [Postman Collection](collections/confluent-the-data-streaming-platform.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/confluent-the-data-streaming-platform.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/confluent)
- [Website](https://www.confluent.io/)
- [Developer  Portal](https://developer.confluent.io/)
- [Documentation](https://docs.confluent.io/)
- [Cloud  A P I  Reference](https://docs.confluent.io/cloud/current/api.html)
- [Git Hub](https://github.com/confluentinc)
- [Blog](https://www.confluent.io/blog/)
- [Pricing](https://www.confluent.io/pricing/)
- [Status Page](https://status.confluent.cloud/)
- [Login](https://confluent.cloud/login)
- [Marketplace](https://www.confluent.io/hub/)
- [Training](https://training.confluent.io/)
- [Terms of Service](https://www.confluent.io/terms-of-service/)
- [Privacy Policy](https://www.confluent.io/privacy-policy/)
- [Integrations](https://www.confluent.io/partner/)
- [L L Ms Txt](https://docs.confluent.io/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
