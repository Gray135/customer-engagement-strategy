# How to Read this Repo
- **Start here:** Scroll to the [Dashboard Preview](#dashboard-preview) to see the Power BI visuals.
- **[Excel prototype](excel/):** Early exploration of customer engagement patterns and the “Next Best Action” framework, illustrated through screenshots.
- **[SQL views](sql/):** Scalable data preparation layer for BI, built to mirror Excel logic and feed Power BI.
- **[Access the Dashboard](dashboard/customer_engagement_dashboard.pbix):** click the file in GitHub, then click "Raw" to download
- **Quick skim:** This README explains the business goal, visuals, and insights.

---
## 🧭 1-Minute Summary
Built a full-cycle **Customer Success Operations (CS Ops)** model using **Excel, SQL, and Power BI** to simulate how teams track engagement, identify at-risk customers, and plan retention outreach.  
The dashboard combines CLV tiers, satisfaction scores, and escalation risk to show where attention is needed most — like a simplified Gainsight or Salesforce CS view.  
This project highlights practical skills in **SQL view design, Power BI data modeling, DAX measures,** and turning CX data into business insights.

---

## Table of Contents
- [Dashboard Preview](#dashboard-preview)
  - [Customer Summary Dashboard](#1-customer-summary-dashboard)
  - [Demographics & Retention Behavior](#2-demographics--retention-behavior)
  - [Engagement & Escalation Risk](#3-engagement--escalation-risk)
  - [Key Insights & Next Steps](#4-key-insights--next-steps)
- [Business Objective](#business-objective)
- [Key Insights](#key-insights)
- [Data Source](#data-source)
- [Data Preparation and Logic](#data-preparation-and-logic)
- [Power BI Data Model](#power-bi-data-model)
- [Real-World Role Alignment](#real-world-role-alignment)
- [Next Steps](#next-steps)
- [Folder Structure](#folder-structure)
- [Reflection](#reflection)
- [Contact](#contact)
- [Disclaimer](#disclaimer)

---

## Dashboard Preview

The dashboard connects Excel logic, SQL structuring, and Power BI visuals to simulate how a CS Ops / retention team might prioritize outreach.

It highlights how CLV, engagement score, satisfaction score, and escalation risk show up across different customer segments.

### Key Metrics

| **Metric**                    | **Value / Description**                          |
|------------------------------|--------------------------------------------------|
| Total Customers              | 4,327                                            |
| Premium Members              | ~19% of total base                               |
| Avg CLV                      | $592.85                                          |
| Avg Satisfaction Score       | 6.63 / 10                                        |
| Repeat Customer Rate         | 84%                                              |
| Top Segment by Volume        | $0–2k CLV (95.7% of all customers)               |
| Avg Income Index             | ~1.89 (skews mid-income / not luxury)            |

> These metrics come from simulated customer data and are used to model retention strategy, not to report on any real business.

---

### 1. Customer Summary Dashboard
![Customer Summary Dashboard](images/Customer_Summary_Dashboard.png)


**Focus:** High-level KPIs  
**Highlights:** Total customers, premium share, average CLV, and satisfaction.  
Also includes premium membership by tenure group, engagement by satisfaction band, and CLV tier distribution.  

**Use Case:**  
Gives leaders a quick view of the customer base — who they are, how engaged they are, and where most revenue comes from.

---

### 2. Demographics & Retention Behavior
![Customer Demographics and Retention](images/Demographic_and_Retention.png)

**Focus:** Segment Behavior  
**Highlights:** Repeat vs new mix, CLV by income level, and customer count by country and gender.  
Includes a summary table showing CLV buckets, engagement averages, repeat %, and satisfaction scores.  

**Use Case:**  
Identifies which segments are most loyal, which drive value, and where satisfaction doesn’t align with spend.

---

### 3. Engagement & Escalation Risk
![Engagement and Risk](images/Engagement_and_Risk.png)
**Focus:** Customer Health & Risk  
**Highlights:** Engagement and satisfaction by CLV bucket and channel (email, mobile, social).  
Shows escalation risk distribution across customer tiers.  

**Use Case:**  
Pinpoints where high-value customers are disengaged or at risk — guiding escalation and outreach priorities.


---

### 4. Key Insights & Next Steps
![Insights and Actions](images/Insights_and_Actions.png)
**Focus:** Strategy & Next Steps  
**Highlights:** Summarizes key findings (e.g., 96% of base in low CLV) and connects engagement, satisfaction, and CLV to actionable next steps.  

**Use Case:**  
Functions like an executive slide — concise takeaways and recommendations for retention and quarterly planning.

---

## Business Objective

Customer Success and Operations teams need to know:
- Who’s most at risk of churning?
- What’s driving engagement and satisfaction?
- Where should outreach and resources go first?

This project simulates that workflow using structured logic across **Excel → SQL → Power BI**, mirroring how CS Ops teams use platforms like Gainsight or Salesforce to manage account health and retention.

**Goal:**  
Create a full-cycle model that:
1. Flags at-risk customers  
2. Segments them by CLV, engagement, and satisfaction  
3. Recommends a data-driven “next best action” for retention and outreach  

The result is a practical, BI-ready framework that blends Excel business logic with scalable SQL views and Power BI visuals — the kind of workflow a real CS Ops or VoC Analyst would use to prioritize high-impact accounts.

---

## Key Insights

| **Insight** | **What It Means** |
|--------------|------------------|
| **96% of customers** fall in the low-CLV ($0–2k) range | The retention backbone — focus here for scalable impact |
| **High-CLV customers** show **lower engagement** | Warning sign for targeted reactivation campaigns |
| **Repeat rate (84%)** | Indicates strong loyalty base to maintain and expand |
| **Income Index (~1.9)** | Spending skews mid-tier, not luxury — outreach tone matters |
| **Channel engagement varies** | Different segments prefer email, mobile, or social — personalize contact strategy |

These insights connect directly to the dashboard visuals, where each page highlights how engagement, satisfaction, and CLV interact to shape retention priorities.

---

## Data Source


All data in this project is **simulated** and designed to reflect what a real Customer Success or CX Analytics team might work with.

The dataset structure mirrors typical operational fields used for retention and engagement analysis:

- Customer demographics (gender, income level, country, tenure group)  
- Customer Lifetime Value (CLV) and total order value  
- Engagement and satisfaction scores  
- Premium membership and repeat status  
- Escalation risk level and support interaction history  
- Channel engagement (email, mobile, social)

No real customer information is used — this dataset is for **demonstration and portfolio purposes only.**

---

## Data Preparation and Logic

### Excel (prototype stage)

Started in Excel (`Data for Updated Project.xlsx`) to shape the base dataset before scaling in SQL and Power BI.

- Combined core attributes (ID, tenure, income, premium status, repeat flag, etc.)
- Added calculated fields for satisfaction, engagement, and escalation risk
- Grouped customers into CLV tiers ($0–2k, $2k–5k, $5k–20k, $20k+)
- Created quick filters like premium member, repeat customer, and negative CLV

This file served as a prototype — a quick way to clean data, test segmentation ideas, and validate logic before moving everything into SQL for automation.

### SQL (scaling the logic)

After validating the cleaned dataset in Excel, I rebuilt the logic in SQL to make it scalable and BI-ready.

**Key views:**
- `vw_core_profile` – Customer attributes such as ID, registration date, tenure, demographics, income, and membership status  
- `vw_customer_value` – Purchasing behavior including total purchases, average order value, lifetime value, CLV bucket, and return flags  
- `vw_customer_satisfaction` – Experience metrics like average satisfaction score and escalation risk  
- `vw_engagement_for_bi` – Consolidated, BI-ready view combining CLV, engagement, satisfaction, and risk indicators

**Highlights:**
- Implemented null handling and default values to prevent customer records from dropping out of analysis  
- Validated SQL outputs against the Excel prototype to confirm row counts and data consistency before loading into Power BI

### Power BI Data Model

With the SQL views finalized, the data was modeled in **Power BI** using a clear, scalable star schema designed for accuracy and easy maintenance.

**Model Overview**
- **Fact Tables:**  
  `F_public_customer_value`, `F_public_customer_engagement`, `F_public_customer_satisfaction`, `F_public_core_profile`  
- **Dimension Table:**  
  `DimCustomer` — central customer key controlling all relationships and filters  
- **Measures Table:**  
  Dedicated layer for all DAX calculations to keep metrics standardized across reports  

**Core DAX Measures**
- Average Customer Lifetime Value (CLV)  
- Average Engagement Score  
- Average Satisfaction Score  
- % Repeat Customers  
- % Premium Members  
- Escalation Risk by CLV Tier and Engagement Level  

**Dashboard Pages**
1. **Customer Summary** – high-level KPIs and engagement by satisfaction  
2. **Demographics & Retention** – repeat rates, CLV distribution, and customer mix  
3. **Engagement & Escalation Risk** – engagement vs. satisfaction, risk by CLV tier  
4. **Insights & Actions** – key findings and strategic recommendations  

This Power BI model translates the Excel and SQL logic into an interactive, executive-level view of customer health and retention risk — similar to what a CS Ops or CX team would use in Gainsight or Salesforce.

---

## Real World Role Alignment

This project reflects the kind of work done by:
- **Customer Success Operations (CS Ops) Analysts**
- **Customer Experience / Voice of Customer Analysts**
- **Business Analysts focused on Retention or Loyalty**
- **Support Operations Analysts** monitoring escalation and account health

**Skills demonstrated:**
- Data cleaning and segmentation in Excel  
- Translating manual logic into scalable SQL views  
- Power BI data modeling with DAX for real-time metrics  
- Turning operational data into actionable insights for customer retention  

This is the type of end-to-end workflow you’d discuss in an interview — moving from raw data to a repeatable model that helps answer:  
> “Which customers need attention first, and why?”

---
## Next Steps

The next iteration of this project will focus on making the model smarter and more automated.

- Add **trend tracking** to show how engagement and satisfaction change over time  
- Automate **data refresh** so Power BI always reflects the latest inputs  
- Introduce a **light churn-risk score** that blends satisfaction, engagement, escalation, and CLV  
- Tighten alignment between the **Excel prototype** and **SQL views** for better consistency  

**Vision:**  
Turn this into a lightweight **CS Ops workload routing tool** that answers a simple but powerful question:  
> “Which customers need attention right now, and why?”
---

## Folder Structure

- `excel/` – Early logic tables and “Next Best Action” mapping
- `sql-views/` – SQL views and validation queries
- `images/` – Power BI dashboard screenshots used in this README
- `dashboard/customer_engagement_strategy.pbix` – Power BI report file
- `README.md` – Project overview, visuals, insights, and next steps

(Adjust folder names if yours differ. The structure above is the intention.)

---

## Reflection

This project was about building something real — not just another demo dashboard.  
I started with messy customer data, cleaned and organized it in Excel, moved the logic into SQL so it could scale, and finished with a Power BI dashboard that helps make sense of customer health and engagement.  

It pushed me to connect the technical work to actual business value — figuring out what metrics matter, how to structure the data, and how to show it in a way that drives action.  

More than anything, it made me think like a CS Ops analyst: turning data into decisions, not just charts.

---

## Contact

**Aaron Zeug**  
Customer Experience & Reporting Specialist  
Focused on data analytics, retention strategy, and building repeatable CS Ops workflows.  
GitHub: https://github.com/Gray135  
LinkedIn: https://linkedin.com/in/aaronzeug

---

## Disclaimer

All data is simulated and for portfolio/demo purposes only.  
Nothing in this repo reflects real customer behavior from any employer.  
This work is meant to demonstrate workflow, logic design, and dashboard build-out.
