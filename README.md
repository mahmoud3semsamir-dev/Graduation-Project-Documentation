# 📊 LTE Network Performance Analysis & Capacity Estimation via Power BI

This repository contains the data analytics framework, data engineering steps, and custom **DAX formulations** developed for our graduation project. The core objective is to evaluate and compare cellular network Key Performance Indicators (KPIs) across diverse geographical regions (**Urban, Rural, and Highway**) and theoretically model node capacity using **Shannon's Theorem**.

---

## 🛠️ Project Architecture & Data Schema

The dataset captures live drive-test metrics segregated into three main environments:
1. **Urban Data**: High-density zones prone to multi-path fading and interference.
2. **Rural Data**: Low-density areas where signal coverage boundaries are tested.
3. **Highway Data**: High-mobility environments highlighting fast handover and Doppler effects.

### Core Tracked Parameters:
* `Operator` & `Technology` (4G/LTE)
* `EARFCN` (Absolute Radio Frequency Channel Number)
* `RSRP` (Reference Signal Received Power, measured in $dBm$)
* `RSSI` (Received Signal Strength Indicator, measured in $dBm$)
* `RSRQ` (Reference Signal Received Quality, measured in $dB$)
* `SINR` (Signal-to-Interference-plus-Noise Ratio, measured in $dB$)
* `Timing Advance (TA)` (Metric mapping user distance to the eNodeB)

---

## 🚀 Step-by-Step Implementation Guide

---<p align="center">
  <img src="./images/Screenshot 2026-07-09 032854.png" width="750">
</p>


### Phase 1: Data ETL & Transformation (Power Query)
1. **Ingestion**: Import the dataset sheets into **Power BI Desktop** using the *Get Data* module.
2. **Data Profiling**: In **Power Query Editor**, ensure categorical data types are set to `Text` and RF parameters (`RSRP`, `RSSI`, `RSRQ`, `SINR`) are typed as `Whole/Decimal Numbers`.
3. **Data Unification (Recommended)**: Append the three regional tables (`Urban`, `Rural`, `Highway`) using the **Append Queries** feature into a single unified model table named `All_Network_Data` for robust cross-regional comparison.

---<p align="center">
  <img src="./images/Screenshot 2026-07-09 034859.png" width="750">
</p>



### Phase 2: Advanced DAX Calculations
> ⚠️ **Engineering Note:** RF metrics like **SINR** ($dB$) and **RSRP** ($dBm$) are logarithmic values. Calculating their standard arithmetic average directly generates mathematically invalid results. They must be mapped back to a **Linear Scale** before statistical pooling.

## 🔢 Implementation Steps for Custom KPI Calculations

To implement the exact calculations utilized in our system dashboard (such as the `Max_SINR_Linear` metrics), follow these sequential procedures inside the Power BI Desktop workspace:

### Step 1: Formulating the Logarithmic-to-Linear Metric
1. Navigate to the **Data** pane on the right side of the interface.
2. Right-click on the consolidated dataset table named `Append1` and select **New Measure**.
3. In the formula bar at the top, inject the custom DAX expression using the `MAXX` iterator to map the raw values back to a proper linear amplitude scale before calculating the upper bound peak:

```dax
Max_SINR_Linear = 
MAXX(
    'Append1', 
    POWER(10, 'Append1'[SINR] / 10)
)
```
---<p align="center">
  <img src="./images/Screenshot 2026-07-09 064530.png" width="750">
</p>

### Step 2: Formulating and Deploying the Maximum Logarithmic SINR Metric

To capture the absolute peak logarithmic Signal-to-Interference-plus-Noise Ratio ($dB$) without linear translation for comparative environment analysis, follow these steps:

1. **Creating the Logarithmic Measure**:
   * Right-click on the consolidated `Append1` table in the **Data** pane and select **New Measure**.
   * In the DAX formula bar, enter the following absolute maximum expression:
   ```dax
   Max_SINR_dB = MAX('Append1'[SINR])


---<p align="center">
  <img src="./images/Screenshot 2026-07-09 071239.png" width="750">
</p>


