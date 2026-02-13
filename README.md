# Hi, I'm Sebastien Moreau 👋  
Junior Data Engineer | Streaming & Lakehouse Architectures | Data Quality & Reliability

---

## 👨‍💻 About Me

I’m a Junior Data Engineer passionate about building reliable and scalable data systems.
Through hands-on academic and volunteer projects, I’ve designed and implemented end-to-end batch and streaming pipelines — from data ingestion and CDC to transformation, validation, and analytics-ready outputs.
I enjoy working on event-driven architectures, lakehouse systems (Bronze/Silver/Gold), and production-like environments where data quality, reliability, and observability matter.
I’m currently seeking a Data Engineer position — in France or internationally — where I can contribute to modern data platforms while continuing to grow in distributed systems and large-scale data processing.

---

## 🛠 Technical Skills

**Programming & Querying**
- Python (data processing, APIs, streaming consumers, validation scripts)
- SQL (data modeling, transformations, analytics queries)

**Data Engineering**
- Batch & Streaming Pipelines
- Apache Spark (Structured Streaming)
- Kafka / Redpanda
- CDC with Debezium
- Data Lakehouse architecture (Bronze / Silver / Gold)
- ETL / ELT design
- Data modeling (relational & dimensional concepts)

**Orchestration & Automation**
- Kestra
- Workflow automation with Dockerized services

**Databases & Storage**
- PostgreSQL
- MongoDB (Replica Set configuration & replication, Sharding)
- DuckDB
- Delta Lake
- FAISS (vector indexing)

**Data Quality & Reliability**
- Great Expectations
- Integrity validation & schema comparison
- Replication testing & performance benchmarking
- Checkpointing & fault tolerance (Spark)

**Cloud & Infrastructure**
- AWS
- Docker & Docker Compose
- Environment-based configuration & secrets management

**APIs & Backend**
- FastAPI
- REST API ingestion
- Slack API integration

**Observability & Monitoring**
- Prometheus (basic metrics exposure)
- Logging strategies in distributed pipelines

---

## 📦 Selected Projects

### 🔹 [Real-Time HR & Sport Streaming Lakehouse](https://github.com/SebM42/POC-Employees-sport-event-Streaming)
Designed and implemented an end-to-end real-time streaming pipeline simulating HR and sport activity tracking.

- CDC from PostgreSQL using Debezium
- Event streaming with Redpanda (Kafka API)
- Python micro-batch stream processing
- Lakehouse architecture with Delta Lake (Bronze → Silver → Gold)
- Data quality validation using Great Expectations
- Real-time Slack notifications
- Metrics exposure with Prometheus

This project demonstrates event-driven architecture, business rule processing, SCD Type 2 historization, and data reliability in a modern streaming stack.

---

### 🔹 [MongoDB Replica Set with S3 Migration & Integrity Validation](https://github.com/SebM42/POC-MongoDB-Migration-with-replicaset)

Built a production-like MongoDB architecture fully containerized with automated initialization.

- Automated Replica Set deployment (1 primary, 2 secondaries)
- Secure internal authentication via keyFile
- JSON ingestion from AWS S3 using boto3
- Data normalization and datetime conversion
- Post-migration integrity checks (schema, types, duplicates)
- Replication consistency validation
- Query performance benchmarking

This project focuses on data integrity, distributed database configuration, and operational reliability.

---

### 🔹 [Spark Structured Streaming – Client Ticket System](https://github.com/SebM42/POC-Client-Ticket-Streaming)
Developed a real-time ticket streaming system using Spark Structured Streaming.

- Synthetic ticket generation via Python producer
- Real-time ingestion into Redpanda (Kafka API)
- Dynamic Spark streaming consumer
- 1-second window aggregations
- Checkpointing for fault tolerance
- JSON persistence of aggregated outputs

This project demonstrates scalable streaming analytics and resilient processing pipelines.

---

### 🔹 [Data Pipeline Automation with Kestra](https://github.com/SebM42/POC-Pipeline-Kestra)

Designed an automated monthly data pipeline orchestrated with Kestra.

- Excel → Parquet conversion
- SQL transformations with DuckDB
- Data cleaning & deduplication
- Automated data quality assertions
- Revenue analytics & anomaly detection (z-score)
- Parallel execution branches

This project highlights orchestration, reproducibility, and analytics-ready data production.

## 🤝 Volunteer Data Projects

### [Trawl Watch – BLOOM Association](https://github.com/dataforgoodfr/12_bloom)

Contributed to the design and implementation of a data platform tracking industrial fishing vessel activity across European waters.

- Designed transformation architecture and data models for multi-stage processing
- Defined intermediate and analytical data structures across the pipeline
- Implemented business logic to transform raw vessel positions into structured excursion-level datasets
- Collaborated with frontend teams on user journey definition and UX design, translating user needs into data models and API-ready outputs

### [Dans Mon Eau – Public Health Data Platform](https://github.com/dataforgoodfr/13_pollution_eau)

Contributed to a nationwide public data platform exposing drinking water quality metrics across France.

- Processed large open government datasets from public health authorities
- Performed exploratory data analysis to disentangle merged datasets and reconstruct original data structures
- Cleaned, normalized, and structured raw datasets for analytical and public-facing use
- Collaborated within a cross-functional team of 40+ volunteers (data engineers, analysts, developers, designers)

## 🌱 Currently Improving

- Analytics engineering with dbt (modular transformations, testing, documentation)  
- Advanced orchestration patterns with Apache Airflow  
- Databricks ecosystem for scalable Spark-based data platforms  
- Production-grade data engineering practices (observability, reliability, CI/CD)

---

## 📫 Let's Connect

- Email: sebastien.t.moreau@gmail.com

