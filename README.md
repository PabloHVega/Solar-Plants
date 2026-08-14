# Solar Power Plant — Anomaly Detection & Performance Analysis

**End-to-end Data Science project** · Python · Pandas · Time-series · IoT/Sensor data · Business Case

---

## Overview

A solar energy company detected recurring anomalous behaviour across two photovoltaic plants (P1 and P2) that the maintenance subcontractor could not diagnose. This project analyses 34 days of sensor and inverter data to find the root cause and quantify the business case for fixing it — before any costly field engineering deployment.

**Pipeline:** raw data ingestion → data quality audit → feature engineering → EDA → anomaly detection → executive business case with ROI projection.

## Highlights

- **756 anomalies** detected across 44 inverters (95.5% critical), 66% occurring during productive hours
- **€50,504/year** in preventable revenue loss identified
- Proposed fix: **38.5% IRR**, payback in **1.75 years**

📄 **[Read the full executive report →](docs/executive_report.md)** for the technical diagnosis, economic impact, investment plan and ROI breakdown.

---

## Tech Stack

`Python 3` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `Jupyter Notebooks`

## Project Structure

```
├── notebooks/
│   ├── 01_ImportacionDatos.ipynb       # Data ingestion & quality audit
│   ├── 02_PreparacionVariables.ipynb   # Feature engineering & KPI creation
│   └── 03_AnalisisInsights.ipynb       # EDA, anomaly detection & business case
├── datos/                # Raw, intermediate and processed data (not versioned)
└── docs/                 # Data dictionary, quality report, project objectives, executive report
```

> Notebooks must be run sequentially — each produces intermediate files consumed by the next.

## What Was Done

**Notebook 1 — Data Quality Audit**
- Detected and corrected a systematic 10× decimal error in Plant 1 DC power values
- Documented 105 missing time intervals in Plant 1 vs. 4 in Plant 2
- Flagged 4 inverters in Plant 2 with disproportionate data loss

**Notebook 2 — Feature Engineering**
- Engineered `inverter_efficiency (%)` = `ac_power / dc_power × 100` with proper edge-case handling
- Built unified analytical table merging generation and sensor data across both plants

**Notebook 3 — EDA & Anomaly Detection**
- Time-series analysis of DC/AC power and irradiation across plants
- Rule-based anomaly detection: zero-power events + drops >70% vs. adjacent hourly windows
- Classified anomalies: normal dusk shutdowns (33.6%) vs. productive-hour failures (66%)
- Full AS-IS / TO-BE business case with 3-year ROI model

