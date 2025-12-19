# Twitter Sentiment Analysis (Databricks Streaming Pipeline)

An end-to-end **Spark Structured Streaming** pipeline built in **Databricks** to process tweet-like text data and produce sentiment-ready analytics using the **Medallion Architecture** (**Bronze → Silver → Gold**). The notebook includes stream monitoring, exploratory analysis, and a cleanup workflow via Databricks widgets.

---

## What this project does

###  Bronze (Raw → Bronze)
- Ingests raw tweet/text records using **Structured Streaming**
- Writes streaming output into a **Bronze Delta table** (raw/near-raw format)

###  Silver (Bronze → Silver)
- Transforms Bronze into a cleaner, structured dataset
- Typical operations include: parsing, cleaning, normalization, type casting, and enrichment
- Writes output to a **Silver Delta table**

###  Gold (Silver → Gold)
- Aggregates/derives analytics-ready outputs (metrics, rollups, summaries)
- Writes to a **Gold Delta table** for consumption (dashboards / reports)

###  Monitoring + Ops
- Includes **Databricks widgets** to:
  - clear previous run outputs
  - stop all active streams
  - optionally optimize tables
- Provides stream monitoring to validate active jobs and state

---

## Tech Stack

- **Databricks**
- **Python**
- **Apache Spark (Structured Streaming)**
- **Delta Lake**
- (Optional / extension-ready): MLflow metrics logging

---

## Repository Structure (expected)

This notebook calls an `includes` notebook using:

```python
%run ./includes/includes

## Project Context
This project was initially inspired by academic coursework. The implementation, experimentation, evaluation, and documentation were independently developed and extended beyond the original assignment scope.
