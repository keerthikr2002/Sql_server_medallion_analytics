# SQL Server Medallion Analytics: Retail Performance Engine

## 📌 Project Overview
This repository hosts a production-grade **Medallion Architecture** built entirely within **Microsoft SQL Server**. It transforms raw transactional data into a high-performance **Star Schema** designed to provide executive-level insights into business growth, customer behavior, and regional performance.

The pipeline is engineered to integrate disparate data sources—**ERP (Sales)** and **CRM (Customer)**—into a unified "Single Source of Truth."

---

## 🏗 Data Engineering Architecture (Medallion Framework)
The project follows the industry-standard Medallion architecture to ensure data integrity and lineage:

1.  **Bronze Layer (Raw):** Ingests source data "as-is" to preserve the original state for auditability.
2.  **Silver Layer (Cleansed):** Data is standardized using T-SQL. This includes type casting, handling `NULL` values, and removing duplicates using Window Functions like `ROW_NUMBER()`.
3.  **Gold Layer (Curated):** The final analytical layer organized into a **Star Schema**. It consists of optimized Fact and Dimension tables ready for high-speed querying and BI tool consumption.



---

## 📊 The Dataset: Global Retail Operations
This project performs data engineering on a global retail dataset spanning from **December 2010 to January 2014**. The data reflects a complex business environment with the following key characteristics:

* **Financial Scope:** Manages operations totaling **$28.4M in Revenue**, **$17.2M in Cost**, and a **$11.2M Profit** (39.42% margin).
* **Customer Profiles:** Analyzes **18,482 unique customers** categorized into segments: **VIP, Regular, and New**.
* **Product Catalog:** Tracks performance across three primary categories: **Bikes** (the core driver at $28.2M), **Accessories**, and **Clothing**.
* **Geographic Reach:** Supports reporting across six major markets: **United States, Australia, United Kingdom, Germany, France, and Canada**.

---

## 📁 Repository Structure

### 🛠️ [SQL Data Warehouse](./Sql_data_warehouse_project)
The engineering core of the project:
* **DDL Scripts:** Database schema definitions and relational constraints (Primary & Foreign Keys).
* **ETL Logic:** T-SQL scripts for the automated migration of data through the Bronze, Silver, and Gold layers.
* **Data Modeling:** Implementation of the Star Schema (Fact_Sales, Dim_Customers, Dim_Products).

### 📈 [Exploratory Data Analysis](./Exploratory_Data_Analysis_of_datawarehouse)
The analytical layer focused on business intelligence:
* **Trend Analysis:** SQL queries identifying peak periods, such as **December 2013 ($1.79M revenue)**.
* **Time Intelligence:** Logic built to support **Year-over-Year (YoY)** comparisons, allowing managers to see recent full-year performance against previous years.
* **Demographic Insights:** Analysis of revenue by **Age Group** (e.g., the 50+ demographic) and **Gender Distribution**.

---

## 🚀 Managerial & Executive Focus
While the warehouse contains historical data, the architecture is specifically optimized for **Executive Reporting**. It enables stakeholders to:
* Identify **Top 3 Products** by revenue (e.g., Road Bikes, Mountain Bikes, Touring Bikes).
* Compare **Current Year vs. Prior Year** growth metrics.
* Monitor **Customer Volume** and acquisition trends across global regions.

---

## 🛠 Tech Stack
* **Database Engine:** Microsoft SQL Server
* **Language:** Advanced T-SQL (CTEs, Window Functions, DDL/DML)
* **Architecture Pattern:** Medallion (Data Lakehouse style)
* **Modeling:** Dimensional Modeling (Star Schema)

## 🤝 Credits
Special thanks to **Baraa** for the detailed walkthrough and for sharing these data engineering best practices.
* **YouTube Channel:** [Data with Baraa](https://www.youtube.com/@DataWithBaraa)
* **Video Link:** [https://youtu.be/SSKVgrwhzus?si=S_Z996sWs94jZSZL](https://youtu.be/SSKVgrwhzus?si=S_Z996sWs94jZSZL)

---
