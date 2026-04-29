# Confluent | The Data Streaming Platform (confluent-the-data-streaming-platform)

Confluent is a fully managed data streaming platform built by the original creators of Apache Kafka. It lets organizations stream, connect, process, and govern data in motion through a cloud-native service (Confluent Cloud) and the on-prem/self-managed Confluent Platform. Confluent's developer surface includes the Confluent Cloud REST API for managing clusters, environments, and access; the Kafka REST Proxy for producing and consuming events over HTTP; the Schema Registry REST API for governance of Avro, JSON Schema, and Protobuf schemas; the Kafka Connect REST API for managing connectors; the ksqlDB REST API for stream processing; and managed Apache Flink. Authentication is API-key based (Cloud) or HTTP/mTLS/OAuth (Platform).

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/confluent-the-data-streaming-platform/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party
- **Classification:** Company

## Tags

- Apache Flink, Apache Kafka, Confluent Cloud, Connectors, Data Streaming, Event Streaming, Kafka Connect, ksqlDB, Real-Time Data, REST, Schema Registry, Stream Processing

## Timestamps

- **Created:** 2025-08-19
- **Modified:** 2026-04-28

## APIs

### Confluent Cloud REST API

The Confluent Cloud REST API is the management plane for Confluent Cloud. It is used to manage organizations, environments, Kafka and Flink clusters, service accounts, API keys, role bindings, networking, schema registry clusters, and connector instances. The API uses Cloud API keys for authentication and follows Confluent's resource-oriented v2 conventions.

**Human URL:** [https://docs.confluent.io/cloud/current/api.html](https://docs.confluent.io/cloud/current/api.html)

#### Tags

- Confluent Cloud, Management, REST

#### Properties

- [Documentation](https://docs.confluent.io/cloud/current/api.html)
- [API Reference](https://docs.confluent.io/cloud/current/api.html)

#### Features

- Cluster Lifecycle Management
- Environments and Organizations
- API Key Management
- RBAC and Service Accounts
- Networking and Private Link
- Schema Registry Cluster Management
- Connector Provisioning
- Flink Compute Pools

#### Use Cases

- Provision Kafka clusters in Confluent Cloud
- Automate environment and access management
- Rotate API keys and manage service accounts
- Wire up private networking for clusters
- Manage Flink compute pools and statements

### Confluent Kafka REST API

The Kafka REST API (Confluent REST Proxy in self-managed deployments, Kafka REST in Cloud) provides HTTP access to Apache Kafka topics, consumers, partitions, brokers, and ACLs. Clients without a native Kafka library can produce and consume records, manage topics, and inspect metadata over HTTP.

**Human URL:** [https://docs.confluent.io/platform/current/kafka-rest/api.html](https://docs.confluent.io/platform/current/kafka-rest/api.html)

#### Tags

- Apache Kafka, Producer, Consumer, REST

#### Properties

- [Documentation](https://docs.confluent.io/platform/current/kafka-rest/api.html)
- [Cloud Documentation](https://docs.confluent.io/cloud/current/kafka-rest/index.html)

#### Features

- Topic Management
- Produce and Consume over HTTP
- Partition Inspection
- Consumer Group Management
- Broker Metadata
- ACL Management

#### Use Cases

- Produce events from clients without a Kafka library
- Bridge legacy systems to Kafka over HTTP
- Inspect topic and partition metadata from web tools
- Manage ACLs from automation scripts

### Confluent Schema Registry REST API

The Schema Registry REST API stores and serves Avro, JSON Schema, and Protobuf schemas with versioning and compatibility enforcement. The full developer profile lives in the api-evangelist/confluent-schema-registry repository.

**Human URL:** [https://docs.confluent.io/platform/current/schema-registry/develop/api.html](https://docs.confluent.io/platform/current/schema-registry/develop/api.html)

#### Tags

- Avro, JSON Schema, Protobuf, Schema Registry

#### Properties

- [Documentation](https://docs.confluent.io/platform/current/schema-registry/develop/api.html)
- [Companion Repo](https://github.com/api-evangelist/confluent-schema-registry)

### Kafka Connect REST API

The Kafka Connect REST API manages connectors, tasks, and worker configuration. Operators use it to deploy, configure, pause, resume, and delete source and sink connectors, inspect task status, and restart failed tasks.

**Human URL:** [https://docs.confluent.io/platform/current/connect/references/restapi.html](https://docs.confluent.io/platform/current/connect/references/restapi.html)

#### Tags

- Connectors, Kafka Connect, REST

#### Properties

- [Documentation](https://docs.confluent.io/platform/current/connect/references/restapi.html)

### ksqlDB REST API

The ksqlDB REST API exposes ksqlDB, Confluent's streaming SQL engine, over HTTP. Clients submit streaming SQL statements, query streams and tables (push and pull queries), and inspect server status.

**Human URL:** [https://docs.ksqldb.io/en/latest/developer-guide/api/](https://docs.ksqldb.io/en/latest/developer-guide/api/)

#### Tags

- ksqlDB, REST, Streaming SQL

#### Properties

- [Documentation](https://docs.ksqldb.io/en/latest/developer-guide/api/)

### Confluent Cloud for Apache Flink REST API

Manages Flink compute pools, statements, and workspaces for stateful stream processing on Confluent Cloud.

**Human URL:** [https://docs.confluent.io/cloud/current/flink/index.html](https://docs.confluent.io/cloud/current/flink/index.html)

#### Tags

- Apache Flink, Stream Processing

#### Properties

- [Documentation](https://docs.confluent.io/cloud/current/flink/index.html)

## Common Properties

- [Website](https://www.confluent.io/)
- [Developer Portal](https://developer.confluent.io/)
- [Documentation](https://docs.confluent.io/)
- [Cloud API Reference](https://docs.confluent.io/cloud/current/api.html)
- [GitHub](https://github.com/confluentinc)
- [Blog](https://www.confluent.io/blog/)
- [Pricing](https://www.confluent.io/pricing/)
- [Status](https://status.confluent.cloud/)
- [Login](https://confluent.cloud/login)
- [Marketplace](https://www.confluent.io/hub/)
- [Training](https://training.confluent.io/)
- [Terms of Service](https://www.confluent.io/terms-of-service/)
- [Privacy Policy](https://www.confluent.io/privacy-policy/)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
