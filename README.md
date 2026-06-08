<div align="center">

<img src="https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
<img src="https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white"/>
<img src="https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white"/>
<img src="https://img.shields.io/badge/Star%20Schema-8A2BE2?style=for-the-badge&logo=databricks&logoColor=white"/>

<br/><br/>

# 🏙️ Real Estate Performance Analytics
### EMAAR — Full-Cycle Power BI Intelligence Dashboard · 2023–2025

<br/>

| 💰 Total Revenue | 🏠 Units Sold | 📊 Conversion Rate | 👥 Total Clients | 👁️ Total Visits |
|:---:|:---:|:---:|:---:|:---:|
| **$1.54 Billion** | **2,000** | **40%** | **1,479** | **5,000** |

<br/>

</div>

---

## 📌 Project Overview

A **comprehensive Power BI analytics platform** built for EMAAR Real Estate, designed to optimize sales efficiency, expose performance gaps, and drive data-informed strategy across three fiscal years.

The project covers the **full data lifecycle** — from raw Excel ingestion and cleaning, through Star Schema modeling and advanced DAX engineering, to an executive-grade interactive dashboard.

> **Key focus areas:** Miami market slowdown · Agent performance gap · Returning customer retargeting · Seasonal demand forecasting

---

## 🎯 Business Problem

The real estate sector in 2025 struggled to sustain the strong momentum built in 2024. Four critical challenges required a data-driven response:

| # | Challenge | Impact |
|---|-----------|--------|
| 1 | 📉 **Declining conversion in Miami** | Referral/lead rates dropped **17% YoY** |
| 2 | ⏳ **Slower purchase decisions** | Q1–Q2 2025 sales stagnated vs 2024 peak |
| 3 | 👥 **Agent performance gap** | Bottom performers recorded as low as **17% efficiency** |
| 4 | 🔄 **Untapped returning customers** | High-CLV 2024 cohort left without re-engagement strategy |

---

## 📂 Dataset

**Source:** Single Excel workbook · **5 relational tables** · **5,000+ rows per table** · Historical data: 2023–2025

| Table | Type | Key Fields |
|-------|------|------------|
| `Sales` | ⚡ Fact | SaleID, SalePrice, SaleDate, AgentID, ClientID, PropertyID |
| `Visits` | ⚡ Fact | VisitID, VisitDate, AgentID, ClientID, PropertyID |
| `Clients` | 🔷 Dimension | ClientID, Client Name, Email, Phone |
| `Agents` | 🔷 Dimension | AgentID, Agents Name, Email, Phone |
| `Properties` | 🔷 Dimension | PropertyID, PropertyType, Location, PriceUSD, Size_sqm |

---

## 🛠️ Tech Stack

```
Power BI Desktop   →   Dashboard design, publishing & interactivity
Power Query (M)    →   Data ingestion, cleaning & transformation
DAX                →   Custom KPIs, time intelligence, iterative measures
Star Schema        →   Optimized relational data model
Excel              →   Source data (5 tables × 5,000+ rows)
```

---

## 🧠 Technical Implementation

### ✅ Data Preparation — Power Query

- Removed duplicate records across all 5 tables
- Standardized data types (dates, currency, text encoding)
- Cleaned inconsistent location and property-type values
- Structured foreign key relationships for Star Schema compatibility

### ✅ Data Model — Star Schema

<br/>

![Data Model](<screenshots/Data Model (Star Schema).png>)

<br/>



### ✅ DAX Measures

```


**Core KPIs:**

```dax
Total Sales =
SUM(Sales[SalePrice])

Units Sold =
COUNT(Sales[SalePrice])

Total Visits =
COUNT(Visits[VisitID])

Total Clients =
DISTINCTCOUNTNOBLANK(Clients[Client Name])

Conversion Rate =
DIVIDE([Units Sold], [Total Visits], 0)
```

**Agent & Pricing Intelligence:**

```dax
Agent's Average Performance =
AVERAGEX(
    Agents,
    [Total Sales]
)

