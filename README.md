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
   <img width="1186" height="637" alt="Image" src="https://github.com/user-attachments/assets/d22b0a2f-74fd-45eb-8a34-9cca13b30293" />
** Created Parameterized Datasets for source and sink.
   <img width="695" height="521" alt="Image" src="https://github.com/user-attachments/assets/8fd48568-0dbc-4851-b36c-a1de67f312f3" />
   <img width="833" height="210" alt="Image" src="https://github.com/user-attachments/assets/636b07dc-d8ec-495f-a3c9-c578ee77f6e6" />


3. **Azure Data Lake Storage Gen2 (ADLS)**
   Acts as the central data lake, organized into:
   <img width="905" height="192" alt="Image" src="https://github.com/user-attachments/assets/7ea90b1d-7645-493f-ae49-e9010ad35571" />

   * **Bronze**: Raw ingested data
   * **Silver**: Cleaned and standardized data
   * **Gold**: Aggregated, analytics-ready data

5. **Azure Databricks**
   Performs scalable data transformations using Spark notebooks, following the medallion architecture.
   ** Loading The Data
   <img width="1146" height="622" alt="Image" src="https://github.com/user-attachments/assets/e7dbecb3-05be-4f5d-b297-d33cdaff52aa" />
   ** Processing the Data[Transformations]
   <img width="1153" height="622" alt="Image" src="https://github.com/user-attachments/assets/05b427a7-4fb1-41c8-a827-d1bff0f863c7" />
   ** Did Sales Analysis
   <img width="1115" height="312" alt="Image" src="https://github.com/user-attachments/assets/475f3f12-57dd-4335-816c-3d64453a9f99" />


7. **Azure Synapse Analytics**
   Provides a SQL-based analytics layer using views over curated (Gold) data for downstream consumption.
  ** Created Views in SQL Script to serve data for visualization in power bi.
     <img width="1133" height="232" alt="Image" src="https://github.com/user-attachments/assets/d8a72fb6-8172-4733-98e5-53b5c86f8483" />
  ** Created Credential ,Ext_Data_Source,Ext_File_Format for databricks to have access in ADLS.
     ![Image](https://github.com/user-attachments/assets/f7d9c839-462c-42d3-9ad2-594f26efd125)

     ![Image](https://github.com/user-attachments/assets/fa673002-05e4-4da1-b573-8fd1dbe12008)

     ![Image](https://github.com/user-attachments/assets/dfe4dd55-b8ac-4878-86b1-8cea3c8e6a64)

9. **Power BI**
 **Connects to Synapse for reporting
     <img width="787" height="650" alt="Image" src="https://github.com/user-attachments/assets/c0578273-ebe5-4bc3-a100-627866de2e04" />

     <img width="847" height="407" alt="Image" src="https://github.com/user-attachments/assets/1479737a-543a-44ae-a1ae-0907fff75159" />
**Once connected Load the data and created the Dashboard which showcases Sales Analysis:
       <img width="1303" height="727" alt="Image" src="https://github.com/user-attachments/assets/abf6fa5b-54c4-4564-8ef4-376769b40550" />

---

## Tech Stack

* **Azure Data Factory**
* **Azure Data Lake Storage Gen2**
* **Azure Databricks (Spark)**
* **Azure Synapse Analytics**
* **Power BI**
* **GitHub (version control)**

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

---

## Purpose of This Project

This project was built to:

* Demonstrate real-world Azure data engineering workflows
* Reflect production-style architecture and security practices


