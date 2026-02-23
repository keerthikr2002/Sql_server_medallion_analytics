## 📌 Project Overview
This repository implements a full-stack **Medallion Architecture** (Bronze, Silver, Gold) entirely within **Microsoft SQL Server**. It demonstrates the transition from raw data ingestion to a refined, query-ready Star Schema for advanced business analytics.

By leveraging T-SQL for the entire pipeline, this project ensures high data integrity, low latency, and a centralized source of truth for downstream BI reporting.

---

## 🏗 The Medallion Framework

### 🥉 Bronze Layer (Raw Ingestion)
* **Purpose:** Lands data exactly as it appears in the source.
* **Process:** Direct `INSERT` or `BULK LOAD` operations.
* **Feature:** Preserves history and allows for full data reprocessing without re-fetching from source.

### 🥈 Silver Layer (Cleansed & Standardized)
* **Purpose:** Data quality and consistency.
* **Process:** * Standardizing Date/Time formats.
    * Handling `NULL` values and data type casting.
    * Deduplication logic using `ROW_NUMBER()` or `DISTINCT`.
* **Outcome:** A reliable "Clean Room" for data analysts.

### 🥇 Gold Layer (Curated Business Insights)
* **Purpose:** Analytics-ready structures.
* **Process:** Aggregations and Star Schema modeling.
* **Structure:** Defined **Fact** tables (metrics) and **Dimension** tables (attributes) optimized for JOIN performance and reporting.

---

## 📁 Repository Structure

### 🛠️ [SQL Data Warehouse](./Sql_data_warehouse_project)
The engine of the project. Contains scripts for:
* **Schema Definition:** Creating the physical layers of the Medallion architecture.
* **Constraints:** Primary Keys, Foreign Keys, and Check constraints to ensure data health.

### 📈 [SQL Data Analysis](./Exploratory_Data_Analysis_of_datawarehouse)
The analytical layer. Instead of external tools, this folder contains:
* **Complex Analytical Queries:** Using Window Functions (`LEAD`, `LAG`, `RANK`) to find trends.
* **Business KPIs:** SQL scripts calculating Monthly Growth, Churn, or Revenue metrics directly from the Gold layer.
* **Views:** Virtual tables created for easy consumption by reporting tools.

---

## 🚀 How to Deploy

1.  **Clone the Repo:**
    ```bash
    git clone [https://github.com/keerthikr2002/Sql_server_medallion_analytics.git](https://github.com/keerthikr2002/Sql_server_medallion_analytics.git)
    ```
2.  **Initialize Environment:** Execute the `01_Setup_Schemas.sql` script to create the Bronze, Silver, and Gold environments.
3.  **Run ETL:** Execute the transformation scripts in order to migrate data from Bronze → Silver → Gold.
4.  **Query Insights:** Use the scripts in the `Data Analysis` folder to generate business reports.

---

## 🛠 Tech Stack
* **Database Engine:** Microsoft SQL Server
* **Language:** T-SQL (Advanced Window Functions, CTEs, DDL/DML)
* **Architecture Pattern:** Medallion (Data Lakehouse style)

---

## 🤝 Credits
Special thanks to **Baraa** for the detailed walkthrough and for sharing these data engineering best practices.
* **YouTube Channel:** [Data with Baraa](https://www.youtube.com/@DataWithBaraa)
* **Video Link:** [https://youtu.be/SSKVgrwhzus?si=S_Z996sWs94jZSZL](https://youtu.be/SSKVgrwhzus?si=S_Z996sWs94jZSZL)

---
