# 🧹 SQL Data Preparation – Finance Dashboard

This document explains **how SQL was used to clean, standardize, and prepare finance data**
before loading it into Power BI for analysis.

The objective was to ensure the data was **accurate, consistent, and ready for financial reporting**.

---

## 📌 Data Used
- Sales data
- Expenses data
- Budget data

Each dataset was cleaned separately and aligned at a **monthly level** for P&L and Budget vs Actual analysis.

---

## 🔹 Step 1: Date Cleaning & Monthly Alignment
- Converted all date columns into proper DATE format
- Created a **MonthStart** column (first day of the month)
- Ensured all datasets follow the same monthly timeline

**Why:**  
Finance reporting (P&L, Budget vs Actual) is done at a **monthly level**, not daily.

---

## 🔹 Step 2: Cleaning Text Columns
- Removed extra spaces using trimming
- Standardized text using consistent casing
  - Region names
  - Product names
  - Departments
  - Categories

**Why:**  
Prevents duplicate values like “UAE”, “uae”, “ UAE ” appearing as separate entries in reports.

---

## 🔹 Step 3: Handling Missing & Invalid Data
- Removed rows with missing dates
- Removed rows with missing or invalid numeric values
- Ensured revenue, cost, and expense values are positive

**Why:**  
Missing or incorrect values can break financial calculations and distort totals.

---

## 🔹 Step 4: Revenue & Cost Validation
- Revalidated revenue using:
  - Units × Unit Price
- Revalidated COGS using:
  - Units × Unit Cost
- Compared calculated values with stored values

**Why:**  
Ensures trust in financial numbers before reporting.

---

## 🔹 Step 5: Expense Data Preparation
- Cleaned expense dates and aligned them to MonthStart
- Standardized department and category names
- Filtered out invalid or zero-value expenses

**Why:**  
Required for accurate **Operating Expense (Opex)** and Net Profit analysis.

---

## 🔹 Step 6: Budget Data Preparation
- Ensured budget data exists at **monthly level**
- Cleaned and validated budget revenue and budget expense values

**Why:**  
Budget data must align exactly with actuals for variance analysis.

---

## 🔹 Step 7: Monthly Aggregation
- Aggregated sales data to monthly totals
- Aggregated expenses to monthly totals
- Prepared clean monthly datasets for Power BI

**Why:**  
Improves performance and matches real-world finance reporting standards.

---

## ✅ Final Outcome
- Clean, standardized finance datasets
- Consistent monthly structure across Sales, Expenses, and Budget
- Reliable input for Power BI modeling and DAX calculations
- Accurate P&L and Budget vs Actual reporting

This SQL preparation step ensured the dashboard outputs were **business-ready, reliable, and CFO-safe**.

---

👩‍💼 **Author:**  
**Ambika Reddy**

