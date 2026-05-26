# 🧹 Data Cleaning & Analysis — Retail Sales Dataset

A hands-on data cleaning and exploratory analysis project using Python and Pandas. Raw, messy retail data across three tables was cleaned, merged, and analysed to surface business insights.

---

## Project Overview

Real-world data is rarely clean. This project simulates the full data analyst workflow — from identifying quality issues in raw data all the way to generating business-level insights and visualisations.

**Dataset:** Multi-table retail dataset with 3 sheets — Customers, Orders, Transactions  
**Tools:** Python, Pandas, Matplotlib  
**File:** `practice_data_cleanini.ipynb`

---

## What Was Done

### 1. Data Cleaning
- Detected and resolved **duplicate records** across all 3 tables using `groupby` and a custom `first_valid()` aggregation function
- Handled **missing values** strategically — filling non-recoverable fields (emails, phone numbers, city) with meaningful defaults rather than dropping rows
- Standardised **inconsistent country name formats** (e.g. `"United States"`, `"U.S.A."`, `"usa"`, `"US"` → `"USA"`) using a mapping dictionary

### 2. Data Integration
- Merged all 3 cleaned tables into a single unified dataset using `customer_id` as the join key
- Renamed conflicting columns (e.g. `purchase_amount` → `transaction_amount`) to preserve data lineage

### 3. Business Analysis
| Analysis                          | Description |
|---                                |---|
| Total Revenue                     | Sum of all order amounts |
| Average Order & Transaction Value | Mean spend per order and transaction |
| Top 5 Customers by Spend          | Highest revenue-generating customers |
| Revenue by Country & City         | Geographic breakdown of sales |
| Monthly & Yearly Revenue Trends   | Time-series analysis using `dt` accessor |
| Shipping Time Analysis            | Average, fastest, and slowest delivery times |
| Negative Ship Days                | Flagged as data quality issues — not silently dropped |

### 4. Visualisation
Built a **2×2 Matplotlib dashboard** covering:
- Top 5 customers by revenue (horizontal bar)
- Revenue by country (bar chart)
- Monthly revenue trend (line chart)
- Shipping days distribution (bar chart)

---

## 📂 Files

```
├── practice_data_cleanini.ipynb   # Main analysis notebook
├── practice dataset raw.xlsx      # Raw input data (3 sheets)
├── sales_analysis_charts.png      # Output dashboard
└── README.md
```

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/mirza-ishtiyaq/data-cleaning-analysis-pandas.git
   cd data-cleaning-analysis-pandas
   ```

2. Install dependencies:
   ```bash
   pip install pandas matplotlib openpyxl
   ```

3. Open the notebook:
   ```bash
   jupyter notebook practice_data_cleanini.ipynb
   ```

---

## 💡 Key Takeaways

- Data cleaning is about **decisions**, not just code — knowing when to fill, when to flag, and when to drop is the real skill
- Negative shipping days were **flagged** rather than silently removed, demonstrating data integrity awareness
- Merging multiple tables requires careful column management to avoid silent data loss

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-lightblue?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualisation-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
