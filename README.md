# Roman Volozhanin

### Senior Data Engineer | Lakehouse Architect | Backend-minded

I design and build **data platforms as distributed systems** - with clear contracts, strong observability, and production-grade reliability.

Currently leading a **300TB+ Lakehouse platform** processing **1B+ CDC events/day** across **70+ heterogeneous sources** in a regulated banking environment.

---

## What I Do

- Architect **Lakehouse platforms (Iceberg, Spark, Impala)** at scale
- Build **contract-driven data systems** with schema governance & lineage
- Design **reliable CDC ingestion** (Kafka, Debezium, idempotency patterns)
- Treat data pipelines as **production services** (SLOs, monitoring, failure handling)
- Translate business problems into **clear technical decisions (ADRs/RFCs)**

---

## Engineering Principles

- **Clarity over complexity** - if you can't explain it, you don't understand it
- **Contracts over assumptions** - schemas are APIs
- **Observability by design** - not as an afterthought
- **Failure is expected** - systems must survive it

---

## Tech Stack

**Data Platform:** Apache Iceberg, Spark, Impala, Flink, dbt, Kafka, Debezium, Oracle GoldenGate

**Backend & Infra:** Python, Rust, FastAPI, SQLAlchemy, Django · Airflow · Kubernetes, Docker, Terraform, GitHub Actions

**Observability & Governance:** Prometheus, Grafana · Data Contracts, Column-level lineage · Apache Ranger (RBAC/ABAC)

**Cloud & Storage:** AWS (Lambda, Step Functions, SQS, Aurora PostgreSQL, S3, Athena, Glue, Firehose, Redshift) · MinIO

---

## Projects

### [AIDE — Metadata Control Plane for Data Platforms](https://github.com/tarodo/aide)

Production-grade **metadata & governance service** controlling schema evolution, data contracts, and ingestion safety.

- Contract enforcement at ingestion layer
- Schema evolution with breaking-change detection
- Column-level lineage & metadata management
- **Impact:** onboarding from 3 days → 3 hours, zero breaking schema changes in production

### [CLOUDER — Serverless Data Pipeline + DJ Curation App](https://github.com/tarodo/clouder-core)

In production for a small group of DJs: scheduled Beatport ingest into an S3 raw zone, a canonical catalog of ~267k tracks in Aurora PostgreSQL built by entity resolution, and a React app for sorting each week's releases.

- Data contracts with record-level quarantine, 11 nightly data-quality SLOs, replay-safe backfill through Step Functions
- Iceberg silver/gold built nightly by dbt on Athena from Firehose telemetry
- Spotify and YouTube Music matching with measured precision; per-user models that suggest where each track goes; similar-track search in pgvector
- 20 Lambda functions, all in Terraform; every merge deploys through GitHub Actions OIDC behind a smoke test with automatic rollback
- [Live demo on sample data](https://tarodo.github.io/clouder-core/demo/)

### [pgcdc — PostgreSQL CDC in Rust](https://github.com/tarodo/pgcdc)

A minimal CDC engine: reads logical replication over `pgoutput` and emits whole transactions as JSON Lines. Built after a small Kafka-less consumer silently skipped 39 committed rows and still exited with code 0.

- A WAL position is acknowledged only after the sink's barrier succeeds (fsync for the file sink)
- Full vs key-only old rows; unchanged TOAST columns are named instead of reported as `null`
- Idle-slot advance, reconnect with backoff, non-zero exit on anything a retry cannot fix

### [debezium-iceberg-lab — Kafka-less CDC into Iceberg](https://github.com/tarodo/debezium-iceberg-lab)

Postgres → Debezium Server → Iceberg on MinIO with a Lakekeeper REST catalog, Prometheus/Grafana, data-quality checks and OpenLineage lineage (Marquez). Executed notebooks walk the Iceberg metadata chain, CDC semantics, in-transaction deduplication, and the delete-then-reinsert case where it goes wrong.

### [iceberg-file-formats-lab — File Formats under Iceberg, Measured](https://github.com/tarodo/iceberg-file-formats-lab)

Parquet, ORC and Avro as Iceberg tables that differ in one property; Lance and Vortex against bare Parquet; Iceberg features per format on format versions 2 and 3. Every number is written by code into one journal the README is rendered from. One finding: Avro manifests carry no column bounds, so a `DELETE` that costs Parquet and ORC nothing costs Avro a deletion vector.

---

## Contact

- [LinkedIn](https://www.linkedin.com/in/volozhanin/)
- [Email](mailto:r.volozh@gmail.com)

---

*In real-world data platforms - failure is not an edge case, it's the default.*
