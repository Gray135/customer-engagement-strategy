# How to Read this Repo
- **Start here:** Scroll to the [Dashboard Preview](#dashboard-preview) to see the Power BI visuals.  
- **[Excel prototype](excel/):** Early exploration of customer engagement patterns and the “Next Best Action” framework.  
- **[SQL views](sql/):** Scalable data preparation layer for BI, built to mirror Excel logic and feed Power BI.  
- **[Access the Dashboard](dashboard/customer_engagement_dashboard.pbix):** Click the file in GitHub, then select **“Raw”** to download.  
- **Quick skim:** This README explains the business goal, visuals, and insights.

---

## 🧭 1-Minute Summary
Built a full-cycle **Customer Success Operations (CS Ops)** model using **Excel, SQL, and Power BI** to simulate how teams track engagement, identify at-risk customers, and plan retention outreach.  
The dashboard combines CLV tiers, satisfaction scores, and escalation risk to show where attention is needed most — like a simplified Gainsight or Salesforce CS view.  
This project highlights practical skills in **SQL view design, Power BI data modeling, DAX measures,** and turning CX data into business insights.

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

The dashboard connects Excel logic, SQL structuring, and Power BI visuals to simulate how a CS Ops or retention team might prioritize outreach.  
It highlights how CLV, engagement, satisfaction, and escalation risk interact across customer segments.

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

> These metrics come from simulated customer data and are used to model retention strategy, not report on any real business.

---

### Report Pages

#### 1. Customer Summary Dashboard  
![Customer Summary Dashboard](images/Customer_Summary_Dashboard.png)  
High-level KPIs showing total customers, premium share, average CLV, and satisfaction.  
Also includes premium membership by tenure group, engagement by satisfaction band, and CLV tier distribution.

---

#### 2. Demographics & Retention Behavior  
![Customer Demographics and Retention](images/Demographic_and_Retention.png)  
Shows repeat vs. new mix, CLV by income level, and customer count by country and gender.  
Includes a summary table showing CLV buckets, engagement averages, repeat %, and satisfaction scores.

---

#### 3. Engagement & Escalation Risk  
![Engagement and Risk](images/Engagement_and_Risk.png)  
Displays engagement and satisfaction by CLV bucket and channel (email, mobile, social).  
Visualizes escalation risk distribution across customer tiers.

---

#### 4. Key Insights & Next Steps  
![Insights and Actions](images/Insights_and_Actions.png)  
Summarizes key findings (e.g., 96% of base in low CLV) and connects engagement, satisfaction, and CLV to actionable next steps — a concise, leadership-level view.

---

## Business Objective

Customer Success and Operations teams need to know:
- Who’s most at risk of churning?
- What’s driving engagement and satisfaction?
- Where should outreach and resources go first?

This project simulates that workflow using **Excel → SQL → Power BI**, mirroring how CS Ops teams use tools like Gainsight or Salesforce to manage account health and retention.

**Goal:**  
Create a full-cycle model that:
1. Flags at-risk customers  
2. Segments them by CLV, engagement, and satisfaction  
3. Recommends a data-driven “next best action” for retention and outreach  

The result is a BI-ready framework blending Excel business logic, scalable SQL views, and Power BI visuals — the same kind of workflow used by CS Ops or VoC Analysts to prioritize high-impact accounts.

---

## Key Insights

| **Insight** | **What It Means** |
|--------------|------------------|
| 96% of customers fall in the low-CLV ($0–2k) range | The retention backbone — focus here for scalable impact |
| High-CLV customers show lower engagement | Warning sign for targeted reactivation campaigns |
| Repeat rate (84%) | Indicates strong loyalty base to maintain and expand |
| Income Index (~1.9) | Spending skews mid-tier, not luxury — outreach tone matters |
| Channel engagement varies | Different segments prefer email, mobile, or social — personalize contact strategy |

These insights link directly to the dashboard visuals, showing how engagement, satisfaction, and CLV shape retention priorities.

---

## Data Source

All data is **simulated**, structured to reflect what a real CS Ops or CX Analytics team might manage.

- Customer demographics (gender, income, country, tenure)  
- Customer Lifetime Value (CLV) and total order value  
- Engagement and satisfaction scores  
- Premium membership and repeat status  
- Escalation risk and support interaction history  
- Channel engagement (email, mobile, social)  

No real customer information is used — this dataset is purely for demonstration and portfolio purposes.

---

## Data Preparation and Logic

### Excel (Prototype Stage)
Initial data cleaning and logic testing began in **Excel** (`Data for Updated Project.xlsx`).  
The goal was to validate segmentation and ensure fields aligned before scaling in SQL.

- Combined key fields (ID, tenure, income, premium, repeat flag, etc.)  
- Calculated satisfaction, engagement, and escalation risk  
- Grouped customers into CLV tiers ($0–2k, $2k–5k, $5k–20k, $20k+)  
- Added status flags for premium members, repeaters, and negative CLV  

This served as the proof-of-concept layer — a fast way to confirm the segmentation logic worked before automating it.

### SQL (Scaling the Logic)
Rebuilt the Excel logic into **SQL views** to make the data scalable and BI-ready.

**Key Views**
- `vw_core_profile` – Base attributes (ID, registration date, tenure, demographics, income, membership)  
- `vw_customer_value` – Purchasing data (total purchases, avg order value, lifetime value, CLV bucket, returns)  
- `vw_customer_satisfaction` – Experience data (average satisfaction score, escalation risk)  
- `vw_engagement_for_bi` – Consolidated BI-ready view combining CLV, engagement, satisfaction, and risk  

**Highlights**
- Implemented null handling and default values to preserve record coverage  
- Validated SQL output against Excel prototype for consistency before loading to Power BI  

---

## Power BI Data Model

With SQL logic finalized, the data was modeled in **Power BI** using a star schema for maintainability and clarity.

**Model Overview**
- **Fact Tables:** `F_public_customer_value`, `F_public_customer_engagement`, `F_public_customer_satisfaction`, `F_public_core_profile`  
- **Dimension Table:** `DimCustomer` (central relationship control via customer_id)  
- **Measures Table:** Centralized DAX calculations  

**Core DAX Measures**
- Average CLV  
- Average Engagement Score  
- Average Satisfaction Score  
- % Repeat Customers  
- % Premium Members  
- Escalation Risk by CLV Tier and Engagement  

The model powers four report pages:
1. Customer Summary  
2. Demographics & Retention  
3. Engagement & Escalation Risk  
4. Insights & Actions  

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

An interviewer could ask, “How do you decide which customers to focus on first?” — this project is your practical answer.

---

## Next Steps

Future improvements planned:
- Add **trend tracking** to visualize engagement over time  
- Automate **Power BI refresh** for live data connections  
- Add a **churn-risk score** combining satisfaction, engagement, escalation, and CLV  
- Improve consistency between the Excel prototype and SQL logic  

**Vision:**  
Evolve this into a lightweight **CS Ops workload routing tool** that answers:  
> “Which customers need attention right now, and why?”

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
