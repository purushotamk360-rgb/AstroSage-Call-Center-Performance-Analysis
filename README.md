# AstroSage-Call-Center-Performance-Analysis
**Data Analytics Project | Excel | Call Center Operations | Customer Experience | Revenue Optimization**


# 📌 Project Overview

This project analyzes AstroSage call-center operations to identify
operational inefficiencies, customer-experience gaps, revenue
opportunities, and workforce imbalances.

Using a dataset of 28,027 customer interactions/users across 34
days, the analysis evaluates call and chat performance, consultation
channels, revenue generation, customer ratings, guru workload,
call-status outcomes, and demand patterns.

The final objective is to support a strategic ₹1 Crore investment
decision aimed at improving operational efficiency, customer
satisfaction, workforce productivity, and profitability


# 🎯 Business Problem

AstroSage operates a multi-channel consultation platform where service
quality and revenue depend on efficient handling of customer
interactions.

The analysis focuses on questions such as:

- How does call volume change over time?

- Which channels generate the most revenue?

- Where are the major call and chat failure points?

- How satisfied are customers with the service?

- Are workloads evenly distributed among gurus?

- Which areas should receive investment to improve business performance?

- How should a ₹1 Crore investment be allocated across technology, training, hiring, incentives, and analytics?


# 📊 Dataset Overview

Metric Value

- Customer interactions/users analyzed: 28,027

- Operational period: 34 days

- Gurus/agents supported: 131

- Total recorded calls: 8,512

- Completed calls: 3,451

- Failed calls: 1,043

- Incomplete calls: 875

- No-answer calls: 1,729

- Total net revenue: ₹2,13,987.32

- Average customer rating: 2.93 / 8


# 🧹 Data Cleaning & Preparation

**Phase 1 – Null/Missing Value Handling**
- Context-aware replacements using nested `IF` formulas.
- Example: `chatStatus` missing for call records → replaced with `"Call_Not_Applicable"`.
- Numeric blanks (e.g., `chatSeconds`, `amount`) → replaced with `0`.

**Phase 2 – Guru Name Standardization**
- Latest name selected based on `createdAT` per `gid`.
- Variations standardized (e.g., `Dr Balkrisna` → `Astro Dr Balkrisna`).
- Manual conflict resolution using business rules.

**Phase 3 – Feature Engineering (7 New Columns)**

| Column | Formula / Logic | Purpose |
|---|---|---|
| `Session_Date` | `=TEXT(createdAT,"yyyy-mm-dd")` | Daily grouping |
| `Session_Month` | `=TEXT(createdAT,"MMMM")` | Monthly trends |
| `Session_Year` | `=TEXT(createdAT,"yyyy")` | Annual filtering |
| `Session_Hour` | `=HOUR(createdAT)` | Time-slot analysis |
| `Time_Slot` | `=IF(Hour<5,"Late Night",IF(Hour<12,"Morning",IF(Hour<17,"Afternoon",IF(Hour<22,"Evening","Night"))))` | Peak-period identification |
| `Actual_Duration` | Unified duration for calls/chats | Standardized engagement metric |
| `Repeat_Caller` | `=COUNTIFS(uid,current_uid,createdAT,"<"&current_time)>0` | Identifies returning users |

**Phase 4 – Data Transfer**
- Used `VLOOKUP` with `MATCH` for dynamic column mapping from raw sheet to cleaned sheet.
- Formula: `=VLOOKUP($A2, data!$A$1:$BI$28028, MATCH('Cleaned data'!B$1, data!$A$1:$BI$1, 0), FALSE)`



# 🔍 Analytical Approach

The project followed a structured analytics workflow:

**1. Data Preparation**

Cleaned and standardized the raw operational dataset.

**2. Exploratory Analysis**

Used sorting, filtering, aggregation, Pivot Tables, and calculated
fields to identify patterns.

**3. Operational Analysis**

Analyzed call volume, call status, hourly demand, workload distribution,
and consultation performance.

**4. Customer Analysis**

Evaluated ratings, repeat callers, channel-level satisfaction, and
customer behavior.

**5. Revenue Analysis**

Compared revenue across consultation types and channels.

**6. Dashboard Development**

