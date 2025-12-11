# 🇦🇺 Australia Energy Market Analysis on Microsoft Fabric

![Status](https://img.shields.io/badge/Status-Data_Engineering_Complete-success)
![Status](https://img.shields.io/badge/Dashboard-Design_in_Progress-yellow)

## 📌 Project Overview
An end-to-end data engineering project analyzing the **South Australia (SA) energy market** using **Microsoft Fabric**. 
The project ingests raw energy and financial data into a Lakehouse, performs ETL using **PySpark**, and derives insights regarding the **"Duck Curve" phenomenon** and **economic correlations (FX rates)**.

## 🏗️ Architecture & Workflow
**`Raw Data (CSV/API)`** $\rightarrow$ **`OneLake`** $\rightarrow$ **`PySpark (ETL)`** $\rightarrow$ **`Delta Tables`** $\rightarrow$ **`Spark SQL`** $\rightarrow$ **`Power BI (Direct Lake)`**

1.  **Ingestion:** Loaded SA Energy data (CSV) and Yahoo Finance API data into OneLake.
2.  **Engineering:** Cleaned data and engineered features (`Hour`, `FX_Group`) using **PySpark**.
3.  **Storage:** Stored processed data as **Delta Tables** optimized for analytics.
4.  **Analysis:** Executed complex aggregations using **Spark SQL** to identify negative price trends.

## 🛠️ Tech Stack
* **Platform:** Microsoft Fabric
* **Storage:** OneLake (Lakehouse), Delta Lake
* **Processing:** Apache Spark (PySpark), Spark SQL
* **External Lib:** `yfinance` (Financial Data API)
* **Visualization:** Power BI (Direct Lake mode)

## 💡 Key Engineering Highlights
* **Workspace Management:** Resolved data visibility issues between personal and capacity-enabled workspaces.
* **Schema Evolution:** Handled Delta Table schema updates (`overwriteSchema=True`) to accommodate new derived features.
* **Performance:** Optimized data retrieval using Fabric's **Direct Lake** mode, eliminating the need for data duplication.

## 📊 Analytical Insights
* **The Duck Curve:** Validated a significant drop in Net Demand and **negative price occurrences** peaking between **10:00 AM - 2:00 PM** due to solar penetration.
* **FX Correlation:** Identified a correlation where **High AUD/USD exchange rates** ($\ge$ 0.64) align with higher average energy prices.

## 📂 Project Structure
```bash
├── 01_Lakehouse/               # Raw Data Samples (CSV)
├── 02_Notebooks/               # Source Code
│   ├── 01_ETL_energy_finance_merge.ipynb
│   └── 02_analysis_SQL_and_visual.ipynb
├── requirements.txt            # Python Dependencies
└── README.md                   # Project Documentation