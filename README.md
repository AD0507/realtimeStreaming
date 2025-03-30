# Real-Time Data Streaming Pipeline with Kafka, Flink, and PostgreSQL

This project demonstrates how to build a **real-time data streaming pipeline** from scratch using:

- 🐍 Python for generating and producing synthetic weather data
- 🦄 Apache Kafka as the message broker
- ⚡ Apache Flink for real-time stream processing and window-based aggregation
- 🐘 PostgreSQL as the final data sink for storing aggregated results

---

## 🚀 What This Project Does

- Generates synthetic weather data (random city + temperature) every few seconds using Python & Faker.
- Sends this data to a Kafka topic (`weather`) via a custom Kafka producer.
- Flink consumes the data from Kafka, aggregates temperature data by city using a **tumbling window** of 1 minute, and computes the average.
- The results are written into a PostgreSQL table.
- Everything runs in Docker containers and is orchestrated via `docker-compose`.

---
## Architecture Diagram


---
## Flink Job Logic
- Uses Java with Apache Flink 1.16
- Aggregates messages using a Keyed Tumbling Window
- Groups by city
- Computes the average temperature over 60-second intervals
- Uses Flink’s JdbcSink to write to PostgreSQL

---

## Features Completed
- Real-time data generation via Faker library in Python
- Kafka producer & topic integration
- Tumbling window aggregation with Flink
- Dockerized services using Docker Compose
- Data persistence in PostgreSQL
- Resilience using wait-for-it.sh scripts