Created an interactive Excel dashboard to present KPIs and operational
trends.

**7. Strategic Investment Analysis**

Translated analytical findings into an investment allocation plan for ₹1
Crore.

# 📈 Key Analysis Areas

**Daily Call Volume**

Daily call volume showed significant fluctuations across the observation
period, with several sharp increases and decreases in activity.

**Revenue by Consultation Type**

The analysis shows that Call is the dominant revenue-generating
consultation channel, while Chat contributes a smaller share of revenue.

**Website / Channel Distribution**

GuruCool accounts for the majority of recorded interactions,
followed by the mobile app, while dashboard usage is comparatively low.

**Call Status Performance**

A substantial proportion of interactions are not successfully completed,
creating an opportunity to improve reliability, availability, routing,
and customer response.

**Customer Satisfaction**

The overall average rating is approximately 2.93/8, indicating
considerable scope for improving service quality and customer
experience.

**Guru Workload**

Workload is unevenly distributed across gurus, with a small group
handling a disproportionately high number of interactions. This creates
potential risks related to workload concentration, service consistency,
and agent burnout.

**Repeat Callers**

The analysis identified 1,101 repeat callers, representing
approximately 53.26% of total calls under the project's
repeat-caller methodology.

# 📊 Dashboard

The Excel dashboard provides a consolidated view of call-center
performance.

**Dashboard KPIs**

- Total Revenue

- Total Agent/Guru Earnings

- Total Calls

- Total Chats

- Total Active Gurus

- Average Customer Rating

- Average Calls per Agent

**Dashboard Visualizations**

- Day-wise change in call volume

- Hourly call-volume pattern

- Revenue by consultation type

- Website/channel distribution

- Call-status distribution

- Chat-status distribution

- Rating-wise user distribution

- Rating-wise guru distribution

- Top-performing gurus

- Workload distribution across gurus

**Filters / Slicers**

- Consultation Type

- Rating

- Date / time-based analysis where applicable

# 💡 Key Business Insights

**1. Calls are the primary revenue driver**

The workbook reports approximately ₹1.68 lakh in net revenue from
the Call consultation category, compared with approximately ₹45.49
thousand from Chat.

**Business implication:** Stabilizing and improving call operations
should be a priority because the call channel has the strongest direct
revenue contribution.

**2. Customer satisfaction requires improvement**

The overall average customer rating is approximately 2.93/8.

**Business implication:** Training, quality monitoring, better customer
handling, and improved service reliability can potentially increase
satisfaction and repeat usage.

**3. Workload is concentrated among a smaller group of gurus**

The analysis identifies significant variation in guru activity, with top
performers handling substantially more interactions than many other
gurus.

**Business implication:** Workforce planning and workload balancing are
required to reduce burnout risk and improve consistency.

**4. Failed and unsuccessful interactions represent an operational opportunity**

The call-status analysis contains substantial volumes of failed,
incomplete, busy, and unanswered interactions.

**Business implication:** Intelligent routing, callback mechanisms,
capacity planning, and real-time monitoring could improve successful
consultation completion.

**5. Peak-hour demand requires better workforce planning**

Call activity changes significantly by hour, with stronger demand during
the daytime and evening operating period.

**Business implication:** Staffing should be aligned with demand instead
of maintaining a uniform workforce level throughout the day.

# 💰 ₹1 Crore Strategic Investment Plan

Based on the analysis, the recommended investment allocation is:

Investment Area Allocation

Technology & Automation - ₹30 Lakhs
Agent Training & Quality Improvement - ₹25 Lakhs
Hiring & Capacity Expansion - ₹20 Lakhs
Performance Incentives & Retention - ₹10 Lakhs
Digital Infrastructure & Cloud Upgrades - ₹10 Lakhs
Customer Feedback & Analytics - ₹5 Lakhs
**Total ₹1 Crore**

**Why this allocation?**

**₹30 Lakhs -- Technology & Automation** - Intelligent call routing -
Real-time monitoring - Automated callbacks - Workflow automation -
AI-assisted customer support

**₹25 Lakhs -- Training & Quality Improvement** - Communication
training - Customer-handling skills - Product/domain knowledge -
Continuous quality monitoring

