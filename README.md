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

**Backend & Infra:** Python, FastAPI, SQLAlchemy, Django · Airflow · Kubernetes, Docker, Terraform

**Observability & Governance:** Prometheus, Grafana · Data Contracts, Column-level lineage · Apache Ranger (RBAC/ABAC)

**Cloud & Storage:** AWS (S3, Athena, Glue, Redshift) · MinIO

---

## Projects

### AIDE — Metadata Control Plane for Data Platforms
https://github.com/tarodo/aide

Production-grade **metadata & governance service** controlling schema evolution, data contracts, and ingestion safety.

- Contract enforcement at ingestion layer
- Schema evolution with breaking-change detection
- Column-level lineage & metadata management
- **Impact:** onboarding from 3 days → 3 hours, zero breaking schema changes in production

### Clouder Core — Serverless Music Data Pipeline
https://github.com/tarodo/clouder-core

**Serverless ingestion + canonicalization pipeline** that collects weekly music release data from Beatport, stores raw snapshots in S3, and normalizes into PostgreSQL.

- AWS Lambda, SQS, Aurora PostgreSQL Serverless, Terraform
- Async processing with idempotent canonicalization
- Infrastructure-as-Code, zero-server maintenance

---

## Contact

- [LinkedIn](https://www.linkedin.com/in/volozhanin/)
- [Email](mailto:r.volozh@gmail.com)

---

*In real-world data platforms - failure is not an edge case, it's the default.*
