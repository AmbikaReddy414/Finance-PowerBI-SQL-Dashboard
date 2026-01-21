# 📐 DAX Measures & Time Intelligence – Finance Dashboard

This document explains all **DAX calculations** used in the Finance Dashboard,
including **Calendar (Time) table creation**, core financial measures,
Budget vs Actual analysis, and time-based metrics.

---

## 📌 Why DAX Was Used
DAX was used to:
- Create reusable financial calculations
- Ensure accurate Profit & Loss reporting
- Enable time intelligence (monthly trends, YoY, MoM)
- Support Budget vs Actual and variance analysis

---

## 🗓️ Calendar (Time) Table Creation

A dedicated Calendar table was created to ensure
accurate time-based filtering and finance reporting.

```DAX
Calendar =
ADDCOLUMNS (
    CALENDAR ( DATE(2024,1,1), DATE(2025,12,31) ),
    "Year", YEAR ( [Date] ),
    "Month Number", MONTH ( [Date] ),
    "Month", FORMAT ( [Date], "MMM" ),
    "MonthYear", FORMAT ( [Date], "MMM YYYY" ),
    "MonthStart", DATE ( YEAR([Date]), MONTH([Date]), 1 ),
    "Quarter", "Q" & FORMAT ( [Date], "Q" )
)```

Why this is important:

Central date table for Sales, Expenses, and Budget

Enables correct monthly, YoY, and MoM calculations

Required for finance-grade reporting
```

💰 Core Financial Measures

```DAX
Total Revenue = SUM(Sales[Revenue])

Total COGS = SUM(Sales[COGS])

Gross Profit = [Total Revenue] - [Total COGS]

Total Opex = SUM(Expenses[Amount])

Net Profit = [Gross Profit] - [Total Opex]

Gross Margin % = DIVIDE([Gross Profit], [Total Revenue])

Net Margin % = DIVIDE([Net Profit], [Total Revenue])
```

Budget vs Actual (monthly)


```DAX
Budget Revenue = SUM(Budget[BudgetRevenue])
Budget Opex = SUM(Budget[BudgetOpex])
Budget Net Profit = SUM(Budget[BudgetNetProfit])

Revenue Variance = [Total Revenue] - [Budget Revenue]
Revenue Variance % = DIVIDE([Revenue Variance], [Budget Revenue])

```
⏱️ Time Intelligence Measures

```DAX
Revenue LY =
CALCULATE([Total Revenue], SAMEPERIODLASTYEAR(Calendar[Date]))

Revenue YoY % =
DIVIDE([Total Revenue] - [Revenue LY], [Revenue LY])

Revenue PM =
CALCULATE([Total Revenue], DATEADD(Calendar[Date], -1, MONTH))

Revenue MoM % =
DIVIDE([Total Revenue] - [Revenue PM], [Revenue PM])


```

📄 P&L Matrix Support Measure

To display a structured P&L statement in a Matrix visual,
a layout table and a SWITCH-based measure were used.


```DAX
PL Layout =
DATATABLE (
    "PL Line", STRING,
    {
        { "Total Revenue" },
        { "Total COGS" },
        { "Gross Profit" },
        { "Total Opex" },
        { "Net Profit" }
    }
)

```

```DAX
PL Amount =
SWITCH (
    SELECTEDVALUE ( 'PL Layout'[PL Line] ),
    "Total Revenue", [Total Revenue],
    "Total COGS",    [Total COGS],
    "Gross Profit",  [Gross Profit],
    "Total Opex",    [Total Expenses],
    "Net Profit",    [Net Profit]
)


```