**₹20 Lakhs -- Hiring & Capacity Expansion** - Add specialized agents -
Improve capacity during peak periods - Reduce pressure on high-workload
gurus

**₹10 Lakhs -- Performance Incentives & Retention** - Performance-linked
incentives - Recognition programs - Retention initiatives

**₹10 Lakhs -- Digital Infrastructure & Cloud Upgrades** - Improve
system reliability - Strengthen scalability - Support real-time
operational monitoring

**₹5 Lakhs -- Customer Feedback & Analytics** - Customer feedback
systems - Satisfaction tracking - Performance analytics - Continuous
improvement monitoring.


# 🚀 Expected Business Outcomes

If successfully implemented and monitored, the investment strategy is
expected to target:

- **20--30% reduction** in failed and incomplete interactions.

- Improvement in customer satisfaction and service quality.

- Faster response and query resolution.

- Better workload distribution across gurus.

- Lower agent burnout risk.

- Higher consultation completion rates.

- Improved revenue conversion.

- Stronger operational visibility through real-time analytics.

These are **target outcomes**, not guaranteed results, and should be
validated through post-investment KPI tracking.

# 📌 Recommended KPI Framework

The following KPIs can be monitored after implementation:

**KPI Purpose**

- Call Completion Rate - Measure successful consultation completion
- Failure Rate - Track operational failures
- Customer Satisfaction (CSAT) - Measure customer experience
- Average Rating - Monitor service quality
- First Contact Resolution - Measure resolution effectiveness
- Average Resolution Time - Track operational efficiency
- Calls per Guru - Monitor workload
- Revenue per Consultation - Measure monetization
- Repeat Caller Rate - Monitor customer retention
- Peak-Hour Utilization - Optimize staffing
- Guru Workload Concentration - Identify workload imbalance

# 🛠️ Tools & Technologies

**Microsoft Excel**

- Data cleaning

- Formulas

- Sorting & filtering

- Pivot Tables

- KPI calculations

- Dashboard creation

- Data visualization

**Analytical Techniques**

- Descriptive analytics

- Trend analysis

- Customer segmentation

- Revenue analysis

- Workload analysis

- Correlation analysis

- Operational performance analysis

# 📁 Project Structure


```text
AstroSage-Call-Center-Analysis/
│
├── README.md
├── Data/
│   └── raw_data.xlsx
|   |__ cleaned_data.xlsx
├── Dashboard/
│   └── AstroSage Excel.xlsx
├── Presentation/
│   └── AstroSage ppt.pptx
└── Report/
    └── Report Purushotam.docx
```


# 📚 Project Deliverables

**Excel Workbook**

Contains:

- Raw dataset

- Cleaned dataset

- Objective analysis

- Subjective analysis

- Pivot-based calculations

- Dashboard

**PowerPoint Presentation**

Contains:

- Problem statement

- Data overview

- Cleaning methodology

- Analytical approach

- Dashboard walkthrough

- Key findings

- Strategic insights

- Investment allocation

- Expected outcomes

**Analytical Report**

Contains detailed business questions, analysis, findings, and strategic
recommendations.

# 🎯 Conclusion

The AstroSage call-center analysis demonstrates how operational data can
be transformed into actionable business decisions.

The analysis highlights three major priorities:

1. **Modernize technology and improve interaction reliability.**

2. **Strengthen workforce capabilities while balancing guru
workloads.**

3. **Use data-driven workforce planning and customer feedback to
improve service quality and profitability.**


A balanced ₹1 Crore investment across technology, training, capacity,
incentives, infrastructure, and analytics provides a structured approach
to addressing the major operational gaps identified in the data.

# 👤 Author

**Purushotam Kumar**

**Project:** AstroSage Call Center Optimization & Strategic Investment Analysis

**Focus Areas:** Data Analytics | Excel | Business Analysis | Operations Analytics | Customer Experience | Revenue Optimization

# ⭐ Project Highlights

**28,027 interactions/users analyzed • 131 gurus • 34 days of operational data • ₹2.14 Lakh+ net revenue analyzed • ₹1 Crore strategic investment plan**

# 📝 License

This project is for educational and demonstration purposes. Data is anonymized and used with permission.
