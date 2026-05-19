#  Real-Time Data Streaming Platform

An end-to-end **real-time data engineering platform** designed to simulate high-volume transactional data processing using modern distributed systems and streaming technologies.

This project demonstrates a **production-like data pipeline** covering ingestion, stream processing, distributed storage, analytics, and interactive visualization.

---

##  Overview

This system simulates a real-time event-driven architecture where data continuously flows through multiple distributed layers:

* Data generation using a Python-based producer
* High-throughput event streaming via Apache Kafka
* Real-time stream processing using Apache Spark Structured Streaming
* Scalable storage in Hadoop HDFS using Parquet format
* SQL-based analytics using Apache Hive
* Business intelligence dashboards using Power BI

---

##  System Architecture

The diagram below illustrates the end-to-end data flow across all system components, from ingestion to visualization.

<img width="1829" height="860" alt="architecture" src="https://github.com/user-attachments/assets/7e3cd2e7-1555-4418-9fc4-91083087bfa9" />

<p align="center">
  <em>Figure 1: Real-Time Event-Driven Data Engineering Architecture</em>
</p>

---

##  Architecture Flow

```
Python Producer
      │
      ▼
Apache Kafka (Event Streaming)
      │
      ▼
Spark Structured Streaming (Processing Layer)
      │
      ▼
Hadoop HDFS (Parquet Storage)
      │
      ▼
Apache Hive (Analytics Layer)
      │
      ▼
Power BI (Visualization Layer)
```

---

##  Tech Stack

Modern big data ecosystem technologies used in this project:

* Python (Data simulation & automation)
* Apache Kafka (Distributed event streaming)
* Apache Spark Structured Streaming (Real-time processing)
* Hadoop HDFS (Distributed storage layer)
* Apache Hive (Data warehousing & SQL analytics)
* Apache HBase (Low-latency NoSQL storage)
* Apache Airflow (Workflow orchestration – extensible)
* Docker (Containerized deployment)
* Power BI (Business intelligence & visualization)
* Parquet (Optimized columnar storage format)

---

##  Project Structure

```
Real-Time-Data-Streaming-Platform/
│
├── producer/              # Kafka data generator
├── streaming/             # Spark streaming jobs
├── transformation/        # Data processing logic
│
├── screenshots/           # Architecture & dashboard images
│
├── docker-compose.yml     # Multi-service environment setup
├── requirements.txt       # Python dependencies
└── README.md
```

---

##  Deployment (Docker)

### Start the platform

```bash
docker-compose up -d
```

### Stop the platform

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

### 1. Start Data Producer

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

### Example Analytical Query

```sql
SELECT currency, COUNT(*) AS total_transactions
FROM transactions
GROUP BY currency;
```

---

##  Visualization (Power BI)

The dashboard provides:

* Real-time transaction monitoring
* Currency-based analytics
* Key performance indicators (KPIs)
* Interactive filtering and insights

<img width="1143" height="682" alt="powerbi" src="https://github.com/user-attachments/assets/1b1b5cad-3db4-4c63-a170-72db926f4ee1" />

---

##  Key Features

* End-to-end real-time streaming pipeline
* Event-driven distributed architecture
* Scalable ETL/ELT processing design
* Columnar storage optimization (Parquet)
* SQL-based analytics layer
* Interactive BI dashboards
* Fully containerized environment

---

## Core Concepts

* Event-Driven Architecture
* Distributed Systems Design
* Stream Processing (Real-Time Analytics)
* Data Lake Architecture
* Big Data Engineering Pipelines
* ETL / ELT Patterns

---

##  Sample Output

| id  | value | amount | currency | timestamp  |
| --- | ----- | ------ | -------- | ---------- |
| 374 | 6963  | 424.35 | USD      | 1777742091 |
| 647 | 3949  | 294.13 | EGP      | 1777741742 |

---

##  Future Enhancements

* Apache Airflow orchestration layer
* Kubernetes deployment for scalability
* Grafana monitoring & observability
* Cloud deployment (AWS / Azure)
* Data quality validation layer
* CI/CD pipeline integration

---

##  Authors

**Fatma Khalid & Wesam Sabry**

---

##  Project Objective

To simulate a production-grade real-time streaming platform demonstrating modern data engineering architecture, distributed processing, and scalable analytics design.
