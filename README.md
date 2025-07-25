# Customer Engagement Strategy — Excel Project

## Overview

This project simulates how a Customer Success Operations Analyst might analyze customer engagement data and generate **Next Best Action** recommendations to help drive continued engagement and retention.

I built this project in Excel to deepen my understanding of **engagement strategy logic** and how tools like Gainsight structure decision models. My goal was to mimic part of a CS Ops workflow — from data cleaning to segmentation to action recommendations — using only Excel.

## Business Goal

Simulate an internal customer engagement model that could help a Customer Success Operations or CS Ops team:

- Identify at-risk customers  
- Segment customers by tenure, risk level, and engagement score  
- Recommend appropriate actions based on customer traits  
- Support a **Next Best Action** framework to guide team interventions  

## Data & Cleaning

I worked with a simulated customer dataset that included:

- Customer demographic and account traits  
- Satisfaction scores  
- Conversion rates across channels  
- Loyalty and repeat purchase indicators  

Cleaning steps included:

- Normalizing Yes/No flags  
- Grouping tenure into **Established, Loyal, New** categories  
- Converting numeric columns for consistency  
- Building calculated columns for **risk level** and **engagement status**  

## Next Best Action Logic

To simulate Gainsight-style logic, I built two levels of recommendations:

### Level 1 — Next Best Action Table

- Based on **tenure group**, **risk level**, and **satisfaction score**  
- Determines whether to **Monitor**, **Maintain**, **Re-engage**, or **Escalate**  

### Level 2 — Strategy Matrix

- Combines Level 1 recommendations with **email strategy** and **tenure signals**  
- Generates a final suggested action per customer  
- Uses a reference matrix to map combinations of key traits to actionable outcomes  

Excel logic used:

- `IF` and `XLOOKUP` functions  
- **Concatenated match key** built from 4 customer attributes  
- Lookup against a reference matrix to assign the correct strategy  

## Key Skills Demonstrated

- Excel formulas for complex decision logic  
- Customer segmentation techniques  
- Simulating CS Ops workflows in Excel  
- Building structured **Next Best Action** models  
- Mimicking Gainsight logic in Excel for learning purposes  

## Sample Outputs

### Cleaned Customer Data Preview
![Cleaned Customer Data](images/cleaned_customer_data.png)

### Next Best Action Level 2 Logic Table
![Next Best Action Level 2](images/next_best_action_lv2.png)

### Customer Engagement Strategy Matrix
![Customer Engagement Strategy Matrix](images/engagement_strategy_matrix.png)

## Why I Built This Project

I am actively building toward a career in **Customer Success Operations**.  
As part of that learning path, I wanted to:

- Better understand **how CS Ops teams use engagement data**  
- Practice structuring action recommendations from raw data  
- Deepen my Excel formula fluency for CS Ops use cases  
- Simulate a **real-world internal process** I might support in a CS Ops role  

## Next Steps

- Expand logic to cover additional signals (support ticket volume, product usage trends)  
- Explore building a version in **Power BI** to support visualization and scaling  
- Compare Excel-based model to functionality in actual **Gainsight** instance  

## Tools Used

- Microsoft Excel  
- Data cleaning and transformation  
- `XLOOKUP`, `IF` logic  
- Concatenated match key logic for strategy mapping  

## What This Project Demonstrates

This isn’t just an Excel workbook — it’s a simulation of how Customer Success Operations teams make structured, repeatable decisions.

By completing this, it demonstrates:

- The ability to turn customer data into actionable prioritization logic  
- Comfort thinking in **rules, segments, and behavioral triggers**  
- Experience building a tool that reflects **real CS workflows**  
- The capacity to troubleshoot, refactor, and complete an operational system using limited tools  

It reflects the kind of thinking required in **CX Analyst, Customer Operations, or CS Ops roles** — where you aren't just analyzing, you're building systems that guide decisions.

## Contact

**Name:** Aaron Zeug  
**LinkedIn:** [linkedin.com/in/aaronzeug](https://linkedin.com/in/aaronzeug)  
**GitHub:** [github.com/aaronzeug](https://github.com/Gray135)
