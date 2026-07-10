
# 📊 LTE Network Performance Analysis & Capacity Estimation via Power BI
An advanced telecommunications data analytics framework developed as an Engineering Graduation Project. This repository contains the complete end-to-end data engineering pipeline, custom **DAX formulations**, and multi-dimensional visualization dashboards designed to evaluate and compare 4G LTE Key Performance Indicators (KPIs) across diverse geographical environments (**Urban, Rural, and Highway**) using real-world Drive Test telemetry.

---

## 🏛️ Academic Profile

* **Institution:** Menofia University, Faculty of Electronic Engineering
* **Department:** Electronics and Electrical Communications Engineering
* **Academic Year:** 2025 – 2026
* **Project Advisor:** Prof. Dr. Saied M. Abd El-atty

---

## 👥 Project Team & Contributors

This project was successfully designed and executed by the following researchers:

* **Mahmoud Asem Samir Riad**
* **Mohamed Ali Said**
* **Ziad Ashraf El-Sayed**
* **Anas Essam El-Sayed**
* **Mohamed Yasser Mohamed**
* **Azza Yasser Abdel-Moati**
* **Salma Allam Mostafa**

---

## 🎯 Project Objectives & Concept

The core objective of this project is to bridge the gap between raw cellular telemetry data and actionable Radio Frequency (RF) optimization intelligence. By conducting statistical drive-test parsing, the framework allows engineers to:
* Evaluate spectral efficiency, latency constraints, and throughput capacities.
* Benchmark comparative operator standings (Vodafone, Etisalat, WE) across multiple operational bands (1800, 2100, 2500 MHz).
* Analyze structural channel degradation caused by physical environment constraints (Shadowing in Urban cores, high Doppler shifts on Highways, and severe Path Loss boundaries in Rural zones).

---
### 4G-LTE-Network-Performance-Analyzer

This repository contains the data analytics framework, data engineering steps, and custom **DAX formulations** developed for our graduation project. The core objective is to evaluate and compare cellular network Key Performance Indicators (KPIs) across diverse geographical regions (**Urban, Rural, and Highway**) and theoretically model node capacity using **Shannon's Theorem**.

---

## 🛠️ Project Architecture & Data Schema

The dataset captures live drive-test metrics segregated into three main environments:
1. **Urban Data**: High-density zones prone to multi-path fading and interference.
2. **Rural Data**: Low-density areas where signal coverage boundaries are tested.
3. **Highway Data**: High-mobility environments highlighting fast handover and Doppler effects.

## 🛠 Project Architecture & Data Schema

The dataset contains three environments:

1. Urban Data
2. Rural Data
3. Highway Data

### Core Parameters

- Operator
- Technology (4G/LTE)
- EARFCN
- RSRP
- RSSI
- RSRQ
- SINR
- Timing Advance (TA)

---

## 🚀 Step-by-Step Implementation Guide

### Phase 1: Data ETL & Transformation (Power Query)

1. Import the Excel dataset into Power BI Desktop.
2. Open **Power Query Editor**.
3. Verify data types.
4. Append Urban, Rural, and Highway tables into one table named **Network Data**.
5. Click **Close & Apply**.

> Add your first screenshot here:

---<p align="center">
  <img src="./images/Screenshot 2026-07-09 033816.png" width="750">
</p>
---

### Phase 2: Create DAX Measures

#### Average KPIs

```dax
Avg_RSRP = AVERAGE('Network Data'[RSRP])

Avg_RSRQ = AVERAGE('Network Data'[RSRQ])

Avg_SINR = AVERAGE('Network Data'[SINR])

Avg_RSSI = AVERAGE('Network Data'[RSSI])
```

#### Maximum KPIs

```dax
Max_SINR = MAX('Network Data'[SINR])

Max_SINR_Linear = MAX('Network Data'[SINR_Linear])
```

#### Minimum KPI

```dax
Min_RSRP = MIN('Network Data'[RSRP])
```

#### Count KPIs

