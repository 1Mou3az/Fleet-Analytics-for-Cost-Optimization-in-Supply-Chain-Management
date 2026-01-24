# 🚚 Fleet Management & Supply Chain Analytics

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)

> **An end-to-end analytics solution for fleet operations, providing data-driven insight into the operational factors that supported a significant turnaround in net profitability.**

---

## 💻 Project Overview

This project analyzes comprehensive fleet management data spanning **January 2018 - August 2019** for a logistics company operating across **51 US states**. Through advanced data engineering and visualization techniques, I uncovered critical operational inefficiencies and designed interactive dashboards that enabled strategic decision-making.

### Business Impact
- **💰 Net Profit Growth:** Identified drivers behind growth from $93.45K to $1.20M (+1,188.6%)
- **📈 Gross Margin Improvement:** Analyzed cost and asset mix changes that lifted gross margin from 5.38% to 45.95% (+754%)
- **⚙️ Cost Structure Optimization:** Quantified impact of 51.5% fixed cost reduction ($2M → $969K)
- **⛽ Fuel Efficiency Gains:** Highlighted factors contributing to a 36% fuel cost reduction
- **🔧 Maintenance Optimization:** Exposed a 44% reduction linked to preventive maintenance adoption

---

## 🎯 Key Features

### 1. **Multi-Dimensional Analytics**
- **Driver Performance Analysis** - Individual efficiency metrics across 32 drivers
- **Asset Optimization** - Vehicle/trailer profitability analysis (31 vehicles, 4 truck types, 3 trailer types)
- **Geographic Intelligence** - 293 cities across 51 states with revenue heatmaps
- **Temporal Insights** - Seasonality patterns, monthly trends, YoY comparisons

### 2. **Interactive Dashboards**
- **Fleet Management Dashboard** - Real-time KPIs with 269K liters consumed, 1M KM traveled
- **Driver Performance Dashboard** - Fuel efficiency ranking (0.17 - 0.33 L/KM range)
- **Revenue Analytics** - Geographic distribution with drill-through capabilities
- **Root Cause Analysis** - Decomposition trees for cost and profit

### 3. **Advanced DAX Calculations**
```dax
// Sample Measures Created
GM% = DIVIDE([Net Profit], [Total Revenue], 0) * 100
AVG Fuel Efficiency = DIVIDE([Total KM Traveled], [Total Liters Consumed], 0)
%YoY Growth = DIVIDE([Current Year] - [Previous Year], [Previous Year], 0)
Customer Retention % = DIVIDE([Customers With Multiple Orders], [Total Active Customers], 0)
```

---

## 🛠️ Technical Stack

### Data Engineering
| Tool | Purpose |
|------|---------|
| **Python 3.x** | Data cleaning, transformation, and validation |
| **Pandas** | DataFrame operations and statistical analysis |
| **Jupyter Notebook** | Exploratory data analysis (EDA) documentation |
| **NumPy** | Numerical computations |

### Business Intelligence
| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Interactive dashboard development |
| **DAX** | Advanced calculations and measures (20+ custom metrics) |
| **Power Query** | ETL processes and data modeling |
| **M Language** | Custom data transformations |

---

## 📁 Project Structure

```
fleet-management-analytics/
│
├───│─ Dataset/                        # Original Excel files
│   │   ├── DimensionTables.xlsx    # Customers, Drivers, Vehicles
│   │   ├── fCosts.xlsx             # KM Traveled & Costs
│   │   └── Dim States.xlsx         # US States lookup
│   │
│   └── Cleaned Data/                  # Cleaned CSV files
│       ├── F_Freight.csv           # Freight transactions (92K records)
│       ├── F_KMTraveled.csv        # Distance & costs (295 records)
│       ├── D_Customers.csv         # Customer dimensions (43K records)
│       ├── D_Drivers.csv           # Driver master (32 drivers)
│       ├── D_Vehicles.csv          # Vehicle fleet (31 vehicles)
│       └── D_STATES.csv            # State lookup (51 states)
│
├── Python Notebook/
│   └── Supply_Chain_Analytics.ipynb  # Complete EDA & cleaning pipeline
│
├── Power BI Dashboard/
│   ├── SupplyChain Dashboard.pbix  # Power BI Dashboard file
│   └── Dashboard.pdf  # Dashboard screenshots
│
├── images/                         # Images used
│   ├── Table.jpg
│   ├── User.png
│   ├── Users.png
│   ├── background.png
│   └── background2.png
│ 
│
└── README.md
│ 
│
└── FUll_Analysis_Report.pdf
```

---

## 🔍 Data Analysis Process

### Phase 1: Data Auditing & Quality Assessment
```python
# Comprehensive data quality checks performed:
✓ Schema validation (data types, column names)
✓ Missing value analysis (zero missing values found)
✓ Duplicate detection (no duplicates identified)
✓ Outlier identification (statistical quantile analysis)
✓ Referential integrity checks (FK relationships validated)
```

**Key Findings:**
- **Invalid Weights:** 3 records with zero weight but non-zero revenue (0.003% - dropped as maintenance-only entries)
- **Data Type Corrections:** Converted date columns from object to datetime format
- **Data Consistency:** 49.63% of records had matching Kg/Cubic weights (indicating dimensional weight usage)

🐍 [Data Cleaning & Preparation (Python Notebook)](Python%20Notebook/Supply_Chain_Analytics.ipynb)

### Phase 2: Feature Engineering

Created **20+ calculated metrics** including:

