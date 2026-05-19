#  Real-Time Data Streaming Platform

An **end-to-end real-time data engineering platform** designed to simulate and process high-volume transactional data using modern distributed systems and streaming technologies.

The project demonstrates a production-like data pipeline that covers ingestion, stream processing, distributed storage, analytics, and visualization.

---

##  Overview

This system simulates a real-time event-driven architecture where data flows continuously through multiple distributed layers:

* Real-time data generation using a Python-based producer
* High-throughput event streaming via Apache Kafka
* Distributed stream processing using Spark Structured Streaming
* Scalable storage in Hadoop HDFS using Parquet format
* SQL-based analytics layer using Apache Hive
* Interactive business dashboards using Power BI

---

## System Architecture

The following diagram illustrates the end-to-end architecture of the real-time data streaming pipeline, showing how data flows across ingestion, processing, storage, analytics, and visualization layers.


<img width="1829" height="860" alt="image" src="https://github.com/user-attachments/assets/7e3cd2e7-1555-4418-9fc4-91083087bfa9" />


<p align="center">
  <em>Figure 1: Real-Time Event-Driven Data Engineering Architecture</em>
</p>

---

##  System Architecture

```
                 ┌──────────────────┐
                 │  Python Producer │
                 └────────┬─────────┘
                          │
                          ▼
                 ┌──────────────────┐
                 │ Apache Kafka     │
                 │ (Event Streaming)│
                 └────────┬─────────┘
                          │
                          ▼
        ┌────────────────────────────────┐
        │ Spark Structured Streaming     │
        │ (Real-time Processing Layer)   │
        └────────┬───────────────────────┘
                 │
                 ▼
        ┌────────────────────────┐
        │ Hadoop HDFS           │
        │ (Parquet Storage)     │
        └────────┬──────────────┘
                 │
                 ▼
        ┌────────────────────────┐
        │ Apache Hive           │
        │ (Analytics Layer)     │
        └────────┬──────────────┘
                 │
                 ▼
        ┌────────────────────────┐
        │ Power BI Dashboard    │
        │ (Visualization Layer) │
        └────────────────────────┘
```

---

##  Tech Stack

This project leverages a modern big data ecosystem:

* Python (Data Simulation & Scripting)
* Apache Kafka (Distributed Event Streaming)
* Apache Spark Structured Streaming (Real-Time Processing)
* Hadoop HDFS (Distributed Storage Layer)
* Apache Hive (Data Warehousing & SQL Analytics)
* Apache HBase (Low-latency NoSQL access)
* Apache Airflow (Workflow Orchestration – extensible)
* Docker (Containerized Environment)
* Power BI (Business Intelligence & Visualization)
* Parquet (Optimized Columnar Storage)

---

##  Project Structure

```
Real-Time-Data-Streaming-Platform/
│
├── producer/               # Kafka data generator
├── streaming/             # Spark streaming jobs
├── transformation/        # Data transformation logic
│
├── screenshots/           # Architecture & outputs
│
├── docker-compose.yml     # Multi-service environment
├── requirements.txt       # Python dependencies
└── README.md
```

---

##  Deployment (Docker)

### Start all services

```bash
docker-compose up -d
```

### Stop services

```bash
docker-compose down
```

---

##  Kafka Setup

### Create topic

```bash
kafka-topics --create \
--topic transaction \
--bootstrap-server localhost:9092
```

---

##  Run the Pipeline

### 1. Start Producer

```bash
python producer.py
```

### 2. Start Spark Streaming Job

```bash
spark-submit spark_streaming.py
```

---

##  Hive Analytics Layer

### Create External Table

```sql
CREATE EXTERNAL TABLE transactions (
    id INT,
    value INT,
    amount DOUBLE,
    currency STRING,
    timestamp BIGINT
)
STORED AS PARQUET
LOCATION '/data/raw/transactions_parquet';
```

### Analytical Query

```sql
SELECT currency, COUNT(*) AS total_transactions
FROM transactions
GROUP BY currency;
```

---

## Visualization Layer (Power BI)

The Power BI dashboard enables:

* Real-time transaction monitoring
* Currency-based analytics
* Key performance indicators (KPIs)
* Interactive filtering & insights
  
<img width="1143" height="682" alt="Power BI" src="https://github.com/user-attachments/assets/1b1b5cad-3db4-4c63-a170-72db926f4ee1" />

---

##  Key Features

* End-to-end real-time streaming architecture
* Event-driven distributed system design
* Scalable ETL / ELT pipeline
* Columnar storage optimization (Parquet)
* SQL-based analytical layer
* Interactive BI dashboards
* Fully containerized infrastructure

---

##  Core Concepts

* Event-Driven Architecture
* Distributed Systems Design
* Stream Processing (Real-Time Analytics)
* Data Lake Architecture
* Big Data Engineering Pipelines
* ETL / ELT Processing Models

---

##  Sample Output

| id  | value | amount | currency | timestamp  |
| --- | ----- | ------ | -------- | ---------- |
| 374 | 6963  | 424.35 | USD      | 1777742091 |
| 647 | 3949  | 294.13 | EGP      | 1777741742 |

---

##  Future Enhancements

* Apache Airflow orchestration for pipeline scheduling
* Kubernetes deployment for scalability
* Grafana monitoring & observability
* Cloud deployment (AWS / Azure)
* Data quality & validation layer
* CI/CD pipeline integration

---

##  Authors

**Fatma Khalid & Wesam Sabry**

---

##  Project Objective

To simulate a production-grade real-time streaming platform that demonstrates modern data engineering architecture, distributed processing, and scalable analytics design.
