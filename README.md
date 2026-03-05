# Automobile & Clothing Sales Performance Analytics
## End-to-End Medallion Architecture (SQL Server & Power BI)

[![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)](https://www.microsoft.com/en-us/sql-server)
[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=power-bi&logoColor=black)](https://powerbi.microsoft.com/)

### 📊 Project Overview
This repository demonstrates a full-cycle Data Engineering and Business Intelligence solution. It transforms raw, siloed sales data into an interactive, multi-metric dashboard using the **Medallion Architecture**. The project provides stakeholders with real-time insights into Sales, Profit, and Customer behavior across global regions.

---

### 🏗️ Data Architecture: The Medallion Approach
The data is processed through three distinct layers within SQL Server to ensure quality and performance:

1.  **Bronze (Raw):** Initial ingestion of source data (Sales, Products, Customers, Geography) with minimal changes.
2.  **Silver (Cleansed):** Data deduplication, handling null values, and enforcing schema consistency.
3.  **Gold (Curated):** Final dimension and fact tables (Star Schema) optimized for Power BI consumption, including aggregated sales metrics.

---

### 🚀 Key Analytics Features
The Power BI dashboard was engineered for high interactivity and "Latest Year" focus:

* **Dynamic Metric Switching:** Utilizes **Field Parameters** allowing users to toggle the entire report between Sales, Profit, Orders, and Customers with a single click.
* **Time-Intelligence DAX:** Custom measures implemented to automatically lock visuals to the **Latest Complete Year (2014)** while maintaining YoY (Year-over-Year) growth context.
* **Dynamic Titling:** Context-aware headers that update based on the selected metric and filtered time frame.
* **Responsive X-Axis:** Engineered to "snap" to monthly trends for the selected year, removing historical noise.

---

### 📁 Repository Structure
* `SQL_Scripts/`
    * `Bronze_Layer/`: DDL for raw ingestion.
    * `Silver_Layer/`: Transformation and cleaning scripts.
    * `Gold_Layer/`: Final Fact and Dimension view definitions.
* `PowerBI_Report/`: `.pbix` file containing the semantic model and dynamic dashboard.
* `Data/`: Sample datasets used for the initial load.

---

### 💡 DAX Highlights: Dynamic Metric Parameter
The core of the dashboard's flexibility is the `Select Metric` field parameter:

```dax
Select Metric = {
    ("Total Sales", NAMEOF([Sales (Latest Year)]), 0),
    ("Total Profit", NAMEOF([Profit (Latest Year)]), 1),
    ("Total Orders", NAMEOF([Orders (Latest Year)]), 2),
    ("Total Customers", NAMEOF([Customers (Latest Year)]), 3)
}
```
## 🛠 Tech Stack
* **Database Engine:** Microsoft SQL Server
* **Language:** Advanced T-SQL (CTEs, Window Functions, DDL/DML)
* **Architecture Pattern:** Medallion (Data Lakehouse style)
* **Modeling:** Dimensional Modeling (Star Schema)
* **Data Analytics tool:** Power bi

## 🤝 Credits
Special thanks to **Baraa** for the detailed walkthrough and for sharing these data engineering best practices.
* **YouTube Channel:** [Data with Baraa](https://www.youtube.com/@DataWithBaraa)
* **Video Link:** [https://youtu.be/SSKVgrwhzus?si=S_Z996sWs94jZSZL](https://youtu.be/SSKVgrwhzus?si=S_Z996sWs94jZSZL)

---
