<div align="center">

# SÉBASTIEN MOREAU · DATA ENGINEER

**Pipelines · Lakehouse · CDC · Data Quality · Lineage**

[![Email](https://img.shields.io/badge/sebastien.t.moreau@gmail.com-0d1117?style=flat-square&logo=gmail&logoColor=58a6ff&labelColor=0d1117)](mailto:sebastien.t.moreau@gmail.com)

</div>

---

## About

Data Engineer focused on **production-grade pipelines** — from raw ingestion to business-ready outputs.

I build systems where data quality, traceability, and compliance are first-class concerns — not afterthoughts.  
My work spans batch and event-driven architectures, CDC-based ingestion, lakehouse modeling, entity resolution, and end-to-end lineage.  
I translate audit and compliance requirements into **reliable, shippable workflows** — with full ownership across the stack.

> Master's equivalent in Data Engineering — OpenClassrooms (2026).  
> Open to relocation — Belgium, Netherlands, Sweden, Denmark.

---

## Stack

<div align="center">

**— Core —**

![Python](https://img.shields.io/badge/Python-0d1117?style=flat-square&logo=python&logoColor=58a6ff)
![SQL](https://img.shields.io/badge/SQL-0d1117?style=flat-square&logo=postgresql&logoColor=58a6ff)

**— Ingestion & Streaming —**

![Kafka](https://img.shields.io/badge/Kafka%20%2F%20Redpanda-0d1117?style=flat-square&logo=apachekafka&logoColor=58a6ff)
![Debezium](https://img.shields.io/badge/Debezium%20CDC-0d1117?style=flat-square&logo=apachekafka&logoColor=f0883e)
![Airbyte](https://img.shields.io/badge/Airbyte-0d1117?style=flat-square&logo=airbyte&logoColor=58a6ff)
![PySpark](https://img.shields.io/badge/PySpark-0d1117?style=flat-square&logo=apachespark&logoColor=f0883e)

**— Storage & Lakehouse —**

![Delta Lake](https://img.shields.io/badge/Delta%20Lake-0d1117?style=flat-square&logo=databricks&logoColor=f0883e)
![Databricks](https://img.shields.io/badge/Databricks-0d1117?style=flat-square&logo=databricks&logoColor=f0883e)
![dbt](https://img.shields.io/badge/dbt-0d1117?style=flat-square&logo=dbt&logoColor=f0883e)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0d1117?style=flat-square&logo=postgresql&logoColor=58a6ff)
![MongoDB](https://img.shields.io/badge/MongoDB-0d1117?style=flat-square&logo=mongodb&logoColor=3fb950)
![DuckDB](https://img.shields.io/badge/DuckDB-0d1117?style=flat-square&logo=duckdb&logoColor=f0883e)
![AWS S3](https://img.shields.io/badge/AWS%20S3-0d1117?style=flat-square&logo=amazons3&logoColor=f0883e)

**— Orchestration & Infra —**

![Databricks Workflows](https://img.shields.io/badge/Databricks%20Workflows-0d1117?style=flat-square&logo=databricks&logoColor=f0883e)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-0d1117?style=flat-square&logo=githubactions&logoColor=58a6ff)
![Kestra](https://img.shields.io/badge/Kestra-0d1117?style=flat-square&logo=kestra&logoColor=58a6ff)
![Airflow](https://img.shields.io/badge/Airflow-0d1117?style=flat-square&logo=apacheairflow&logoColor=58a6ff)
![Docker](https://img.shields.io/badge/Docker-0d1117?style=flat-square&logo=docker&logoColor=58a6ff)

**— Quality & Observability —**

![Great Expectations](https://img.shields.io/badge/Great%20Expectations-0d1117?style=flat-square&logo=python&logoColor=3fb950)
![Prometheus](https://img.shields.io/badge/Prometheus-0d1117?style=flat-square&logo=prometheus&logoColor=f0883e)

</div>

---

## Projects

### ▸ [Economic Activity Monitor — End-to-End Lakehouse Pipeline (SIRENE/INSEE)](https://github.com/SebM42/insee-sirene-monitor)
`Python` `Databricks` `Delta Lake` `dbt` `Databricks Workflows` `GitHub Actions` `Unity Catalog`

Production-grade monthly pipeline on 42M+ French business establishments (INSEE SIRENE). Configurable geographic scope. Medallion architecture (Bronze → Silver → Gold): Bronze as a transit-only dead letter queue, Silver as a SCD Type 2 historical source of truth, Gold as dbt-powered business aggregations. Single atomic Delta MERGE for Silver writes — no rollback needed. Circuit breaker pattern for transformation failure isolation, reset via GitHub Actions manual trigger without direct Databricks access. Gold failures trigger automatic rollback via Delta time travel. Full ADR documentation (DECISIONS.md). Deployable on any Databricks workspace in minutes.

> **Key decisions:** significance filter on tracked columns — INSEE updates `dateDernierTraitementEtablissement` for both business and technical changes, filtering prevents spurious SCD2 periods · single atomic MERGE eliminates partial write risk without rollback logic · Bronze as implicit DLQ — batch retained until Silver transformation confirmed successful · two source files at initialization (stock + historical) to reconstruct full SCD2 history from day one · circuit breaker reset decoupled from Databricks access — operator only needs Git.

---

### ▸ [End-to-End Streaming Lakehouse — HR & Sport Activity](https://github.com/SebM42/POC-Employees-sport-event-Streaming)
`Python` `Kafka/Redpanda` `Debezium` `Delta Lake` `Great Expectations` `Prometheus` `OSMNX`

Production-grade event-driven pipeline: CDC from PostgreSQL via Debezium, Python micro-batch consumer (100ms poll), geospatial distance computation via OSMNX/BAN API. Delta Lake lakehouse (Bronze → Silver → Gold) with SCD Type 2 historization for full auditability. Data quality gates at every layer transition. Dead letter table for failed batches. Metrics exposed via Prometheus.

> **Key decisions:** CDC over polling — fact table capture is natural fit, state table monitored on 2 columns only · quarantine logic for implausible records · PII excluded from the lakehouse · SCD Type 2 scoped to auditability, not retroactive rule changes · at-least-once delivery with explicit crash recovery per stage.

---

### ▸ [MongoDB Replica Set — S3 Migration & Integrity Validation](https://github.com/SebM42/POC-MongoDB-Migration-with-replicaset)
`Python` `MongoDB` `boto3` `AWS S3`

Containerized MongoDB replica set with keyFile intra-cluster authentication. Automated S3 ingestion with JSON parsing and normalization. Post-migration integrity validation: schema checks, type enforcement, duplicate detection, replication consistency across all nodes. Fully automated bootstrap — zero manual intervention.

> **Key decisions:** 3 nodes across independent datacenters — simultaneous failure of 2 nodes in separate datacenters is statistically negligible, all 3 is not an operational scenario · odd node count reaches quorum without an arbiter · idempotent bootstrap skips init on subsequent restarts.

---

### ▸ [Orchestrated Monthly Pipeline — Analytics & Reporting](https://github.com/SebM42/POC-Pipeline-Kestra)
`Python` `Kestra` `DuckDB`

Kestra-orchestrated monthly pipeline: ingestion, SQL transformations, deduplication, per-step data quality assertions, parallel report generation (revenue analytics + z-score anomaly detection). CSV → Parquet upfront for columnar query performance with DuckDB. Custom Docker image to resolve C-level dependency constraints in Kestra's Python task type.

> **Key decisions:** per-step integrity checks rather than end-to-end only · partial failure isolation between reporting branches · Parquet chosen defensively given unknown volume baseline.

---

### ▸ [Conversational AI System — RAG Pipeline & Architecture Design](https://github.com/SebM42/Conversational-AI-System-RAG-Pipeline-Production-Architecture-Design)
`Python` `LangChain` `FAISS` `Mistral AI` `FastAPI`

Full production architecture study (POC → MVP): cloud design, cost modeling, and systematic component trade-off analysis across scalability, cost efficiency, fault tolerance, access control, and observability constraints. Two-service RAG system as POC implementation.

> **Key decisions:** two-stage LLM pipeline designed from the start to separate filter extraction from generation · single Mistral ecosystem to guarantee embedding space consistency · FAISS FlatL2 for exact search at POC scale, with explicit migration path to Pinecone documented for production.

---

### ▸ MongoDB Schema Migration — Structured → Document + Sharding *(coming soon)*
`Python` `MongoDB`

Relational-to-document schema migration with a configurable transformation engine — schema mapping defined as data config rather than hardcoded logic. Sharding strategy designed around the business access pattern.

---

## Volunteer

| Project | Org | Role |
|---|---|---|
| [Trawl Watch](https://github.com/dataforgoodfr/12_bloom) | BLOOM Association | Transformation architecture · Data modeling · Business logic implementation |
| [Dans Mon Eau](https://github.com/dataforgoodfr/13_pollution_eau) | Public Health Data Platform | EDA on opaque merged datasets · Normalization · Cross-functional team (40+ volunteers) |

> Dans Mon Eau is in production and publicly accessible. Trawl Watch pre-production repository is publicly available on GitHub.
