# Apache Beam (apache-beam)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Apache Beam is a unified, open-source programming model developed by the Apache Software Foundation for defining both batch and streaming data processing pipelines. It provides a portable API layer that lets developers write pipeline logic once in Java, Python, or Go and deploy it to multiple execution engines (runners) including Apache Flink, Apache Spark, Google Cloud Dataflow, and the direct runner for local testing.

**URL:** [https://beam.apache.org/](https://beam.apache.org/)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Apache, Batch Processing, Data Pipeline, ETL, Open Source, Python, Streaming, Unified Model

## Timestamps

- **Created:** 2026-03-16
- **Modified:** 2026-04-19

## APIs

### Apache Beam SDK
The Apache Beam SDK provides the programming model for constructing data processing pipelines in Java, Python, and Go with PCollections, PTransforms, and Runners.

**Human URL:** [https://beam.apache.org/documentation/](https://beam.apache.org/documentation/)

#### Tags

 - Batch, Pipeline, SDK, Streaming

#### Properties

- [Documentation](https://beam.apache.org/documentation/)
- [APIReference](https://beam.apache.org/releases/pydoc/current/)
- [GettingStarted](https://beam.apache.org/get-started/wordcount-example/)

### Apache Beam Job Service API
The Beam Job Service API provides a gRPC-based interface for submitting, managing, and monitoring Apache Beam pipeline jobs on supported runners.

**Human URL:** [https://beam.apache.org/documentation/runtime/environments/](https://beam.apache.org/documentation/runtime/environments/)

#### Tags

 - gRPC, Job Management, Portability

#### Properties

- [Documentation](https://beam.apache.org/documentation/runtime/environments/)

## Common Properties

- [GitHubOrganization](https://github.com/apache)
- [GitHubRepository](https://github.com/apache/beam)
- [Documentation](https://beam.apache.org/)
- [GettingStarted](https://beam.apache.org/get-started/)
- [Tutorials](https://beam.apache.org/get-started/wordcount-example/)
- [Support](https://beam.apache.org/community/contact-us/)
- [TermsOfService](https://www.apache.org/licenses/)
- [ChangeLog](https://beam.apache.org/blog/)
- [Python SDK (PyPI)](https://pypi.org/project/apache-beam/)
- [Java SDK (Maven)](https://search.maven.org/artifact/org.apache.beam/beam-sdks-java-core)
- [Go SDK](https://pkg.go.dev/github.com/apache/beam/sdks/v2/go/pkg/beam)

## Features

| Name | Description |
|------|-------------|
| Unified Batch and Streaming | Single programming model for both batch and streaming data processing with consistent semantics. |
| Runner Portability | Write pipeline logic once and execute on Apache Flink, Spark, Google Dataflow, Samza, or the local direct runner. |
| Multi-Language Support | Native SDKs for Java, Python, and Go with cross-language transform support for mixing languages. |
| Windowing and Triggers | Flexible windowing (fixed, sliding, session, global) and trigger strategies for streaming data processing. |
| I/O Connectors | Built-in connectors for BigQuery, Kafka, Pub/Sub, GCS, HDFS, databases, and many other sources and sinks. |
| Beam SQL | SQL-based data processing on Beam PCollections using Apache Calcite for query planning. |
| ML Integration | RunInference transform for integrating ML model inference into Beam pipelines with TensorFlow, PyTorch, and sklearn. |
| Schema-Aware Processing | Schema inference and typed PCollections for structured data processing with automatic serialization. |
| Cross-Language Transforms | Call Java transforms from Python pipelines and vice versa via the Beam portability framework. |
| Metrics and Monitoring | Built-in metrics API and integration with runner-specific monitoring dashboards. |

## Use Cases

| Name | Description |
|------|-------------|
| ETL Pipelines | Extract, transform, and load data between storage systems using portable, reusable pipeline components. |
| Real-Time Stream Processing | Process high-throughput event streams with low-latency windowing and triggering strategies. |
| Batch Data Analytics | Compute aggregate statistics, joins, and group-by operations on large historical datasets. |
| ML Model Inference at Scale | Run ML model inference in distributed pipelines using the RunInference transform. |
| Log and Event Processing | Parse, filter, and enrich log events from Kafka or Pub/Sub for operational analytics. |
| Data Migration | Migrate data between cloud providers and storage systems using Beam's portable I/O connectors. |

## Integrations

| Name | Description |
|------|-------------|
| Google Cloud Dataflow | Managed Apache Beam runner on Google Cloud with autoscaling and monitoring. |
| Apache Flink | Apache Flink runner for stateful stream processing with exactly-once semantics. |
| Apache Spark | Apache Spark runner for batch and streaming processing on Spark clusters. |
| Apache Kafka | Kafka I/O connector for reading and writing Kafka topics in Beam pipelines. |
| Google BigQuery | BigQuery I/O connector for reading and writing BigQuery tables in Beam pipelines. |
| Apache Hadoop | HDFS I/O connector for reading and writing files on Hadoop HDFS. |
| TensorFlow Extended (TFX) | TFX uses Beam as the runtime for ML data validation and preprocessing components. |

## Vocabulary

- [Apache Beam Vocabulary](vocabulary/apache-beam-vocabulary.yaml) — Domain taxonomy mapping 6 resources, 5 actions, and 2 personas for Beam pipeline development and ML integration

## Maintainers

**FN:** Kin Lane

**Email:** info@apievangelist.com