Avg Price per SQM =
AVERAGEX(
    Properties,
    DIVIDE(
        Properties[PriceUSD],
        Properties[Size_sqm]
    )
)
```

**Dynamic Date Table:**

```dax
Dim Date =
VAR MinDate = MIN(MIN(Sales[SaleDate]), MIN(Visits[VisitDate]))
VAR MaxDate = MAX(MAX(Sales[SaleDate]), MAX(Visits[VisitDate]))
RETURN
ADDCOLUMNS(
    CALENDAR(MinDate, MaxDate),
    "Year",        YEAR([Date]),
    "Quarter",     "Q" & FORMAT([Date], "Q"),
    "Month Name",  FORMAT([Date], "MMMM"),
    "Month Number", MONTH([Date]),
    "Year Month",  FORMAT([Date], "YYYY-MM")
)
```

---

## 📊 Dashboard Pages

### 1️⃣ Real Estate Performance Review

![Performance Review](<screenshots/Real Estate Performance Review.png>)

Executive overview with YoY revenue trend, sales volume by property type, property revenue breakdown, and total visits by location.

---

### 2️⃣ Property Portfolio

![Property Portfolio](<screenshots/Property Portfolio.png>)

Drill into monthly sales trends, average price/SQM by city, and property type performance. Filtered to 2024 data with $793M in sales and 1,030 units.

---

### 3️⃣ Performance Analytics — Agent Leaderboard

![Performance Analytics](<screenshots/Performance Analytics.png>)

Top-performing agents ranked by total revenue. Highlights the dominance of the top 15 agents and the wide efficiency gap across the team.

---

### 4️⃣ Client Insights

![Client Insights](<screenshots/Client Insights.png>)

Customer purchasing power by property type, top-purchasing clients, sales volume over time (2023–2025), and revenue by location.

---

## 📈 Key Insights

### 🔴 Miami Market Slowdown — 2025
- Lead/referral rates **declined 17%** compared to 2024
- January 2025 opened weaker; stagnation persisted through Q1–Q2
- Buyers entered a **waiting mode** — extended lead-to-sale cycles
- Seasonal demand peak was delayed vs historical patterns

### 🔵 Agent Performance Polarization
- **Top 15 agents** drive a disproportionate share of total revenue
- High performers close **Villa and premium-tier** properties — not just more volume
- Bottom-tier agents recorded conversion efficiency as low as **17%**
- Actionable gap exists for structured mentorship and coaching

### 🟢 2024 Customer Cohort — Untapped CLV
- Clients acquired in 2024 represent the highest retargeting ROI
- Segmenting by purchasing behavior enables precision offers
- Increasing **Customer Lifetime Value (CLV)** is a faster growth lever than cold acquisition

### 🟡 Product & Location Mix
| Property Type | Units Sold | Avg Price/Unit |
|---------------|:----------:|:--------------:|
| Apartment | 500 | $512K |
| Villa | 428 | $515K |
| Retail | 377 | $523K |
| Office | 355 | $525K |
| Warehouse | 340 | $530K |

| City | Total Visits | Revenue |
|------|:------------:|:-------:|
| New York | 1,052 | $335M |
| Miami | 1,013 | $330M |
| Chicago | 986 | $298M |
| Los Angeles | 945 | $294M |
| Houston | — | $282M |

---

## 🚀 Actionable Recommendations

### 🎓 Experience Transfer Program
> Deploy structured workshops led by the **top 15 agents** — covering villa sales tactics, premium negotiation, and high-ticket closing techniques — targeting the bottom 30% of the team.

### 📣 Seasonal Marketing Strategy
> Increase advertising investment in **Miami before Q3 summer peaks**. Layer retargeting campaigns for the 2024 buyer cohort using behavioral segmentation to accelerate re-conversion.

### 🏗️ Inventory Optimization
> Expand **apartment inventory** in New York and Miami — both cities show sustained high visit-to-sale turnover. Evaluate **warehouse and office listings** in Chicago to exploit the price/SQM advantage.

---

## 📁 Repository Structure

```
📦 Real-Estate-Performance-Analytics
├── 📊 Reports/
│   ├── Real Estate Performance Analytics 2026.pdf
│   └── Real Estate Performance Review 2026.pbix
├── 📸 screenshots/
│   ├── Real Estate Performance Review.png
│   ├── Real Estate Performance Review with Filters.png
│   ├── Property Portfolio.png
│   ├── Performance Analytics.png
│   ├── Client Insights.png
│   └── Data Model (Star Schema).png
└── 📄 README.md
```

---

## 🤝 Connect

<div align="center">

[LinkedIn](https://www.linkedin.com/in/mahmoud-hamdi-analyst) · [Email](mailto:mahmoudhamdiwm@gmail.com)

*If you found this project useful, please consider giving it a ⭐*

</div>

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

