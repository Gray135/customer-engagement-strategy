# How to Read this Repo
- **Start here:** Scroll to the [Dashboard Preview](#dashboard-preview) to see the Power BI visuals.  
- **[Excel prototype](excel/):** Early exploration of customer engagement patterns and the “Next Best Action” logic.  
- **[SQL views](sql/):** Scalable data prep layer that mirrors Excel logic and feeds Power BI.
- **[Access the Dashboard](dashboard/customer_engagement_dashboard.pbix):** → Raw to download.
- **Quick skim:** This README walks through the business goal, visuals, and insights.

---

## 🧭 1-Minute Summary
This project builds a Customer Success Operations (CS Ops) model using Excel, SQL, and Power BI to show how teams track engagement, identify at-risk customers, and plan retention outreach.
The dashboard blends CLV tiers, satisfaction scores, and escalation risk — similar to what tools like Gainsight or Salesforce surface for account health.

It highlights practical, real-world analyst skills in:

SQL view design

Power BI data modeling

DAX metrics and data storytelling

---

## Table of Contents
- [Dashboard Preview](#dashboard-preview)
- [Business Objective](#business-objective)
- [Key Insights](#key-insights)
- [Data Source](#data-source)
- [Data Preparation and Logic](#data-preparation-and-logic)
- [Power BI Data Model](#power-bi-data-model)
- [Real-World Role Alignment](#real-world-role-alignment)
- [Next Steps](#next-steps)
- [Reflection](#reflection)
- [Contact](#contact)
- [Disclaimer](#disclaimer)

---

## Dashboard Preview

This dashboard connects Excel logic, SQL structure, and Power BI visuals to simulate how a CS Ops or retention team might prioritize outreach.

### Key Metrics

| **Metric** | **Value / Description** |
|-------------|--------------------------|
| Total Customers | 4,327 |
| Premium Members | ~19% of total base |
| Avg CLV | $592.85 |
| Avg Satisfaction Score | 6.63 / 10 |
| Repeat Customer Rate | 84% |
| Top Segment by Volume | $0–2k CLV (95.7% of all customers) |
| Avg Income Index | ~1.89 (skews mid-income, not luxury) |

> All metrics come from simulated data and model realistic retention scenarios.

---

### Report Pages

#### 1. Customer Summary Dashboard  
![Customer Summary Dashboard](images/Customer_Summary_Dashboard.png)  
High-level KPIs showing total customers, premium share, average CLV, and satisfaction — plus segmentation by tenure, satisfaction, and CLV tier.

---

#### 2. Demographics & Retention Behavior  
![Customer Demographics and Retention](images/Demographic_and_Retention.png)  
Shows repeat vs new mix, CLV by income level, and customer count by country and gender, plus a summary table with engagement and satisfaction averages.

---

#### 3. Engagement & Escalation Risk  
![Engagement and Risk](images/Engagement_and_Risk.png)  
Visualizes engagement and satisfaction by CLV tier and channel (email, mobile, social) and highlights escalation risk patterns.

---

#### 4. Key Insights & Next Steps  
![Insights and Actions](images/Insights_and_Actions.png)  
Summarizes overall findings and connects CLV, engagement, and satisfaction to specific retention actions.

---

## Business Objective

Customer Success and Operations teams need to answer::
- Who’s most at risk of churn?
- What’s driving engagement and satisfaction?
- Where should outreach and resources go first?

This model walks through that full workflow — Excel → SQL → Power BI — similar to how real CS Ops teams use Gainsight or Salesforce to monitor account health.

**Goal:**  
Create a full-cycle model that:
1. Flags at-risk customers  
2. Segment by CLV, engagement, and satisfaction
3. Recommend a data-driven “next best action”

---

## Key Insights

| **Insight** | **Meaning** |
|--------------|------------------|
| 96% of customers fall in the low-CLV ($0–2k) range | Core retention focus for scale |
| High-CLV customers show lower engagement | Target reactivation campaigns |
| Repeat rate (84%) | Strong loyalty base to sustain |
| Income Index (~1.9) | Mid-market position — tone matters |
| Channel engagement varies | Personalize contact strategy |


---

## Data Source

All data is simulated to mirror the structure used by CX and CS Ops teams:

- Demographics (gender, income, country, tenure)
- Customer Lifetime Value and purchase totals
- Engagement & satisfaction scores
- Premium status and repeat flags
- Escalation risk and support history
- Channel engagement (email, mobile, social)  

---

## Data Preparation and Logic

### Excel Prototype - Initial data cleaning and segmentation tests (Data for Updated Project.xlsx):
- Calculated engagement, satisfaction, and risk levels
- Grouped customers into CLV tiers ($0–2k, $2k–5k, $5k–20k, $20k+)  
- Created status flags for premium members and repeaters

### SQL Views - Scaled the Excel logic into reusable views for Power BI:
- `vw_core_profile` – Customer demographics and tenure
- `vw_customer_value` – Purchase behavior and CLV bucket
- `vw_customer_satisfaction` – Experience and risk metrics  
- `vw_engagement_for_bi` – Unified BI-ready view 

---

## Power BI Data Model - Star schema with clean relationships and standardized DAX measures:
- **Fact Tables:** `F_public_customer_value`, `F_public_customer_engagement`, `F_public_customer_satisfaction`, `F_public_core_profile`  
- **Dimension Table:** `DimCustomer` (central join key)
- **Measures Table:** Centralized DAX logic

Core DAX Examples:
- Avg CLV | Avg Engagement | Avg Satisfaction
- % Repeat Customers | % Premium Members
- Escalation Risk by CLV Tier + Engagement

---

## Real-World Role Alignment

This project mirrors work done by:
- Customer Success Operations Analysts  
- CX / Voice of Customer Analysts  
- Retention-focused Business Analysts  
- Support Operations Analysts  

**Skills Demonstrated**
- Data cleaning and segmentation (Excel)  
- SQL logic design and BI view creation  
- Power BI modeling and DAX  
- Translating metrics into retention strategy  

---

## Next Steps

- Add **trend tracking** to visualize engagement over time  
- Automate **Power BI refresh** for live updates
- Create a churn-risk score combining key factors
- Align Excel and SQL logic for stronger consistency

**Vision:**  
A lightweight CS Ops routing tool that answers →
“Which customers need attention right now — and why?”

---

## Reflection

This project was built to simulate real-world retention analytics used in CS Ops.  
Starting with messy data, I cleaned and organized it in Excel, rebuilt it in SQL for scale, and visualized it in Power BI for decision-making.  

It reinforced three key skills:
- Building structured logic that scales from Excel → SQL → Power BI  
- Designing DAX measures that turn data into insight, not just charts  
- Thinking like a CS Ops analyst — balancing data accuracy with business context  

---

## Contact

**Aaron Zeug**  
Customer Experience & Reporting Specialist  
Focused on data analytics, retention strategy, and building repeatable CS Ops workflows.  
[GitHub](https://github.com/Gray135) • [LinkedIn](https://linkedin.com/in/aaronzeug)

---

## Disclaimer

All data is simulated and for demonstration only.  
Nothing in this repo reflects real customer behavior from any employer.  
This project is for showcasing workflow, logic design, and dashboard development.