```dax
Count_Cell_ID = DISTINCTCOUNT('Network Data'[Cell ID])

Count_eNB_ID = DISTINCTCOUNT('Network Data'[eNB ID])
```

---

## 📂 Organizing Measures

Open **Model View** and set the **Display Folder** of all measures to:

```text
_All Measures
```

---

## 📊 Dashboard KPIs

| KPI | Measure |
|------|----------|
| Average RSRP | Avg_RSRP |
| Average RSRQ | Avg_RSRQ |
| Average SINR | Avg_SINR |
| Average RSSI | Avg_RSSI |
| Maximum SINR | Max_SINR |
| Maximum SINR Linear | Max_SINR_Linear |
| Minimum RSRP | Min_RSRP |
| Count Cell ID | Count_Cell_ID |
| Count eNB ID | Count_eNB_ID |

---

## 📊 Dashboard 1:

- KPI Cards
- Clustered Column Charts
- Scatter Charts
- Operator Slicer
- Environment Slicer
- Coverage Analysis

> Add your dashboard screenshot here:

---<p align="center">
  <img src="./images/Screenshot 2026-07-09 193351.png" width="750">
</p>

---
An interactive performance analysis dashboard for evaluating 4G LTE mobile network coverage and capacity using field measurements. This project focuses on analyzing Key Performance Indicators (KPIs) such as **RSRP**, **RSRQ**, and **SINR** to assess network quality and optimize cellular coverage.

## 📊 Dashboard Overview

The dashboard provides a visual analytics suite divided into two primary analytical dimensions: **Correlation Analytics** (Scatter Plots) and **Cell Ranking & Trends** (Line Charts).

### 1. Correlation Analytics (Scatter Plots)
Located on the left side of the dashboard, these charts plot individual Base Stations (**eNB IDs**) to identify underlying mathematical and physical relationships between different signal metrics.

* **Avg_RSRP vs. Avg_SINR by eNB ID:** Analyzes how raw signal strength impacts the signal-to-noise ratio. It helps identify interference-limited zones where signal strength is high but quality is poor.
* **Avg_RSRP vs. Avg_RSRQ by eNB ID:** Evaluates the relationship between signal power and overall received quality, factoring in thermal noise and loading.
* **Interpretation of Dots:** Each distinct white dot represents a specific network node or measurement point. The spatial distribution (scattering) reveals environmental path loss behaviors and network performance clustering.

### 2. Cell Performance & Ranking (Line Charts)
Located on the right side of the dashboard, these charts aggregate metrics across specific **Cell IDs** to identify peak performers and worst-performing cells (Top/Bottom KPIs).

* **Avg_RSRP by Cell ID:** Displays the average Reference Signal Received Power across filtered cells, sorted sequentially.
* **Avg_SINR by Cell ID:** Displays the Signal-to-Interference-plus-Noise Ratio to isolate cells suffering from pilot pollution or heavy environmental degradation.
* **Interpretation of Lines:** The continuous line connects discrete cell metrics to form a trend gradient. The downward slope indicates a sorted degradation profile, allowing RF engineers to instantly pinpoint underperforming sectors that require immediate optimization or physical tilt adjustments.

## 🛠 Technologies Used

- Microsoft Power BI Desktop
- Microsoft Excel
- Power Query
- DAX

---



# 🎯 Project Objective

The objective of this project is to evaluate and visualize the performance of a 4G LTE mobile network using real drive test measurements. The dashboard enables users to monitor signal strength, signal quality, interference levels, and network coverage through interactive Power BI visualizations.
# 📖 About the Project

The **4G LTE Network Performance Dashboard** is an interactive Power BI project designed to analyze and visualize LTE drive test data. It helps evaluate the performance and quality of a mobile network by transforming raw measurement data into meaningful insights through interactive dashboards.

The dashboard allows users to:

- Monitor key LTE performance indicators (KPIs).
- Analyze signal strength using **RSRP**.
- Evaluate signal quality using **RSRQ**.
- Measure network quality using **SINR**.
- Analyze total received signal power using **RSSI**.
- Count the total number of unique **Cell IDs** and **eNB IDs**.
- Compare network performance across different mobile operators.
- Analyze performance under different environments such as **Urban**, **Rural**, and **Highway**.
- Filter data dynamically using interactive slicers.
- Display real-time KPI cards and charts that update automatically based on user selections.

