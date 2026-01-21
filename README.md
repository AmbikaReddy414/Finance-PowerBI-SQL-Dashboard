# 📊 Finance Performance Dashboard (SQL + Power BI)

An end-to-end **Finance Analytics project** built using **SQL and Power BI**, focused on transforming raw financial data into **CFO-ready insights** through clean modeling, P&L reporting, and Budget vs Actual analysis.

---

## 📌 Table of Contents
1. 📖 Project Overview  
2. 🧰 Tools & Skills Used  
3. 🗂️ Repository Structure  
4. 🔄 Data Preparation (SQL)  
5. 📊 Data Modeling & Power BI  
6. 📈 Dashboard Pages Explained  
7. 💡 Key Business Insights  
8. ✅ Results & Outcomes  
9. 👩‍💼 Author  

---

## 📖 Project Overview
This project demonstrates how finance data can be:
- Cleaned using **SQL**
- Modeled using **best-practice star schema**
- Analyzed using **DAX**
- Presented through **executive-level dashboards**

The goal is not just visualization, but **business decision support**.

---

## 🧰 Tools & Skills Used
- **SQL**  
  - SELECT, JOINs  
  - WHERE filters  
  - CASE logic  
  - Date functions  
  - Aggregations & GROUP BY  
  - Data validation  

- **Power BI**
  - Data modeling
  - DAX measures
  - Executive dashboard design

- **Finance Concepts**
  - Profit & Loss (P&L)
  - FP&A
  - Budget vs Actual
  - Variance Analysis
  - Margin Analysis

---

## 🗂️ Repository Structure

Finance-PowerBI-SQL-Dashboard
│
├── README.md
├── data
│ ├── Sales_100rows.csv
│ ├── Expenses_100rows.csv
│ └── Budget_24months.csv
│
├── powerbi-dashboard
│ └── Finance_Dashboard.pbix
│
└── screenshots
├── executive_summary.png
├── pnl.png
└── variance_waterfall.png


---

## 🔄 Data Preparation (SQL)
Raw sales, expense, and budget data were cleaned using **SQL** before loading into Power BI.

### Key SQL cleaning steps:
- Standardized date formats
- Created monthly time buckets
- Cleaned inconsistent region and product names
- Handled missing and invalid values
- Validated revenue, cost, and expense fields

This ensured the data was **analysis-ready** before visualization.

---

## 📊 Data Modeling & Power BI
Inside Power BI:
- Built a **star schema** with a centralized Calendar table
- Connected Sales, Expenses, and Budget to the Calendar
- Created DAX measures for:
  - Revenue
  - COGS
  - Gross Profit
  - Operating Expenses
  - Net Profit
  - Margins
  - Budget Variance

This structure enables **accurate time-based and financial analysis**.

---

## 📈 Dashboard Pages Explained

### 🟦 Page 1: Executive Summary
Purpose: **Quick business health check for leadership**
- Total Revenue
- Total Expenses (Opex)
- Net Profit
- Net Margin %
- Revenue trend over time
- Budget vs Actual comparison
- Revenue by Region

---

### 🟦 Page 2: Profit & Loss (P&L)
Purpose: **Detailed financial performance view**
- Revenue
- COGS
- Gross Profit
- Operating Expenses
- Net Profit
Displayed monthly and as totals for clear interpretation.

---

### 🟦 Page 3: Variance Analysis
Purpose: **Explain performance gaps**
- Waterfall chart showing monthly revenue variance vs budget
- Highlights cumulative impact of underperformance
- Supports corrective decision-making

---

## 💡 Key Business Insights
- 📈 Total Revenue of approximately **1.05M**
- 💰 Healthy **~57% gross margin**
- ⚠️ High operating expenses reduce profitability
- 📉 Net margin remains low at **~3%**
- ❌ Actual revenue underperformed budget every month
- 🌍 UAE and Qatar are the strongest revenue contributors

---

## ✅ Results & Outcomes
✔ Demonstrated end-to-end finance analytics workflow  
✔ Showed ability to clean data using SQL  
✔ Built CFO-level dashboards in Power BI  
✔ Translated numbers into clear business insights  
✔ Applied real-world FP&A concepts  

This project reflects **practical, real finance analysis**.

---

## 👩‍💼 Author
**Ambika Reddy**  

Finance & Data Analytics Enthusiast  
Skilled in SQL, Power BI, and Financial Modeling  

---

⭐ If you found this project useful, feel free to explore, share feedback, or connect!
