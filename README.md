# 📊 Telecom Churn Analysis Dashboard (Power BI)

A comprehensive end-to-end telecom analytics project using Power BI and Excel that investigates customer churn, usage patterns, and billing inefficiencies. This case study transforms raw telecom data into actionable KPIs and visual dashboards ideal for business and product decision-making.

---

## 🧠 Problem Statement

Telecom companies struggle with identifying customer churn drivers and optimizing revenue per customer. With complex cost structures, incomplete visibility into usage behavior, and customer attrition, there's a pressing need for:

- Better visibility into usage and billing patterns
- Clear churn risk indicators
- Revenue segmentation and optimization insights

This project uses synthetic but realistic telecom usage data to explore all of the above.

---

## 📥 Raw Dataset Overview

**Source**: Adapted from open-source Kaggle telecom datasets (e.g., CDR and Churn data)

### Files Used:
- `cdr.csv`: Raw telecom call/SMS usage logs
- `churn.csv`: Churn labels, billing and account data

### Data Cleaning & Transformation:
- Used Excel to clean and engineer features
- Created a unified `customer_id` across both files using:
  ```excel
  ="C" & TEXT(ROW(A1), "0000")
  ```
- Removed nulls and zero-usage rows
- Created two clean summary sheets:
  - `cdr_summary` with total usage/costs
  - `churn_summary` with financials and churn labels
- Joined both summaries on `customer_id` in Excel to form a final dataset: `telecom_dashboard_dataset.csv`

---

## 📈 Business Questions & Related KPIs

| Business Question                                           | Related KPI(s)                       |
|-------------------------------------------------------------|--------------------------------------|
| What’s the current churn rate and revenue impact?          | Churn Rate, Revenue Lost to Churn    |
| Which customers are generating the most revenue?           | TotalCharges (Top 10)                |
| Are high-usage customers more likely to churn?             | Total Minutes vs. Churn              |
| How efficient is cost per call/minute across users?        | Cost per Call, Cost per Minute       |
| Are there high-cost, low-usage outliers?                   | Scatter: Usage vs. Charges           |
| What’s the behavior difference between churned vs active?  | Avg Call Duration, Msg/Call Ratio    |
| Who are good candidates for loyalty/cross-sell?            | High usage, low churn, high revenue  |

---

## 📊 Dashboard Sections & Visuals

### 🔹 Section 1: Churn Analysis
- KPI Cards: Churn Rate, Churned Customers, Revenue Lost
- Pie Chart: Churn Distribution (Yes vs No)
- Bar Chart: Avg. Monthly Charges by Churn Status
![image alt](https://github.com/saksham667806/Telecomchurnanalysis/blob/main/dashboard_page_1.png?raw=true)

### 🔹 Section 2: Usage Patterns
- KPI Cards: Total Minutes, Messages, Calls
- Line Chart: Monthly Charges vs. Usage Trend
![image alt](https://github.com/saksham667806/Telecomchurnanalysis/blob/b7ed6831a331d45ed9fa779a904fc73a06c3531d/dashboard_page_2.png)


### 🔹 Section 3: Revenue Analysis
- Bar Chart: Top 10 Customers by Revenue
- Slicers : With all the checks of churn and revenue.

![image alt](https://github.com/saksham667806/Telecomchurnanalysis/blob/b7ed6831a331d45ed9fa779a904fc73a06c3531d/dashboard_page_3.png)


### 🔹 Section 4: Risk & Opportunities
- Conditional Table: High Usage + Churn = Risk
- Slicers : With all the checks of churn and revenue.
![image alt](https://github.com/saksham667806/Telecomchurnanalysis/blob/b7ed6831a331d45ed9fa779a904fc73a06c3531d/dashboard_page_4.png)
---

## ✅ KPIs Calculated (via DAX in Power BI)

| KPI                    | Description                                   |
|------------------------|-----------------------------------------------|
| Churn Rate (%)         | % of churned users in dataset                |
| Revenue Lost           | Sum of TotalCharges where churn = TRUE       |
| Avg Monthly Charges    | AVERAGE of MonthlyCharges                    |
| Cost Per Call          | total_call_charges / total_call_units        |
| Cost Per Minute        | total_call_charges / total_call_minutes      |
| Avg Call Duration      | total_call_minutes / total_call_units        |
| Message-to-Call Ratio  | total_messages / total_call_units            |

---

## 📌 Key Insights

- **15% churn rate**, resulting in **20% revenue loss**
- **High-usage customers have better retention** — targeting them for loyalty rewards is key
- **10% of users have high cost per call despite low usage** — suggests billing plan mismatch
- **Top 5% of customers contribute 40% of total revenue** — ideal for upsell or VIP plans
- **Churned users tend to have shorter average call durations and fewer messages sent**
- **Cost per minute varies 4× across customers** — highlights pricing gaps and inefficiencies

---

## 📝 Executive Summary

**Problem Statement**  
Difficulty in tracking churn, revenue inefficiencies, and optimizing plans.

**Summary KPIs**  
- 15% churn rate  
- 20% revenue impact  
- Top 5% customers = 40% revenue

**3 Key Insights**  
- Churned users = low usage, short calls  
- High cost/low usage = misaligned plans  
- Retain top-value users via loyalty incentives

**Recommendations**  
- Introduce tiered billing plans  
 
- Audit pricing for efficiency




---

## 🗂 Files Included

| File Name                    | Purpose                                    |
|-----------------------------|--------------------------------------------|
| `telecomanalysis.pbit`      | Power BI dashboard template file           |
| `telecom_dashboard_dataset.csv` | Cleaned and joined dataset             |
| `tlecomanalysis.pdf`        | Dashboard screenshots                      |
| `README.md`                 | Project documentation                      |
| `images/`                   | Dashboard visuals (optional)               |

---

## 🚀 How to Use This Project

1. Download this repo or clone using GitHub
2. Open `telecomanalysis.pbit` in Power BI Desktop
3. Load `telecom_dashboard_dataset.csv` when prompted
4. Explore visuals and filters in Power BI
5. Use insights for case study, presentation, or interviews

---

## 💻 Technologies Used

- Power BI Desktop
- Excel (data cleaning, summary tables)
- Kaggle (raw dataset inspiration)

---

## 🎯 Target Audience

- Business Intelligence & Analytics recruiters
- Telecom product/marketing teams
- BI engineers and dashboard designers

---