The project is built using **Microsoft Power BI**, **Power Query**, and **DAX** to provide an easy-to-use and interactive dashboard for LTE network performance evaluation.


# 📊 Dashboard 2 :

The final dashboard provides an interactive and comprehensive overview of 4G LTE network performance by transforming raw drive test data into meaningful visual insights. It enables users to evaluate network coverage, signal quality, and overall performance through dynamic charts, KPI cards, and interactive filters.

The dashboard allows users to:

- Monitor key performance indicators (KPIs) such as **RSRP**, **RSRQ**, **RSSI**, and **SINR**.
- Display the maximum, minimum, average, and unique counts of important network metrics.
- Compare network performance across different environments (**Urban, Rural, and Highway**).
- Compare mobile network operators using interactive slicers.
- Analyze signal strength and signal quality through multiple visualizations.
- Identify weak coverage areas and potential network performance issues.
- Support network optimization and decision-making using interactive Power BI reports.

Overall, the dashboard provides a user-friendly platform for analyzing LTE network performance, helping engineers quickly identify trends, evaluate network quality, and improve coverage efficiency.

---<p align="center">
  <img src="./images/Screenshot 2026-07-09 195237.png" width="750">
</p>


## 📊 Dashboard 3: Link Capacity & Timing Advance Analysis

This section of the dashboard evaluates network throughput performance (**Link Capacity**) against signal quality (**SINR**) and geographical distance proxies (**Timing Advance**). It also provides a benchmark comparison across multiple network operators.

### 1. Throughput & Quality Correlation (Top Left)
* **Chart:** `Avg_SINR and Link_Capacity_Mbps by eNB ID` (Scatter Plot)
* **Description:** Plots link capacity against signal quality ($SINR$) for each base station ($eNB\ ID$).
* **Insight:** Demonstrates a clear positive linear correlation. As $SINR$ improves (moving right), the $Link\_Capacity$ increases significantly (moving up), proving that higher channel quality directly yields higher data throughput due to advanced modulation schemes (e.g., 64QAM/256QAM).

### 2. Operator Benchmarking (Top Right)
* **Chart:** `Link_Capacity_Mbps by Operator` (Bar Chart)
* **Description:** A categorical comparison of the average link capacity delivered by different service providers (**Etisalat, WE, and Vodafone**).
* **Insight:** Allows RF planners to benchmark network competitive performance and analyze market capacity standing under identical environment filters.

### 3. Distance vs. Quality Analysis (Bottom Left)
* **Chart:** `Average of Timing Advance and Avg_SINR by eNB ID` (Scatter Plot)
* **Description:** Analyzes the impact of **Timing Advance (TA)**—which represents the distance between the user equipment and the cell tower—on the signal quality ($SINR$).
* **Insight:** Typically illustrates how signal quality degrades or experiences higher interference variations as the propagation distance ($Timing\ Advance$) increases.

### 4. Distance vs. Signal Strength Analysis (Bottom Right)
* **Chart:** `Average of Timing Advance and Avg_RSRP by eNB ID` (Scatter Plot)
* **Description:** Maps **Timing Advance (TA)** against the raw received power ($Avg\_RSRP$).
* **Insight:** Visualizes free-space path loss. As the $Timing\ Advance$ value grows larger (User is farther from the eNB), the $RSRP$ values naturally drop lower (closer to -80 dBm or worse), helping identify the effective coverage radius of the serving sectors.

---

## 🔑 Additional Telecommunication Metrics Defined

| Metric | Full Name | Description | Engineering Relevance |
| :--- | :--- | :--- | :--- |
| **Link Capacity** | Link Capacity (Mbps) | The maximum achievable data rate over the radio link. | Directly maps to user experience, download speeds, and spectral efficiency. |
| **Timing Advance** | Timing Advance (TA) | A signal used by the eNB to control the timing of uplink transmissions from the UE. | Acts as a direct proxy for the physical distance between the user and the base station ($1\ TA \approx 78 \text{ meters}$). |