| Metric Category | Examples |
|----------------|----------|
| **Efficiency KPIs** | Fuel Efficiency (KM/L), Fuel Cost per KM, Maintenance Cost per KM |
| **Financial Metrics** | Net Profit, Gross Margin %, YoY Growth %, Total Costs |
| **Driver Analytics** | Avg Trip Distance, Number of Trips, Fixed Cost per KM |
| **Customer Insights** | Retention Rate, Multiple Order %, Active Customers |

### Phase 3: Data Modeling

**Star Schema Implementation:**
- **Fact Tables:** F_Freight (92,057 rows), F_KMTraveled (295 rows)
- **Dimension Tables:** D_Customers, D_Drivers, D_Vehicles, D_STATES
- **Relationships:** One-to-many with proper cardinality and cross-filter direction

 📊 [Dashboard implementation file for measures, data modeling, and analytics – Power BI](Power%20BI%20Dashboard/SupplyChain%20Dashboard.pbix)  
---

## ✨ Dashboard Highlights

### 1. Fleet Management Overview
- Real-time operational metrics
- Time-series analysis with seasonality detection
- Geographic revenue distribution map

### 2. Driver Performance Analytics
- Comparative efficiency rankings
- Drill-through to individual driver profiles
- Fuel consumption heatmaps

### 3. Root Cause Analysis
- Decomposition trees for cost/profit/revenue
- Multi-level drill-down (Year → Quarter → Month → Truck Type → Driver)
- What-if scenario modeling

🖥️ [View Dashboard (PDF)](Power%20BI%20Dashboard/Dashboard.pdf)

---

## 📈 Key Insights & Recommendations

### 1️⃣ Financial & Operational Performance
> Metrics compare **2018 vs 2019**  

- **Net Profit:** $93K → $1.20M (+1,188%)  
- **Gross Margin:** 5.38% → 45.95%  
- **Total Distance:** 880,000 KM → 456,000 KM (↓48%)  
- **Fixed Costs:** $2M → $969K (↓51.5%)  
- **Fuel Costs:** $551K → $351K (↓36%)  
- **Maintenance Costs:** $171K → $96K (↓44%)  

**Key Drivers:** Cost restructuring, preventive maintenance, route optimization, load efficiency.

---

### 🏆 Top Drivers
| Driver | Fuel Efficiency | Fuel Cost/KM | Maintenance Cost/KM |
|--------|----------------|--------------|-------------------|
| **Efan Archer** | 5.74 | $0.56 | $0.11 |
| **Salahuddin Arellano** | 5.38 | $0.67 | $0.11 |
| **Yasin Buck** | 5.14 | $0.65 | $0.11 |

### ⚠️ Underperformers
| Driver | Fuel Efficiency | Fuel Cost/KM | Action Required |
|--------|----------------|--------------|----------------|
| **Amman Vega** | 3.04 | $1.10 | Fuel-efficient driving training |
| **Karol Woods** | 4.01 | $0.81 | Administrative review |
| **Kenny Todd** | 4.92 | $0.70 | Asset utilization improvement |

### 🚨 Critical Finding: "No Driver" Issue
- **31 trips** (84,336 KM) unassigned drivers  
- **$41,069** in maintenance costs (345% higher than fleet average)  
- **Recommendation:** Implement mandatory driver ID logging system

---

### 🚗 Asset Performance
**High-ROI Assets:**  
- **Reefer + Box/Trailer:** 47.6% GM, $697K net profit  
- Fuel: 18.5 L/100KM, Maintenance: $0.18/KM  

**Assets to Retire:**  
- **Tractor (Dry):** 36.3 L/100KM, $0.31/KM (economically unviable)  

---

### 🛠️ Key Strategic Recommendations
- **Asset Management:** Immediate replacement of low-performing tractors; preventive maintenance schedule every 10,000 KM  
- **Driver Optimization:** Incentives for top performers, specialized training for low performers, enforce mandatory driver logging  
- **Financial Sustainability:** Diversify seasonal contracts, flexible cost structures, balanced maintenance scheduling  
- **Customer Strategy:** Tiered loyalty program, cross-selling/up-selling, referral campaigns  
- **Geographic Expansion:** Pilot Western Frontier expansion (CA/WA), CRM campaigns for single-order customers  
- **Peak Season Preparation:** Early hiring of seasonal drivers to avoid third-party surcharges



📑 [FULL Detailed Report with Insights and Recommendations](FUll_Analysis_Report.pdf)
---

## 🎓 Skills Demonstrated

### Technical Skills
- **Data Engineering:** ETL pipelines, data validation, schema design
- **Python Programming:** Pandas, NumPy, data cleaning automation
- **SQL Concepts:** Star schema modeling, relationship management
- **DAX Programming:** Time intelligence, complex calculations, context transition
- **Power BI Development:** Interactive visualizations, drill-through, bookmarks, slicers

### Analytical Skills
- **Exploratory Data Analysis (EDA):** Statistical profiling, outlier detection
- **Business Intelligence:** KPI design, metric definition, performance benchmarking
- **Root Cause Analysis:** Decomposition methodologies, hypothesis testing
- **Data Storytelling:** Insight synthesis, executive reporting

### Domain Knowledge
- **Supply Chain Management:** Fleet optimization, route efficiency, asset utilization
- **Financial Analysis:** P&L analysis, margin optimization, cost structure analysis
- **Operations Management:** Driver performance, preventive maintenance, capacity planning

---