# Adventure_Works_ADF
Adventure Works Data Engineering Project
# End-to-End Azure Data Engineering Project

## Project Overview

This project demonstrates an **end-to-end Azure data engineering pipeline** designed to ingest, transform, model, and visualize data using modern Azure services.
The architecture follows industry best practices such as **medallion architecture (Bronze–Silver–Gold)**, **managed identity–based authentication**, and **analytics-ready modeling** for BI consumption.

The primary objective of this project is to showcase practical, production-aligned skills across **data ingestion, transformation, analytics, and visualization**.

---

## Architecture Overview

**Data Flow:**

1. **Azure Data Factory (ADF)**
   Ingests raw data from external sources and lands it into Azure Data Lake Storage Gen2.

2. **Azure Data Lake Storage Gen2 (ADLS)**
   Acts as the central data lake, organized into:

   * **Bronze**: Raw ingested data
   * **Silver**: Cleaned and standardized data
   * **Gold**: Aggregated, analytics-ready data

3. **Azure Databricks**
   Performs scalable data transformations using Spark notebooks, following the medallion architecture.

4. **Azure Synapse Analytics**
   Provides a SQL-based analytics layer using views over curated (Gold) data for downstream consumption.

5. **Power BI**
   Connects to Synapse for reporting, KPIs, and business insights.

---

## Tech Stack

* **Azure Data Factory**
* **Azure Data Lake Storage Gen2**
* **Azure Databricks (Spark)**
* **Azure Synapse Analytics**
* **Power BI**
* **GitHub (version control)**

---

## Repository Structure

```
├── adf/
│   ├── pipelines/
│   ├── datasets/
│   ├── linked_services/
│   └── triggers/
│
├── databricks/
│   ├── notebooks/
│   │   ├── 01_bronze_ingestion.ipynb
│   │   ├── 02_silver_transformation.ipynb
│   │   └── 03_gold_aggregation.ipynb
│   └── README.md
│
├── synapse/
│   ├── sql_scripts/
│   │   ├── gold_views.sql
│   │   └── analytics_queries.sql
│
├── powerbi/
│   └── dashboards/
│
└── README.md
```

---

## Data Engineering Workflow

### 1. Data Ingestion (ADF)

* Parameterized pipelines ingest source data
* Data is landed into **Bronze** containers in ADLS
* Pipelines are designed for reusability and scalability

### 2. Data Transformation (Databricks)

* Spark notebooks process data in stages:

  * Bronze → Silver (cleaning, schema enforcement)
  * Silver → Gold (business transformations, aggregations)

### 3. Analytics Layer (Synapse)

* External data is exposed via **SQL views**
* Gold layer is optimized for BI queries
* No data duplication; Synapse acts as a semantic layer

### 4. Visualization (Power BI)

* Power BI connects to Synapse SQL
* KPIs and dashboards are built for analysis and reporting

---

## Security & Authentication

* **No secrets or keys are stored in code**
* Authentication is handled using **Azure Managed Identity**
* Role-based access control (RBAC) is applied:

This approach aligns with **enterprise security best practices**.

---

## Purpose of This Project

This project was built to:

* Demonstrate real-world Azure data engineering workflows
* Reflect production-style architecture and security practices


