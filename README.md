# 📊 Customer Engagement Strategy (Excel Logic Engine)

This project simulates a real-world **Customer Success Operations workflow** that transforms customer risk signals and behavioral patterns into automated strategy assignments using only Excel.

It delivers **Next Best Actions (NBA)** and **CSM Strategy Codes** based on layered logic, match keys, and behavioral inputs — all without any code or third-party platforms.

---

##  Business Value Delivered

| Value | Description |
|-------|-------------|
| Customer Insights | Segments accounts based on risk, engagement level, email status, and tenure |
| Strategic Automation | Assigns CSM strategies based on logic-driven inputs, reducing manual review |
| Churn Risk Targeting | Flags at-risk customers for re-engagement or escalation |
| Operational Efficiency | Mimics the prioritization logic used by modern CS teams |
| Portfolio-Ready Logic | Demonstrates real-world segmentation, lookup structures, and Excel modeling under constraint |

---

## Files Included

| File | Description |
|------|-------------|
| `Customer Engagement Strategy.xlsx` | Final workbook with match keys, logic matrix, and strategy output |
| `README.md` | This file — full project overview |

---

## Project Overview

Each customer record is evaluated based on four behavioral dimensions:

- **Risk Response** (e.g. At Risk, Escalate, Monitor)
- **Engagement Action** (e.g. Re-Engage, Maintain, Nurture)
- **Email Strategy** (e.g. Re-Engage Email, Maintain Email)
- **Tenure Signal** (e.g. Loyal, Unknown, Established)

These are combined into a **Match Key**, such as:  
`AT RISK | RE-ENGAGE | MAINTAIN EMAIL | LOYAL`

This key is used to look up the appropriate:
- **CSM Code** (e.g. Escalate, Maintain, Monitor)
- **Strategy Notes** or actions based on engagement tier

---

## How It Works

1. **Input Columns:** Risk, Engagement, Email Strategy, Tenure  
2. **Match Key Generator:** Combines the four variables into a unique lookup key  
3. **Logic Matrix:** Maps each key to a CSM Code and Suggested Action  
4. **Next Best Action Engine:** Uses `XLOOKUP` to assign strategies at scale  

All logic was built manually using Excel functions like `XLOOKUP`, `INDEX`, `MATCH`, `TRIM`, and `TEXTJOIN`, along with error handling and match validation.

---

## What This Project Demonstrates

This isn’t just an Excel workbook — it’s a simulation of how **Customer Success Operations teams** make structured, repeatable decisions.

By completing this, it demonstrates:
- The ability to turn customer data into **actionable prioritization logic**
- Comfort thinking in **rules, segments, and behavioral triggers**
- Experience building a tool that reflects **real CS workflows**
- The capacity to troubleshoot, refactor, and complete an operational system using limited tools

It reflects the kind of thinking required in **CX Analyst, Customer Operations, or CS Ops roles** — where you aren't just analyzing, you're building systems that guide decisions.

---

## Contact

- **Name:** Aaron Zeug  
- **LinkedIn:** [linkedin.com/in/aaronzeug](https://www.linkedin.com/in/aaronzeug)  
- **GitHub:** [github.com/aaronzeug](https://github.com/aaronzeug)
