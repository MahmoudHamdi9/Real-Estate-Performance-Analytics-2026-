# 🏠 Real Estate Performance Analytics (2023–2025)

## 📌 Project Overview
This project presents a comprehensive **Real Estate Performance Analytics Dashboard** designed to optimize **sales efficiency**, improve **customer experience**, and uncover actionable business opportunities across the 2023–2025 period.

The analysis focuses on identifying performance gaps, seasonal sales behavior, top agent efficiency, customer retargeting opportunities, and market fluctuations in key cities such as **Miami** and **New York**.

The dashboard was built using **Power BI**, leveraging advanced **data modeling**, **DAX calculations**, and interactive dashboard design principles.

---

## 🎯 Business Problem

The real estate sector in 2025 faced several challenges in maintaining the growth momentum achieved in 2024.

Key issues included:

- Declining conversion rates in major cities such as **Miami**
- Slower customer purchasing decisions in early 2025
- Significant performance gap between top-performing agents and the rest of the sales team
- Underutilized returning customer opportunities

This project aimed to provide a **data-driven strategy** to improve operational efficiency and revenue growth.

---

## 📂 Dataset Information

### Source:
Excel Dataset containing **5 relational tables**:

- Sales
- Visits
- Customers
- Agents
- Properties

### Volume:

- 5,000+ records per table
- Historical data covering **2023–2025**

---

## 🛠 Tools & Technologies Used

- **Power BI**
- Power Query
- DAX
- Data Modeling
- Star Schema Design
- Data Cleaning & Transformation
- UI/UX Dashboard Design

---

## 🧠 Technical Implementation

### ✔ Data Preparation
- Cleaned inconsistent records
- Standardized data types
- Removed duplicates
- Structured relationships between tables

### ✔ Data Modeling
Designed an optimized **Star Schema** connecting:

- Fact Sales
- Fact Visits

With dimensions:

- Customers
- Agents
- Properties
- Date Table

### ✔ Advanced DAX Measures
## 📐 Key DAX Measures & Data Modeling

This project includes custom DAX measures designed to track revenue, sales activity, customer conversion efficiency, agent productivity, pricing trends, and dynamic time-based analysis.

### Built KPIs such as:

- Conversion Rate  
- Total Revenue  
- Units Sold  
- Total Visits  
- Client Count  
- Agent Performance  
- Average Unit Price  
- Price per SQM  
- Dynamic Time Intelligence Analysis  

---

### Core Business Measures

```DAX
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
---
Agent's Average Performance =
AVERAGEX(
    Agents,
    [Total Sales]
)

Average Unit Price =
AVERAGE(Properties[PriceUSD])

Avg Price per SQM =
AVERAGEX(
    Properties,
    DIVIDE(
        Properties[PriceUSD],
        Properties[Size sqm]
    )
)
``` Dynamic Date Table
Dim Date =
VAR MinDate =
    MIN(
        MIN(Sales[SaleDate]),
        MIN(Visits[VisitDate])
    )

VAR MaxDate =
    MAX(
        MAX(Sales[SaleDate]),
        MAX(Visits[VisitDate])
    )

RETURN
ADDCOLUMNS(
    CALENDAR(MinDate, MaxDate),

    "Year", YEAR([Date]),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Month Name", FORMAT([Date], "MMMM"),
    "Month Number", MONTH([Date]),
    "Year Month", FORMAT([Date], "YYYY-MM")
)

```
## 📊 Key Insights

## 1️⃣ Temporal & Spatial Analysis

### Miami Market Slowdown in 2025

- Referral/Lead rates declined by **17%**
- January 2025 started weaker than 2024
- Continued stagnation through Q1 and Q2

### Strategic Interpretation:

- Buyers entered a **waiting mode**
- Lower lead-to-sale conversion
- Delayed seasonal peak demand

---

## 2️⃣ Agent Performance Analysis

### Top Agents Dominance

- Top 15 agents generated the highest conversion rates

### Important Finding:

Performance was not based only on quantity sold, but also:

- Ability to sell premium properties (Villas)
- Negotiation effectiveness
- High-ticket deal closing capability

### Performance Gap:

Some agents recorded efficiency as low as **17%**

---

## 3️⃣ Customer Experience & Retargeting

Customers acquired in **2024** represent a major untapped growth opportunity.

### Recommended Strategy:

- Analyze purchasing behavior
- Segment high-value customers
- Launch personalized offers
- Increase Customer Lifetime Value (CLV)

---

## 🚀 Actionable Recommendations

### 🔹 Experience Transfer Program
Create workshops led by top 15 agents to train lower-performing teams.

### 🔹 Seasonal Marketing Strategy
Increase advertising spend in Miami before summer demand peaks.

### 🔹 Inventory Optimization
Expand apartment inventory in:

- New York
- Miami

Due to high turnover and strong demand.

---

## 📈 Dashboard Features

- Executive KPI Overview
- Sales Trend Analysis
- Regional Performance Breakdown
- Agent Leaderboard
- Customer Segmentation
- Interactive Filters
- Time Intelligence Analysis

---

## 📷 Dashboard Preview
<img width="1257" height="647" alt="Screenshot 2026-01-27 095425" src="https://github.com/user-attachments/assets/f73a3ce4-75d9-41f0-b11b-ddddf8f57ddc" />
<img width="1206" height="674" alt="Screenshot 2026-01-28 055731" src="https://github.com/user-attachments/assets/40cc606b-34d4-410e-85d9-38e4991be28f" />
<img width="1622" height="904" alt="Screenshot 2026-01-28 055831" src="https://github.com/user-attachments/assets/d7a06979-3523-40ea-8db7-f8e79f8ea739" />
<img width="1621" height="911" alt="Screenshot 2026-01-28 055854" src="https://github.com/user-attachments/assets/9c7edf2c-03cd-45c1-a3c9-22b672890b08" />
<img width="1206" height="676" alt="Screenshot 2026-01-28 060002" src="https://github.com/user-attachments/assets/342b6789-b4f7-4698-9219-18835a83caa4" />
<img width="1204" height="674" alt="Screenshot 2026-01-28 060041" src="https://github.com/user-attachments/assets/04536d96-390e-42aa-8f1e-22a5d7090ed9" />
<img width="1208" height="674" alt="Screenshot 2026-01-28 100612" src="https://github.com/user-attachments/assets/c8744648-b47d-4e4e-b667-106128b2fdad" />

