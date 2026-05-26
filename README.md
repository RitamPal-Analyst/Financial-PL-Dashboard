# 📊 Financial P&L Dashboard — FY2023
### Budget vs Actuals | Power BI · DAX · Power Query · Star Schema

---

## 📌 Project Overview

A 6 department organization relied on manual Excel consolidation to produce monthly financial reports — a time consuming and error prone process that delayed critical decision making.

This Power BI dashboard was built to solve that problem by giving leadership **real time visibility** into Budget vs Actual performance across all 6 cost categories for the full financial year 2023.

---

## 🎯 Business Questions This Dashboard Answers

- Are we over or under budget overall?
- Which cost categories are overspending?
- When during the year did overspending occur?
- Which month was the best and worst performer?
- How does each category perform month by month?

---

## 📂 Dashboard Pages

### Page 1 — Executive Summary
> *What happened?*
- KPI Cards — Total Budget, Actual, Variance % and Budget Utilisation
- Donut Chart — Share of total spend by category
- Variance Waterfall — % overspend or saving per category
- RAG Status Table — Red, Amber, Green performance per category
- Insight Text — Key findings highlighted for the CFO

### Page 2 — Trend Analysis
> *When did it happen?*
- Monthly Actual vs Budget line chart with shaded area
- KPI Cards — YTD Actual, Best Month, Worst Month, Avg Monthly Spend
- Monthly Categorical Variance heatmap — every category every month
- Insight Text — H1 vs H2 spending pattern analysis

### Page 3 — Category Deep Dive *(Drill Through)*
> *Where exactly is the problem?*
- Monthly line chart for selected category
- Budget Utilisation Gauge — green under budget, red over budget
- Month by month matrix with Variance % and RAG Status
- Dynamic Insight Text — automatically updates per selected category

---

## 🗂️ Data Model

Star schema with the following tables:

```
dim_Date ──────────────────┐
                           ▼
dim_Category ──────► fact_Finance (Fact Table)
```

| Table | Type | Description |
|---|---|---|
| fact_Finance | Fact | Unpivoted actuals and budget by month and category |
| dim_Date | Dimension | Calendar table with Month, Quarter, Year |
| dim_Category | Dimension | Cost category and group |

---

## 🧮 DAX Measures

| Measure | Description |
|---|---|
| `Total Amount` | Base SUM of all amounts |
| `Budget` | Filtered total for Budget type |
| `Actual` | Filtered total for Actual type |
| `Variance` | Actual minus Budget |
| `Variance %` | Variance divided by absolute Budget |
| `RAG Status` | Red Amber Green classification using SWITCH |
| `Budget Utilization` | Actual divided by Budget |
| `Best Month` | Month with lowest variance (most saved) |
| `Worst Month` | Month with highest variance (most overspent) |
| `YTD Actual` | Year to date cumulative actual spend |
| `Avg Monthly Actual` | Average actual spend per month using AVERAGEX |
| `Dynamic Insight` | Auto updating insight text per selected category |

---

## 🔍 Key Findings

- **Operational Costs** exceeded budget in 7 out of 12 months — the most consistently overspent category at 5.5% over annual budget
- **Maintenance Cost** spiked 95% over budget in March — spending £7,800 against a £4,000 budget — a one time anomaly requiring investigation
- **Training Cost** was the most efficient category — using only 79% of its annual budget and saving £18K
- Company **overspent in H1** but recovered strongly in **H2** — finishing the full year **£44K under budget overall**
- **Development Costs** represent **76.5% of total spend** making it the dominant cost category

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|---|---|
| Power BI Desktop | Dashboard development |
| Power Query (M) | Data transformation and unpivoting |
| DAX | Measures and calculated columns |
| Star Schema | Data modeling |
| Excel | Source data |

---

## ⚙️ Power Query Transformations

- Unpivoted 6 cost columns from wide to long format
- Renamed Attribute column to Cost Category
- Renamed Value column to Amount
- Fixed Month column data type to Date
- Added Month Name custom column

---

## 🚀 How to Use

1. Download the `.pbix` file from this repository
2. Open with **Power BI Desktop** (free download from Microsoft)
3. Explore all 3 pages using the navigation tabs
4. Right click any category bar on Page 1 → Drill Through → Category Deep Dive
5. Use the back button on Page 3 to return to Summary

---

## 📁 Repository Structure

```
📦 Financial-PL-Dashboard
 ┣ 📊 Financial_PL_Dashboard.pbix
 ┣ 📄 Financial_analysis_Data_Set.xlsx
 ┗ 📝 README.md
```

---

## 📸 Dashboard Preview

### Page 1 — Executive Summary
Screenshot 2026-05-26 030149.png

### Page 2 — Trend Analysis
Screenshot 2026-05-26 030244.png

### Page 3 — Category Deep Dive
Screenshot 2026-05-26 030320.png

---


## 👤 Author

**Ritam Pal**  
Aspiring Data Analyst | Power BI · SQL · Excel · Python  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](www.linkedin.com/in/palritam)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black)](your-github-url)

---

*Built as part of a data analytics portfolio project to demonstrate end to end Power BI development skills.*