---<p align="center">
  <img src="./images/Screenshot 2026-07-10 033059.png" width="750">
</p>

## 📊 Dashboard 4 : Environmental Performance Analysis

This section analyzes how different operational environments (**Urban, Highway, and Rural**) physically impact cellular distribution, signal attenuation, quality degradation, and overall capacity.

### 1. Cellular Distribution (Top Left)
* **Chart:** `Count of Cell ID by Environment` (Donut Chart)
* **Description:** Displays the percentage and count of serving cells active within each specific environment category.
* **Insight:** Identifies the geographical focus of the drive test or deployment. In this scenario, **Highway** sectors hold the majority share (56.25% with 9 cells), followed by **Urban** (25%), and **Rural** (18.75%).

### 2. Capacity by Environment (Middle Left)
* **Chart:** `Link_Capacity_Mbps by Environment` (Bar Chart)
* **Description:** Compares the average maximum data rate achieved across the different test zones.
* **Insight:** Shows that **Urban** and **Highway** environments yield the highest throughput, while **Rural** areas experience a noticeable drop in link capacity, likely due to lower allocated bandwidth or fallback to basic modulation profiles.

### 3. Total Received Energy (Bottom Left)
* **Chart:** `Avg_RSSI by Environment` (Bar Chart)
* **Description:** Represents the average Received Signal Strength Indicator ($RSSI$), which accounts for the total power received including standard reference signals, serving traffic, and background thermal noise/interference.

### 4. Channel Quality Benchmarks (Right Column)
* **Charts:** `Avg_SINR by Environment`, `Avg_RSRQ by Environment`, and `Avg_RSRP by Environment` (Bar Charts)
* **Description:** Three aligned categorical bar charts tracking signal quality ($SINR$), quality relative to noise ($RSRQ$), and pure reference signal strength ($RSRP$) across the environment spectrum.
* **Insight:** Provides a clear diagnostic look at physical channel behavior:
  * **Urban & Highway:** Retain higher $SINR$ performance, allowing for more stable connections and better spectral efficiency.
  * **Rural:** Exhibits significant degradation in $SINR$ and $RSRP$ (becoming more negative), pinpointing areas suffering from heavy path loss due to long-distance propagation away from the nearest base station.

  ---<p align="center">
  <img src="./images/Screenshot 2026-07-10 034022.png" width="750">
</p>

## 💡 Engineering Recommendations & Insights

Based on the multi-dimensional analysis conducted across the three dashboards, the following optimization strategies are recommended for network performance enhancement:

1. **Rural Coverage Bootstrapping:** Since Rural environments exhibit severe path loss (highly negative $RSRP$) and heavily degraded $SINR$, it is critical to deploy low-frequency bands (e.g., $800\text{ MHz}$) to exploit better propagation characteristics, or implement active Antenna Tilting (electrical/mechanical down-tilt adjustments) to maximize cell boundary gains.
2. **High-Mobility Handover Optimization:** For Highway tracks (which contain 56.25% of the cell distribution), mobility parameters such as *Time-to-Trigger (TTT)* and *Hysteresis margins* must be tightly tuned to eliminate ping-pong handovers and maintain stable $Link\_Capacity$.
3. **Interference Mitigation in Urban Clusters:** In high-density Urban sectors where $RSRP$ is adequate but $SINR$ drops, physical optimization via sector re-orientation or adjusting pilot power allocation is required to eliminate co-channel interference and pilot pollution.

---

## 🎯 Conclusion

This framework successfully bridges the gap between raw drive-test telemetry and actionable RF engineering intelligence. By translating standard telecom indicators ($RSRP, RSRQ, RSSI, SINR$) into dynamic Power BI visualizations, network operators can seamlessly diagnose coverage holes, benchmark competitor performance, and mathematically map achievable link capacities via Shannon's Theorem.

