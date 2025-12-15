# Telecom Customer Churn & Risk Dashboard (Power BI)

## Overview
This repository contains an interactive **Power BI dashboard** for analyzing **telecom customer churn and churn risk**. It summarizes churn KPIs, customer segments, service adoption, billing behavior, and support-ticket volume to help business teams prioritize **retention actions** and reduce revenue leakage.
Strengthened power bi skills through job simulation by developing an interactive dashboard identifying 7,043 at-risk customers (26.54% churn rate) using data cleaning, feature engineering, visualization techniques, enabling targeted retention strategies and reducing churn.

## What You Can See in the Dashboard (Visible Numbers)
The dashboard surfaces these headline metrics directly:
- **Total customers:** 7,043
- **Churn rate:** 26.54%
- **Customers at risk (Churn = Yes):** 1,869
- **Yearly charges (Total):** $16.06M
- **Tickets:** 2,955 Tech Tickets and 3,632 Admin Tickets

> These KPI cards provide an immediate estimate of churn scale and revenue exposure.

## Dashboards Included
### 1) Churn Dashboard
A management view focused on:
- Customers at risk and billing exposure (monthly/yearly charges)
- Support load signals (tech/admin tickets)
- Demographics distribution (gender, senior citizen, partner, dependents)
- Subscription time (tenure buckets)
- Billing behavior (payment method + paperless billing)
- Contract type (month-to-month vs 1-year vs 2-year)
- Services signed up for (phone, streaming, security, tech support, etc.)

### 2) Customer Risk Analysis
A diagnostic view for churn drivers:
- Churn by **internet service type**
- Customer distribution by internet service
- Monthly charges mix by internet service
- Churn by **contract type**, **tenure (months subscribed)**, and **payment method**
- Slicers for fast segmentation:
  - Risk of churn (Yes/No)
  - Internet service (DSL/Fiber optic/No)
  - Months subscribed (range)
  - Contract type

## Business Insights You Can Derive (Examples)
This dashboard is designed to help answer questions like:
- Which **contract types** are most associated with churn risk?
- Does churn concentrate in specific **internet service categories**?
- Are there billing behaviors (payment method / paperless billing) linked to higher churn?
- Do customers with more **support tickets** show higher churn risk?
- Which tenure groups (new vs long-term) require targeted retention programs?

## Business Impact (Why This Matters)
With **1,869 customers** already marked as churned/at-risk and **26.54% churn rate**, even a small improvement can create measurable value:
- If retention initiatives reduce churn by **2 percentage points** (26.54% → 24.54%), that is roughly:
  - **~141 customers retained** (7,043 × 0.02 ≈ 140.86)
- If average customer value (ARPU) is assumed at **$50/month**, the annualized impact is approximately:
  - **~$84.6K/year retained revenue** (141 × $50 × 12)

> Note: The revenue example uses an assumed ARPU. Replace with your company’s actual ARPU/LTV for a more accurate impact estimate.

## Statistical Summary (From Dashboard KPIs)
- **Churn count:** 1,869
- **Churn prevalence:** 26.54% (about 1 in 4 customers)
- **Revenue exposure:** $16.06M in yearly charges represented in the dataset
- **Support demand signal:** 6,587 total tickets (tech + admin), useful as a churn-risk proxy

## How to Use
1. Clone/download this repository.
2. Open the `.pbix` file using **Power BI Desktop**.
3. Update data source path if required.
4. Use slicers (risk, internet service, contract type, months subscribed) to drill into churn segments.
5. Export charts/KPIs for stakeholder reporting.

## Recommended Folder Structure
.
├── pbix/
│   └── Telecom-Churn-Risk-Dashboard.pbix
├── data/
│   └── telecom_churn.csv  (or .xlsx)
├── assets/
│   ├── churn-dashboard.png
│   └── customer-risk-analysis.png
└── README.md

## Example Measures (DAX)
> Adjust table/column names to match your model.

- Customers At Risk:
  - Customers At Risk = CALCULATE(COUNTROWS(Customer), Customer[Churn] = "Yes")

- Total Customers:
  - Total Customers = COUNTROWS(Customer)

- Churn Rate %:
  - Churn Rate % = DIVIDE([Customers At Risk], [Total Customers], 0)

- Total Monthly Charges:
  - Total Monthly Charges = SUM(Customer[MonthlyCharges])

- Total Yearly Charges:
  - Total Yearly Charges = SUM(Customer[TotalCharges])

## Enhancements (Optional Next Steps)
- Add a **Churn Driver** page with model-based feature importance (Python → Power BI integration).
- Create **retention cohorts** (tenure cohorts / contract cohorts).
- Add “Recommended Action” logic by segment (e.g., month-to-month + high charges + high tickets).

## License
MIT (or your preferred license)
