# Solar Power Plant — Anomaly Detection & Performance Analysis

**End-to-end Data Science project** · Python · Pandas · Time-series · IoT/Sensor data · Business Case

---

## Overview

A solar energy company detected recurring anomalous behaviour across two photovoltaic plants (P1 and P2) that the maintenance subcontractor could not diagnose. The Data Science team was engaged to analyse 34 days of sensor and inverter data — identifying the root cause before any costly field engineering deployment.

**Pipeline:** raw data ingestion → data quality audit → feature engineering → EDA → anomaly detection → executive business case with ROI projection.

---

## Key Results

| Metric | Value |
|--------|-------|
| Anomalies detected | **756 events** (95.5% critical) |
| Inverters requiring urgent intervention | **24 / 44** |
| Generation loss detected (25-day window) | **49,439 kWh** |
| Estimated annual revenue loss (AS-IS) | **€50,504 / year** |
| Projected annual benefit (TO-BE) | **€58,903 / year** |
| ROI payback period | **12–18 months** |

Plant 2 accounts for **87% of all anomalies**, concentrated in 4 specific inverters.

---

## Tech Stack

`Python 3` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `Jupyter Notebooks`

---

## Project Structure

```
├── notebooks/
│   ├── 01_ImportacionDatos.ipynb       # Data ingestion & quality audit
│   ├── 02_PreparacionVariables.ipynb   # Feature engineering & KPI creation
│   └── 03_AnalisisInsights.ipynb       # EDA, anomaly detection & business case
├── datos/
│   ├── brutos/          # Raw CSVs (2 plants × generation + sensors)
│   ├── intermedios/     # Analytical tables (.pkl)
│   └── procesados/      # Final anomaly output (.csv)
├── docs/                # Data dictionary, quality report, project objectives
└── entregables/informes/  # Executive report + anomaly summary
```

> Notebooks must be run sequentially — each produces intermediate files consumed by the next.

---

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

---

## Business Impact

| | AS-IS | TO-BE | Δ |
|---|---|---|---|
| Annual generation loss | 721,485 kWh | 144,297 kWh | **−80%** |
| Annual revenue loss | €50,504 | €10,101 | **−80%** |
| Fault detection time | >15 days | <24 hours | **−95%** |

---


