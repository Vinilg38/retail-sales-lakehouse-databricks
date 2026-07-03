# 🛒 Retail Sales Lakehouse using Databricks Lakeflow Jobs

An end-to-end Data Engineering project demonstrating the Medallion Architecture (Bronze → Silver → Gold) using **Databricks**, **Delta Lake**, **PySpark**, and **Lakeflow Jobs**.

The pipeline ingests retail sales data, performs incremental processing, schema validation, schema evolution, deduplication, late-arriving data handling, and produces analytics-ready business KPI tables.

---

# 📌 Project Overview

This project simulates a real-world retail sales pipeline where daily transaction files are ingested into a Lakehouse.

The pipeline demonstrates modern Data Engineering concepts including:

- Incremental Batch Processing
- Medallion Architecture
- Delta Lake MERGE operations
- Schema Validation
- Schema Evolution
- Deduplication
- Late Arriving Data Handling
- Lakeflow Job Parameters
- Business KPI Generation

---

# 🏗 Architecture

> **(Insert architecture diagram here)**

Example:

```
Landing CSV Files
        │
        ▼
Bronze Layer
(Raw Standardized Data)
        │
        ▼
Silver Layer
(Data Validation + MERGE +
Schema Evolution +
Deduplication +
Late Data Handling)
        │
        ▼
Gold Layer
(Business KPI Tables)
```

---

# ⚙ Technology Stack

| Technology | Purpose |
|------------|----------|
| Databricks | Data Engineering Platform |
| PySpark | Data Processing |
| Delta Lake | ACID Tables & MERGE |
| Lakeflow Jobs | Workflow Orchestration |
| Delta Tables | Storage Layer |
| SQL | Validation & Analytics |
| GitHub | Version Control |

---

# 📂 Project Structure

```
Retail-Sales-Lakehouse/

│
├── landing/
│   ├── base/
│   │      sales_base.csv
│   │
│   └── updates/
│          └── 2026-06-30/
│                update_1.csv
│                update_2.csv
│                update_3.csv
│
├── notebooks/
│   ├── Bronze_Ingestion.py
│   ├── Silver_Data_Validation_Upsert.py
│   └── Gold_Business_Analytics.py
│
├── images/
│   architecture.png
│   lakeflow_job.png
│   bronze_output.png
│   silver_output.png
│   gold_output.png
│
└── README.md
```

---

# 🚀 Workflow

## Bronze Layer

### Responsibilities

- Reads Initial Full Load
- Reads Daily Incremental Files
- Standardizes Data Types
- Validates Required Columns
- Adds Ingestion Metadata
- Writes Delta Bronze Tables

### Output Tables

- bronze_sales
- bronze_incremental

---

## Silver Layer

### Responsibilities

- Schema Validation
- Manual Schema Evolution
- Deduplication
- Late Arriving Data Detection
- Delta MERGE INTO
- Quarantine Invalid Records

### Output Tables

- silver_sales
- quarantine_schema
- quarantine_late

---

## Gold Layer

### Responsibilities

Generate analytics-ready business tables.

### Output Tables

#### gold_store_sales

- Total Sales
- Total Transactions
- Average Order Value
- Highest Sale
- Lowest Sale
- Unique Customers

---

#### gold_customer_sales

- Total Orders
- Total Spend
- Average Order Value
- Last Purchase Date
- Favorite Category
- High Value Customer Flag

---

#### gold_category_sales

- Category Sales
- Category Revenue
- Total Transactions
- Average Sale
- Unique Customers

---

# 🔄 Lakeflow Job

The project is orchestrated using Databricks Lakeflow Jobs.

Pipeline:

```
Bronze - Ingestion
        │
        ▼
Silver - Data Validation & Upsert
        │
        ▼
Gold - Business Analytics
```

All downstream tasks execute only after successful completion of upstream dependencies.

---

# ⚡ Job Parameters

| Parameter | Description |
|-----------|-------------|
| full_refresh | Run Full Load or Incremental Load |
| process_date | Incremental Folder Date |
| source_system | Source System Name |
| late_threshold_days | Late Arrival Threshold |
| minimum_sales | High Value Customer Threshold |

---

# 📊 Business KPIs

The Gold layer generates:

- Store Revenue
- Customer Spend
- Average Order Value
- Product Category Performance
- High Value Customers
- Purchase Trends

These tables are ready for reporting tools like:

- Power BI
- Tableau
- Databricks SQL Dashboards

---

# 🧩 Key Engineering Features

✅ Medallion Architecture

✅ Incremental Processing

✅ Delta MERGE INTO

✅ Window Function Deduplication

✅ Schema Validation

✅ Schema Evolution

✅ Late Arriving Data Handling

✅ Data Quarantine

✅ Lakeflow Job Parameters

✅ Business KPI Generation

---

# 📸 Screenshots

## Lakeflow Workflow

> *(Insert Lakeflow Job screenshot)*

---

## Bronze Output

> *(Insert Bronze notebook output)*

---

## Silver Output

> *(Insert Silver notebook output)*

---

## Gold Output

> *(Insert Gold notebook output)*

---

## Quarantine Tables

> *(Insert quarantine_schema and quarantine_late screenshots)*

---

# 💡 Production Considerations

In a production environment, the following enhancements would be implemented:

- Auto Loader for cloud-based incremental ingestion
- Structured Streaming for real-time processing
- Unity Catalog for centralized governance
- CI/CD using Databricks Asset Bundles
- Cluster Policies
- Monitoring & Alerting
- Data Quality Expectations
- Partitioning and Z-Ordering
- Secrets Management
- Cloud Object Storage (ADLS / S3 / GCS)

---

# 📈 Skills Demonstrated

- PySpark
- Delta Lake
- Databricks
- Lakeflow Jobs
- ETL Pipeline Design
- Medallion Architecture
- Data Validation
- Schema Evolution
- Data Deduplication
- Incremental Processing
- Data Engineering Best Practices

---

# 📬 Author

**Vinil Gupta**

B.Tech Computer Science Engineering

Databricks Certified Data Engineer Associate

GitHub: *(Add your GitHub profile)*

LinkedIn: *(Add your LinkedIn profile)*
