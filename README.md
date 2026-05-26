# 🧹 Data Cleaning & Analysis — Retail Sales Pipeline

A hands-on data cleaning and exploratory analysis project using Python and Pandas. Raw, messy retail data split across multiple tables was engineered, integrated, and analysed to surface core business insights.

---

## Project Overview

Real-world data is rarely clean. This project simulates the full data analyst workflow — from identifying quality issues in raw data all the way to generating business-level insights and visualizations.

* **Dataset:** Multi-table retail dataset split across 3 CSV files — Customers, Orders, and Transactions
* **Tools:** Python, Pandas, Matplotlib, NumPy
* **Core File:** `notebooks/sales_pipeline_analysis.ipynb`

---

## What Was Done

### 1. Data Cleaning
* Detected and resolved **duplicate records** across all 3 tables using `groupby` and a custom `first_valid()` aggregation function.
* Handled **missing values** strategically — filling non-recoverable fields (emails, phone numbers, city) with meaningful defaults rather than dropping rows.
* Standardised **inconsistent country name formats** (e.g., `"United States"`, `"U.S.A."`, `"usa"`, `"US"` ➔ `"USA"`) using a mapping dictionary.

### 2. Data Integration
* Merged all 3 cleaned tables into a single unified dataset using `customer_id` as the join key.
* Renamed conflicting columns (e.g., `purchase_amount` ➔ `transaction_amount`) to preserve data lineage.

### 3. Business Analysis
* **Total Revenue:** Sum of all order amounts.
* **Average Order & Transaction Value:** Mean spend per order and transaction.
* **Top 5 Customers by Spend:** Highest revenue-generating customers.
* **Revenue by Country & City:** Geographic breakdown of sales.
* **Monthly & Yearly Revenue Trends:** Time-series analysis using the `dt` accessor.
* **Shipping Time Analysis:** Average, fastest, and slowest delivery times.
* **Negative Ship Days:** Flagged as data quality issues — not silently dropped.

### 4. Visualisation
Built a **2×2 Matplotlib dashboard** covering:
* Top 5 customers by revenue (horizontal bar)
* Revenue by country (bar chart)
* Monthly revenue trend (line chart)
* Shipping days distribution (bar chart)

---

## 📂 Project Structure

```text
├── data/
│   └── raw/                           # Raw CSV datasets (customers, transactions, orders)
├── notebooks/
│   └── sales_pipeline_analysis.ipynb  # Main production analysis notebook
├── reports/
│   └── figures/                       # Saved dashboard visualizations
├── LICENSE
└── README.md
