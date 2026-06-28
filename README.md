# 🚀 Modern SQL Data Warehouse & Analytics Platform

### End-to-End Data Engineering Project using SQL Server, ETL Pipelines, Medallion Architecture, Star Schema Modeling, and Advanced SQL Analytics

---

## 📖 Project Overview

This project demonstrates the complete lifecycle of designing and building a modern enterprise Data Warehouse using Microsoft SQL Server.

The solution follows the **Medallion Architecture (Bronze → Silver → Gold)** to transform raw ERP and CRM data into a clean, integrated, and business-ready analytical database. The warehouse is designed to support Business Intelligence, reporting, and advanced SQL analytics.

The project simulates a real-world Data Engineering workflow by covering data ingestion, ETL development, data cleansing, dimensional modeling, quality validation, and business reporting.

---

## ✨ Features

- Multi-source Data Integration (ERP & CRM)
- Automated ETL Pipelines using Stored Procedures
- Medallion Architecture Implementation
- Data Cleansing & Standardization
- Star Schema Data Modeling
- Business-ready Gold Layer
- Data Quality Validation
- Advanced SQL Analytics
- Customer & Product Reports
- Modular SQL Scripts
- Well-documented Project Structure

---

# 🛠️ Technology Stack

| Category | Technology |
|----------|------------|
| Database | Microsoft SQL Server |
| Query Language | T-SQL |
| ETL | SQL Stored Procedures |
| Data Architecture | Medallion Architecture |
| Data Modeling | Star Schema |
| Source Systems | ERP & CRM CSV Files |
| Database Tool | SQL Server Management Studio (SSMS) |
| Version Control | Git & GitHub |

---

# 🏗️ Data Architecture

This project follows the **Medallion Architecture**, a modern data engineering design pattern consisting of three layers.

```
               CSV Files
          (ERP + CRM Sources)
                   │
                   ▼
        ┌─────────────────────┐
        │   Bronze Layer      │
        │ Raw Data Ingestion  │
        └─────────────────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │   Silver Layer      │
        │ Data Cleaning       │
        │ Standardization     │
        │ Integration         │
        └─────────────────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │    Gold Layer       │
        │ Star Schema         │
        │ Business Views      │
        │ Analytics Ready     │
        └─────────────────────┘
                   │
                   ▼
          SQL Analytics & Reports
```

---

# 🥉 Bronze Layer

The Bronze Layer stores raw data exactly as received from the source systems.

### Responsibilities

- Import ERP CSV files
- Import CRM CSV files
- Preserve original data
- No transformations applied
- Serves as the source of truth

---

# 🥈 Silver Layer

The Silver Layer performs data cleaning and transformation.

### Responsibilities

- Remove duplicate records
- Handle missing values
- Standardize formats
- Clean invalid data
- Merge ERP and CRM datasets
- Improve data consistency

---

# 🥇 Gold Layer

The Gold Layer contains business-ready analytical data.

### Responsibilities

- Build Star Schema
- Create Fact Tables
- Create Dimension Tables
- Generate Business Views
- Optimize analytical queries
- Support reporting and dashboards

---

# ⭐ Data Model (Star Schema)

The Gold Layer follows a Star Schema to improve analytical performance.

```
                  +----------------------+
                  |    Dim Customer      |
                  +----------------------+
                           |
                           |
+----------------+   +----------------+   +----------------+
|  Dim Product   |---|   Fact Sales   |---|    Dim Date    |
+----------------+   +----------------+   +----------------+
                           |
                           |
                  +----------------------+
                  |   Dim Territory      |
                  +----------------------+
```

---

# ⚙️ ETL Pipeline

The ETL process is implemented using SQL Stored Procedures.

### Step 1

Load raw ERP and CRM CSV files into Bronze tables.

↓

### Step 2

Clean, standardize, validate, and integrate data in the Silver layer.

↓

### Step 3

Transform cleaned data into analytical Star Schema tables in the Gold layer.

↓

### Step 4

Execute quality validation scripts.

↓

### Step 5

Run analytics queries and generate business reports.

---

# 📊 Analytics Implemented

The project includes several analytical SQL reports, including:

- Database Exploration
- Dimension Exploration
- Date Range Analysis
- Measure Exploration
- Magnitude Analysis
- Ranking Analysis
- Time Series Analysis
- Cumulative Analysis
- Performance Analysis
- Customer Segmentation
- Part-to-Whole Analysis
- Customer Reports
- Product Reports

---

# 💼 Business Questions Answered

This warehouse helps answer important business questions such as:

