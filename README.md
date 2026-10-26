# Confluent | the Data Streaming Platform (confluent-the-data-streaming-platform)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
