# 🚚 Transportation & Logistics Optimization Dashboard

> An Excel-based analytics project that evaluates transportation cost, delivery performance, carrier and route efficiency, and vehicle utilization across 1,200 shipments (January–October 2026).

![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346) ![Domain](https://img.shields.io/badge/Domain-Supply%20Chain%20%26%20Logistics-blue) ![Dashboards](https://img.shields.io/badge/Dashboards-3-orange)

> **📌 Draft notes for the author (delete before publishing)**
> This README was built from the three dashboard screenshots. Items marked **`[PLACEHOLDER]`** need your input. Items marked **⚠️ Validate** are inconsistencies or unclear definitions found in the screenshots. Resolve or document them before publishing.

---

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Problem Statement](#2-problem-statement)
3. [Business Objectives](#3-business-objectives)
4. [Project Workflow](#4-project-workflow)
5. [Dataset and Data Model](#5-dataset-and-data-model)
6. [Data Cleaning and Preparation](#6-data-cleaning-and-preparation)
7. [Key Calculations and Metrics](#7-key-calculations-and-metrics)
8. [Dashboard Overview](#8-dashboard-overview)
9. [Dashboard 1: Transportation Performance Overview](#9-dashboard-1-transportation-performance-overview)
10. [Dashboard 2: Carrier & Route Optimization](#10-dashboard-2-carrier--route-optimization)
11. [Dashboard 3: Vehicle Utilization & Cost Saving](#11-dashboard-3-vehicle-utilization--cost-saving)
12. [Key Project Insights](#12-key-project-insights)
13. [Business Value](#13-business-value)
14. [Business Questions Answered](#14-business-questions-answered)
15. [Technical Skills and Tools](#15-technical-skills-and-tools)
16. [Project Structure](#16-project-structure)
17. [Data Validation Notes](#17-data-validation-notes)
18. [Dashboard Preview](#18-dashboard-preview)
19. [Connect With Me](#19-connect-with-me)

---

## 1. Project Overview

This project analyzes transportation operations for **1,200 shipments** with a total transportation cost of **₹36,874,775**. It is delivered as three interactive Excel dashboards:

| # | Dashboard | Focus |
|---|-----------|-------|
| 1 | Transportation Performance Overview | Cost, volume, delivery status, budget vs. actual |
| 2 | Carrier & Route Optimization | Carrier cost, on-time rate, route transit performance |
| 3 | Vehicle Utilization & Cost Saving | Load vs. capacity, cost breakdown, estimated savings |

**Data source:** `[PLACEHOLDER: state the source. If the dataset is synthetic or simulated, say so clearly here.]`
**Data period:** January 2026 – October 2026 (based on the monthly charts; October may be a partial month — **⚠️ Validate**).
**Currency:** Indian Rupees (₹). The symbol appears on some chart labels, but not on KPI cards. **⚠️ Validate** that all values are INR.

---

## 2. Problem Statement

Logistics teams need to control transportation spend while keeping deliveries on time. Common challenges include:

- Actual cost running above budget
- Uneven on-time performance across carriers and routes
- Planned transit times that are not met
- Vehicles running below their load capacity

Without a consolidated view, it is hard to tell where cost is going, which carriers or routes underperform, and where optimization could have the most impact. This project brings these views together in one dashboard set.

---

## 3. Business Objectives

- Track total transportation cost, cost per shipment, and monthly cost trends
- Compare **actual vs. budgeted** transportation cost by month
- Measure delivery performance (on-time rate, delays, pending shipments)
- Compare carriers on cost, on-time delivery, and rating
- Identify routes where actual transit time exceeds planned transit time
- Measure vehicle utilization and identify underutilized shipments
- Break down cost by component (freight, fuel surcharge, handling, toll, other)
- Estimate **potential** savings under clearly stated scenario assumptions

---

## 4. Project Workflow

```text
Raw Data  →  Data Cleaning  →  Data Model / PivotTables  →  KPI Calculations  →  Charts & Slicers  →  Insights & Recommendations
```

| Step | Activity | Status |
|------|----------|--------|
| 1 | Collect / generate shipment data | `[PLACEHOLDER: describe]` |
| 2 | Clean and standardize fields | `[PLACEHOLDER: describe]` |
| 3 | Build calculated columns and measures | `[PLACEHOLDER: Excel formulas and/or DAX]` |
| 4 | Create PivotTables and PivotCharts | Evident from chart field names (e.g., "Sum of Budgeted_Cost") |
| 5 | Add slicers (Destination, Carrier_ID, Order_Date, etc.) | Evident from screenshots |
| 6 | Design three dashboards | Completed |
| 7 | Validate metrics and document findings | See [Section 17](#17-data-validation-notes) |

---

## 5. Dataset and Data Model

> `[PLACEHOLDER: add table names, row counts, and relationship diagram.]` Only fields visible in the dashboards are listed below.

### 5.1 Fields Confirmed from the Dashboards

| Field | Used In | Description |
|-------|---------|-------------|
| `Order_Date` | Dashboard 1 slicer | Shipment order date |
| `Order_Month` | Dashboard 2 slicer | Month of the order |
| `Destination` | Dashboards 1 and 3 | Delivery destination (city) |
| `Origin` | Dashboard 3 slicer | Shipment origin (city) |
| `Carrier_ID` | Dashboards 1 and 2 | Carrier identifier (e.g., CAR-01) |
| `Route_ID` | Dashboard 2 | Route identifier (e.g., RT-001) |
| `Vehicle_Type` | Dashboard 3 | Vehicle category (e.g., 14ft Closed Body Truck) |
| `Budgeted_Cost` | Dashboard 1 | Planned cost for the shipment |
| `Total_Transportation_Cost` | Dashboards 1–3 | Actual total cost for the shipment |
| `Planned_Transit_Hours` | Dashboard 2 | Planned transit duration |
| `Actual_Transit_Hours` | Dashboard 2 | Actual transit duration |
| `Capacity_KG` | Dashboard 3 | Vehicle capacity |
| `Actual_Load_KG` | Dashboard 3 | Actual load carried |

### 5.2 Fields Implied but Not Confirmed

These are needed for the charts shown, but the column names are not visible. `[PLACEHOLDER: confirm exact names]`

| Implied Field | Needed For |
|---------------|-----------|
| Shipment ID | Shipment counts (1,200) |
| Delivery status (On Time / Delayed / Pending) | Dashboard 1 donut chart |
| Shipment status (Delivered / In Transit / Returned) | Dashboard 3 donut chart |
| Transportation mode (Road – FTL / LTL / Express) | Dashboard 1 pie chart |
| Carrier name and rating | Dashboard 2 charts and rating KPI |
| Distance (km) | Cost per km KPI |
| Cost components (Freight, Fuel Surcharge, Handling, Toll, Other) | Dashboard 3 cost breakdown |
| Delay hours | Average delivery delay KPI |
| Damage / failure indicator | Damage / failed delivery rate KPI |

### 5.3 Table Structure and Relationships

`[PLACEHOLDER: e.g., Shipments (fact) → Carriers, Routes, Vehicles, Destinations (dimensions). Add a model diagram: images/data_model.png]`

---

## 6. Data Cleaning and Preparation

`[PLACEHOLDER: document the cleaning steps you actually performed.]`

| Check | Details |
|-------|---------|
| Duplicates | `[PLACEHOLDER]` |
| Missing values | `[PLACEHOLDER]` |
| Data types (dates, numbers, text) | `[PLACEHOLDER]` |
| Naming standardization (city, carrier, vehicle names) | `[PLACEHOLDER]` |
| Calculated columns added | `[PLACEHOLDER]` |
| Month ordering | Month axes should be sorted chronologically (see Section 17) |

---

## 7. Key Calculations and Metrics

> **Important:** The formulas below are **suggested reference definitions** and have not been taken from the original workbook. Replace them with your actual Excel formulas or DAX measures. Some KPI values shown on the dashboards do not reconcile with the reference definitions (see Section 17).

### 7.1 KPI Definitions

| KPI | Dashboard Value | Reference Definition |
|-----|-----------------|----------------------|
| Total Transportation Cost | ₹36,874,775 | Sum of `Total_Transportation_Cost` |
| Total Shipments | 1,200 | Count of shipments |
| Cost per Shipment | ₹30,728.98 | Total cost ÷ total shipments |
| On-Time Delivery Rate | 89.05% | On-time shipments ÷ shipments in scope (**⚠️ definition unclear**) |
| Average Delivery Delay Hours | 29.03 | Average of delay hours (**⚠️ scope unclear**) |
| Total Active Carriers | 12 | Distinct count of carriers |
| Lowest Cost per Shipment | ₹5,127 | **⚠️ Unclear**: minimum of what? |
| Average Carrier Rating | 3.9 / 5 | Average of carrier rating |
| Average Cost per KM | ₹58.00 | Total cost ÷ total distance |
| Route Cost Variance | 5.35% | (Actual − Budget) ÷ Budget (**⚠️ scope unclear**) |
| Average Vehicle Utilization | 66.59% | Actual load ÷ capacity (**⚠️ method unclear**) |
| Underutilized Shipments | 621 | Shipments below a utilization threshold `[PLACEHOLDER: threshold]` |
| Total Excess Transportation Cost | ₹1,962.9K | Actual − Budget (see note in 7.3) |
| Potential Estimated Cost Saving | ₹2,040.0K | Scenario estimate (see 7.3) |
| Damage / Failed Delivery Rate | 4.17% | Damaged or failed shipments ÷ total shipments |

### 7.2 Example Excel Formulas (Reference Only)

```excel
' Cost per shipment
= SUM(Total_Transportation_Cost) / COUNTA(Shipment_ID)

' Vehicle utilization (row level)
= Actual_Load_KG / Capacity_KG

' Transit delay (row level)
= Actual_Transit_Hours - Planned_Transit_Hours

' Cost variance %
= (SUM(Total_Transportation_Cost) - SUM(Budgeted_Cost)) / SUM(Budgeted_Cost)
```

### 7.3 Example DAX Measures (Reference Only, if a Data Model Is Used)

```dax
Total Cost = SUM ( Shipments[Total_Transportation_Cost] )

Total Shipments = COUNTROWS ( Shipments )

Cost per Shipment = DIVIDE ( [Total Cost], [Total Shipments] )

Avg Utilization % = DIVIDE ( SUM ( Shipments[Actual_Load_KG] ), SUM ( Shipments[Capacity_KG] ) )

Cost Variance % = DIVIDE ( [Total Cost] - SUM ( Shipments[Budgeted_Cost] ), SUM ( Shipments[Budgeted_Cost] ) )
```

### 7.4 Savings Estimate: Observed Relationships

The Dashboard 3 savings figures appear to be **scenario-based assumptions**, not measured outcomes:

| Component | Value | How It Appears to Be Derived |
|-----------|-------|------------------------------|
| Reduced Budget Overruns by 10% | ₹196.3K | 10% × ₹1,962.9K excess cost |
| Reduced Transportation Costs by 5% | ₹1.8M | ≈ 5% × ₹36.87M total cost |
| **Potential Estimated Cost Saving** | **₹2,040.0K** | Sum of the two scenarios (≈ ₹2.04M) |

The 10% and 5% reduction rates are assumptions `[PLACEHOLDER: state the basis]`. These are **estimates only, not guaranteed savings**.

---

## 8. Dashboard Overview

| Dashboard | Slicers | KPI Cards | Charts |
|-----------|---------|-----------|--------|
| 1. Transportation Performance Overview | Destination, Carrier_ID, Order_Date | 5 | 5 |
| 2. Carrier & Route Optimization | Order_Month, Route_ID, Carrier_ID | 5 | 5 |
| 3. Vehicle Utilization & Cost Saving | Vehicle_Type, Origin, Destination | 5 | 5 |

---

## 9. Dashboard 1: Transportation Performance Overview

**Purpose:** Give a high-level view of total spend, shipment volume, delivery status, and budget performance.

### KPIs

| KPI | Value |
|-----|-------|
| Total Transportation Cost | ₹36,874,775 |
| Total Shipments | 1,200 |
| On-Time Delivery Rate | 89.05% (⚠️ see Section 17) |
| Cost per Shipment | ₹30,728.98 |
| Average Delivery Delay Hours | 29.03 |

### Charts

| Chart | What It Shows | Observations from the Screenshot |
|-------|---------------|----------------------------------|
| Monthly Transportation Cost Trend | Monthly actual cost | Peak in August (₹5.1M); lowest in October (₹1.8M). Months are plotted alphabetically, not chronologically. |
| Delivery Status Distribution | On Time / Delayed / Pending | On Time 993, Delayed 167, Pending 40 (total 1,200) |
| Monthly Actual vs. Budgeted Transportation Cost | Budget vs. actual by month | Actual is above budget in every month shown, Jan–Oct (rounded labels) |
| Transportation Cost By Destination | Cost by city | Highest bars appear to be Indore (~₹2.9M), Hyderabad (~₹2.7M), Ahmedabad (~₹2.0M). Verify label-to-bar mapping. |
| Shipment Volume By Transportation Mode | Shipments by mode | Road – FTL 615 (51.3%), Road – LTL 321 (26.8%), Road – Express 264 (22.0%) |

### Monthly Actual vs. Budget (Values Read from Chart Labels, in ₹ Millions)

| Month | Budgeted | Actual |
|-------|---------:|-------:|
| Jan | 3.1 | 3.3 |
| Feb | 2.8 | 2.9 |
| Mar | 3.7 | 3.9 |
| Apr | 3.9 | 4.2 |
| May | 3.7 | 3.9 |
| Jun | 4.4 | 4.6 |
| Jul | 3.8 | 4.1 |
| Aug | 4.8 | 5.1 |
| Sep | 3.0 | 3.2 |
| Oct | 1.7 | 1.8 |
| **Total (approx.)** | **≈ 34.9** | **≈ 37.0** |

The values are rounded, so totals are approximate. The actual total is consistent with the ₹36.87M KPI.

### Insights and Recommendations

- Spending exceeded budget in every month shown, with an overall gap of roughly ₹2M, or about 6% on rounded values.
- Full truckload (FTL) carries just over half of all shipments, so it is a natural first area for cost review.
- Recommendation: investigate the months with the largest gaps (e.g., Aug, Jun, Apr) and review budget-setting for peak months.

---

## 10. Dashboard 2: Carrier & Route Optimization

**Purpose:** Compare carriers and routes on cost, reliability, and transit performance.

### KPIs

| KPI | Value |
|-----|-------|
| Total Active Carriers | 12 |
| Lowest Cost per Shipment | ₹5,127 (⚠️ definition unclear) |
| Average Carrier Rating | 3.9 / 5 |
| Average Cost per KM | ₹58.00 |
| Route Cost Variance | 5.35% |

### Carrier Comparison (Values Read from the Charts)

| Carrier | Total Cost (₹M) | On-Time Rate | Cost per Shipment* (₹) |
|---------|----------------:|-------------:|-----------------------:|
| Apex Parcel & Cargo | 1.6 | 92.06% | 23.1K |
| Arrow Cargo Express | 2.1 | 75.28% | 23.3K |
| Bharat Freight Lines | 3.8 | 87.63% | 37.0K |
| Deccan Transport Co | 3.5 | 75.53% | 35.1K |
| Ganga Carriers | 1.9 | 66.10% | 31.1K |
| Himalaya Cargo Movers | 5.0 | ~92.66%† | 43.5K |
| Kaveri Logistics | 3.8 | 83.50% | 35.9K |
| MetroLink Freight | 3.3 | ~86.59%† | 22.8K |
| QuickLoad LTL Services | 2.4 | ~85.10%† | 22.8K |
| RapidMove Logistics | 2.0 | 74.65% | 25.9K |
| Sunrise Roadways | 5.3 | 83.06% | 40.1K |
| SwiftHaul Express | 2.2 | 92.55% | 22.5K |

\* The bottom-right chart is titled "Carrier Cost vs On Time Delivery" but shows a single "Total" series in ₹ thousands. The measure is assumed to be cost per shipment. **⚠️ Validate.**
† These labels are partly cut off in the screenshot and need to be re-checked.

### Other Charts

| Chart | Observations |
|-------|--------------|
| On-Time Delivery Rate by Route | Five routes shown: RT-016 (74.4), RT-017 (75.0), RT-028 (77.6), RT-058 (78.0), RT-062 (83.0). Values lack a % sign. The selection logic (e.g., top/bottom 5) is not stated. |
| Planned vs. Actual Transit Time | For all ten routes shown, actual transit time is higher than planned. The largest gaps appear on RT-051 (46.3 → 67.9 hrs) and RT-073 (35.7 → 57.6 hrs). The RT-010 actual label is obscured. |

### Insights and Recommendations

- On-time performance varies widely: Ganga Carriers is lowest at 66.10%, while SwiftHaul Express and Apex Parcel & Cargo are above 92%.
- SwiftHaul Express combines one of the lowest cost-per-shipment values (₹22.5K) with a high on-time rate (92.55%). Himalaya Cargo Movers has the highest cost per shipment (₹43.5K) and a similar on-time rate. Both are worth a deeper review.
- Recommendation: review contracts and volume allocation for high-cost, lower-reliability carriers, and investigate root causes on routes with large transit gaps.

---

## 11. Dashboard 3: Vehicle Utilization & Cost Saving

**Purpose:** Evaluate how well vehicle capacity is used, where cost is concentrated, and what savings might be possible under stated assumptions.

### KPIs

| KPI | Value |
|-----|-------|
| Average Vehicle Utilization | 66.59% |
| Underutilized Shipments | 621 (51.75% of 1,200) |
| Total Excess Transportation Cost | ₹1,962.9K |
| Potential Estimated Cost Saving | ₹2,040.0K (estimate) |
| Damage / Failed Delivery Rate | 4.17% (≈ 50 of 1,200) |

### Charts

| Chart | Observations |
|-------|--------------|
| Vehicle Utilization by Vehicle Type | 32ft MXL Container 73.72% and 22ft Closed Body Truck 72.45% are highest among legible labels. Mahindra Bolero Pickup is lowest at 55.23%, and Tata 407 is 58.11%. The 32ft SXL label is cut off. |
| Shipment Status Distribution | Delivered 1,141; In Transit 40; Returned 19 |
| Transportation Cost Breakdown | See table below |
| Actual Load vs. Vehicle Capacity | Average actual load is below capacity for every vehicle type (e.g., 32ft MXL: ~11.8K vs 16.0K kg) |
| Potential Saving by Optimization Opportunity | Reduced budget overruns by 10%: ₹196.3K. Reduced transportation costs by 5%: ₹1.8M. |

### Cost Breakdown (Values Read from the Chart)

| Component | Cost (₹M) | Approx. Share |
|-----------|----------:|--------------:|
| Freight | 30.9 | 83.7% |
| Fuel Surcharge | 2.4 | 6.5% |
| Handling | 1.7 | 4.6% |
| Toll | 1.3 | 3.5% |
| Other | 0.6 | 1.6% |
| **Total** | **≈ 36.9** | |

The shares are calculated from rounded labels and are approximate.

### Insights and Recommendations

- Freight accounts for more than 80% of total cost, so freight rates and load planning have the largest influence on spend.
- Over half of all shipments (621 of 1,200) are flagged as underutilized. Consolidating loads or right-sizing vehicles may reduce cost.
- Recommendation: define the underutilization threshold clearly, then test consolidation and vehicle-size changes on a pilot set of lanes.
- The savings figures are **estimates based on assumed reduction rates (10% and 5%)**. They are **not guaranteed results**.

---

## 12. Key Project Insights

Insights below are limited to what the dashboards support.

1. **Spend is above budget throughout the period.** Actual cost exceeds budget in all ten months shown.
2. **Freight dominates cost.** About 84% of cost comes from freight; fuel surcharge, handling, toll, and other charges make up the rest.
3. **Road FTL is the largest mode by volume.** 615 of 1,200 shipments (51.3%).
4. **Carrier reliability varies widely.** On-time rates range from 66.10% (Ganga Carriers) to over 92% (SwiftHaul Express, Apex Parcel & Cargo, and Himalaya Cargo Movers).
5. **Higher cost does not clearly mean better delivery.** Himalaya Cargo Movers has the highest cost per shipment and a high on-time rate, while SwiftHaul Express matches it on reliability at roughly half the cost per shipment (pending validation of the chart measure).
6. **Actual transit time exceeds plan on every route shown.** Some routes, such as RT-051 and RT-073, are more than 20 hours over plan.
7. **Vehicles run well below capacity.** Average utilization is 66.59%, and 51.75% of shipments are flagged as underutilized.
8. **Estimated savings of about ₹2.04M** are possible under the stated 10% and 5% scenarios. These are assumptions, not forecasts.

---

## 13. Business Value

| Area | How the Dashboards Help |
|------|-------------------------|
| Cost control | Show where spend exceeds budget and which cost components dominate |
| Carrier management | Support carrier scorecards and contract reviews |
| Service levels | Highlight routes and carriers with delivery delays |
| Capacity planning | Reveal underutilized vehicle types and load consolidation opportunities |
| Planning | Give a baseline for evaluating cost-saving scenarios |

> Business value is **potential**. No actual savings or operational improvements have been measured.

---

## 14. Business Questions Answered

- What is the total transportation cost and cost per shipment?
- How does monthly actual cost compare with budget?
- What share of shipments are on time, delayed, or pending?
- Which destinations account for the highest transportation cost?
- Which transportation modes carry the most shipments?
- Which carriers are the most and least reliable?
- Which carriers have the highest cost per shipment?
- Which routes show the largest gap between planned and actual transit time?
- How well are different vehicle types utilized?
- How is total cost split across freight, fuel surcharge, handling, toll, and other charges?
- What savings could result from the stated reduction scenarios?

---

## 15. Technical Skills and Tools

| Category | Details |
|----------|---------|
| Tool | Microsoft Excel |
| Data analysis | PivotTables, PivotCharts, slicers |
| Calculations | Excel formulas `[PLACEHOLDER]`, DAX measures `[PLACEHOLDER: if Power Pivot / data model used]` |
| Visualization | KPI cards, bar, line, donut, pie, and column charts |
| Domain skills | Transportation cost analysis, carrier performance, route analysis, capacity utilization |
| Analytical skills | Budget variance analysis, KPI design, data validation |

---

## 16. Project Structure

`[PLACEHOLDER: update to match your repository.]`

```text
transportation-logistics-optimization/
│
├── README.md
├── data/
│   ├── raw/                        # [PLACEHOLDER: raw dataset]
│   └── cleaned/                    # [PLACEHOLDER: cleaned dataset]
├── excel/
│   └── Transportation_Logistics_Dashboard.xlsx   # [PLACEHOLDER: file name]
├── images/
│   ├── dashboard_1_transportation_performance.png
│   ├── dashboard_2_carrier_route_optimization.png
│   ├── dashboard_3_vehicle_utilization_cost_saving.png
│   └── data_model.png              # [PLACEHOLDER]
└── docs/
    └── data_dictionary.md          # [PLACEHOLDER]
```

---

## 17. Data Validation Notes

The items below were found while reviewing the screenshots. Resolve them or document the reasons before publishing.

### 17.1 Metric Inconsistencies

| # | Issue | Evidence | Suggested Action |
|---|-------|----------|------------------|
| 1 | **On-time rate does not match the delivery status chart** | KPI shows 89.05%. The donut shows 993 on time of 1,200 (82.75%), or 993 of 1,160 excluding pending (85.60%). The average of the 12 carrier rates is also ~83%. | Confirm the formula and denominator. Correct the KPI or document the definition. |
| 2 | **"Lowest Cost per Shipment" (₹5,127)** | The lowest carrier-level cost per shipment in the bottom-right chart is ~₹22.5K. | Clarify whether ₹5,127 is a single-shipment minimum. Rename the KPI accordingly. |
| 3 | **Chart title does not match content** | "Carrier Cost vs On Time Delivery" shows a single "Total" series in ₹K and no on-time data. | Rename it, or plot cost and on-time rate together (e.g., scatter or combo chart). |
| 4 | **Status labels differ between dashboards** | Dashboard 1 uses "Pending" (40); Dashboard 3 uses "In Transit" (40). | Confirm whether these are the same shipments and standardize terms. |
| 5 | **Failed delivery rate not traceable** | 4.17% ≈ 50 of 1,200 shipments, but the status chart shows only 19 Returned. | Document which statuses or flags are counted. |
| 6 | **Average delay (29.03 hrs) vs. route transit gaps** | Route-level gaps shown are about 5–22 hours. | Clarify whether 29.03 is the average over delayed shipments only. |
| 7 | **Route cost variance (5.35%)** | Overall variance from the monthly chart is roughly 6%. | Document the scope (filtered vs. full dataset). |
| 8 | **Underutilization threshold undefined** | 621 shipments flagged, but the threshold is not stated. | Document the threshold (e.g., utilization below X%). |
| 9 | **"Excess cost" definition** | ₹1,962.9K matches actual minus budget only if "excess" means total overrun. | Document the formula. |

### 17.2 Slicer Behavior

Slicers on all three dashboards show single selections (e.g., Destination = Agra, Carrier_ID = CAR-01, Route_ID = RT-001), yet KPIs and charts still show full-dataset totals (e.g., 1,200 shipments, all 12 carriers, ₹36.87M total in the carrier chart). The slicers may not be connected to all PivotTables, or the screenshots may have been taken without active filters. **⚠️ Validate** slicer connections.

### 17.3 Chart and Formatting Issues

- Dashboard 1, monthly cost trend: months are in alphabetical order (Apr, Aug, Feb, ...). Sort chronologically.
- Dashboard 1 title and KPI typos: "Transportatin" (chart title) and "AVRAGE" (KPI label).
- Several data labels are cut off or overlap (QuickLoad and MetroLink on-time labels, 32ft SXL utilization, RT-010 actual transit label).
- On-time rate by route shows values such as 74.4 and 83.0 without a % sign.
- 3D column and bar charts make values harder to compare. Consider 2D charts.
- Currency formatting is mixed (₹ on some labels, none on KPI cards). Use one format.
- "Order_Date" slicer starts at 2026-01-01. Confirm whether October is a full month (it shows the lowest monthly cost).

### 17.4 Simulated Data and Estimates

- `[PLACEHOLDER: confirm whether the dataset is synthetic / simulated. If so, say so prominently at the top of this README.]`
- All savings figures are **scenario-based estimates** and should not be presented as realized or guaranteed savings.
- Figures taken from chart labels are rounded and may differ slightly from underlying values.

---

## 18. Dashboard Preview

> Replace the paths below with your actual image files.

### Dashboard 1: Transportation Performance Overview
![Transportation Performance Overview](images/dashboard_1_transportation_performance.png)

### Dashboard 2: Carrier & Route Optimization
![Carrier & Route Optimization](images/dashboard_2_carrier_route_optimization.png)

### Dashboard 3: Vehicle Utilization & Cost Saving
![Vehicle Utilization & Cost Saving](images/dashboard_3_vehicle_utilization_cost_saving.png)

---

## 19. Connect With Me

**Name:** `[PLACEHOLDER]`
**Role:** Supply Chain / Data Analyst
**LinkedIn:** `[PLACEHOLDER: link]`
**GitHub:** `[PLACEHOLDER: link]`
**Email:** `[PLACEHOLDER]`
**Portfolio:** `[PLACEHOLDER]`

---

⭐ If you found this project useful, consider giving the repository a star.