- Who are the top-performing customers?
- Which products generate the highest revenue?
- Which products have declining sales?
- What are the monthly and yearly sales trends?
- Which customer segments contribute the most revenue?
- Which products perform best across different periods?
- What percentage of total sales comes from each product category?
- How has business performance changed over time?

---

# ✅ Data Quality Checks

Several validation checks are performed before data reaches the Gold layer.

- Duplicate Detection
- NULL Value Validation
- Primary Key Validation
- Foreign Key Validation
- Invalid Date Detection
- Data Completeness Checks
- Business Rule Validation

Quality scripts are available under:

```
tests/
├── quality_checks_silver.sql
└── quality_checks_gold.sql
```

---

# 📂 Repository Structure

```
sql-data-warehouse-project/
│
├── datasets/
│   ├── source_crm/
│   └── source_erp/
│
├── docs/
│   ├── Data Analytics Roadmap.png
│   ├── data_catalog.md
│   └── naming_conventions.md
│
├── scripts/
│
│   ├── analytics/
│   │   ├── 00_create_analytics_database.sql
│   │   ├── 01_database_exploration.sql
│   │   ├── 02_dimensions_exploration.sql
│   │   ├── 03_date_range_exploration.sql
│   │   ├── 04_measures_exploration.sql
│   │   ├── 05_magnitude_analysis.sql
│   │   ├── 06_ranking_analysis.sql
│   │   ├── 07_change_over_time_analysis.sql
│   │   ├── 08_cumulative_analysis.sql
│   │   ├── 09_performance_analysis.sql
│   │   ├── 10_data_segmentation.sql
│   │   ├── 11_part_to_whole_analysis.sql
│   │   ├── 12_report_customers.sql
│   │   └── 13_report_products.sql
│   │
│   ├── bronze/
│   │   ├── ddl_bronze.sql
│   │   └── proc_load_bronze.sql
│   │
│   ├── silver/
│   │   ├── ddl_silver.sql
│   │   └── proc_load_silver.sql
│   │
│   ├── gold/
│   │   └── ddl_gold.sql
│   │
│   └── init_database.sql
│
├── tests/
│   ├── quality_checks_gold.sql
│   └── quality_checks_silver.sql
│
├── LICENSE
└── README.md
```

---

# 🚀 Getting Started

## Prerequisites

- Microsoft SQL Server
- SQL Server Management Studio (SSMS)

---

## Installation

### Clone the repository

```bash
git clone https://github.com/yourusername/sql-data-warehouse-project.git
```

### Open SQL Server Management Studio

Connect to your SQL Server instance.

### Execute scripts in the following order

```
scripts/init_database.sql

scripts/bronze/ddl_bronze.sql

scripts/bronze/proc_load_bronze.sql

scripts/silver/ddl_silver.sql

scripts/silver/proc_load_silver.sql

scripts/gold/ddl_gold.sql
```

Finally, execute the analytics scripts under

```
scripts/analytics/
```

---

# 📈 Project Workflow

```
Raw CSV Files
        │
        ▼
Bronze Layer
        │
        ▼
Silver Layer
        │
        ▼
Gold Layer
        │
        ▼
Analytics Queries
        │
        ▼
Business Reports
        │
        ▼
Decision Making
```

---

# 🎯 Skills Demonstrated

This project showcases practical experience in:

- SQL Programming
- Data Engineering
- ETL Development
- Data Warehousing
- Medallion Architecture
- Star Schema Design
- Data Modeling
- Data Cleaning
- Data Validation
- Business Intelligence
- SQL Analytics
- Query Optimization
- Documentation
- Git & GitHub

---

# 📌 Future Enhancements

Possible improvements include:

- Incremental Data Loading
- Slowly Changing Dimensions (SCD Type 2)
- SQL Server Agent Scheduling
- Power BI Dashboard Integration
- Azure Data Factory Pipelines
- CI/CD Deployment
- Data Lineage Documentation
- Performance Monitoring
- Index Optimization

---

# 📷 Project Screenshots

You can add screenshots here to better showcase the project.

- Architecture Diagram
- ETL Pipeline
- Star Schema
- Bronze Tables
- Silver Tables
- Gold Tables
- Sample Analytics Queries
- SQL Query Results
- Database Explorer
- Data Quality Validation

---

# 📚 Learning Outcomes

Through this project, I gained practical experience in:

- Designing enterprise-scale Data Warehouses
- Building ETL pipelines using SQL Server
- Applying Medallion Architecture
- Implementing Star Schema Modeling
- Performing data quality validation
- Writing advanced analytical SQL queries
- Creating business-focused reports
- Organizing scalable SQL projects using best practices

---

# 📄 License

This project is licensed under the MIT License.

---

## ⭐ If you found this project helpful, consider giving it a Star on GitHub!
