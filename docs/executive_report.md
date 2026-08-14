# Executive Report — Solar Plants P1 & P2 Performance Analysis

**Analysis period:** 15 May – 17 Jun (34 days, 15-minute sensor windows) · **Scope:** 42 operational inverters (P1: 20 · P2: 22)

---

## 1. The Problem

Plants P1 and P2 show recurring anomalous behaviour that the maintenance subcontractor has been unable to diagnose.

| Operational context | Value |
|---|---|
| Fault detection lag | > 15 days after the event |
| Diagnosis method | 100% manual, no prioritisation |
| Maintenance model | Reactive, no preventive capacity |

## 2. Key Findings

| Metric | Value |
|---|---|
| Anomalies detected | 756 (95.5% critical — power = 0) |
| Inverters affected | 44 (24 require urgent intervention) |
| Generation loss (25-day window analysed) | 49,439 kWh |
| Anomalies concentrated in Plant 2 | 87% |

**Key finding:** 66% of failures occur during productive hours (9am–5pm) → direct, immediate revenue loss.

## 3. Technical Diagnosis

Three behavioural patterns identified:

| # | Pattern | Share | Severity | Action |
|---|---|---|---|---|
| 1 | Automatic dusk shutdown | 33.6% | Low | None — normal behaviour from low irradiation at 18:00 |
| 2 | Productive-hour failures | 66% | High | Total disconnections 9am–5pm; power drops >70% vs. adjacent hours. Direct economic loss |
| 3 | Recurrent inverter failures (24 units) | — | Critical | Repeated faults across multiple days; likely hardware degradation. Requires repair/replacement |

## 4. Estimated Economic Impact (AS-IS)

| Concept | Annual value |
|---|---|
| Generation loss | 721,485 kWh/year |
| Revenue loss | €50,504/year |
| Impact on expected profitability | −3–5% |

| Current operating costs | Annual cost |
|---|---|
| Lost revenue from failures | €50,504 |
| Reactive maintenance | €15,000 |
| Manual diagnosis | €8,000 |
| Unnecessary site visits | €5,000 |
| **Total** | **€78,504** |

*Average electricity price used: €0.07/kWh*

## 5. Proposed Solution (TO-BE)

**Predictive monitoring & proactive maintenance system**

- **Real-time analytics platform** — automatic anomaly detection, per-inverter dashboard, severity-based alerts
- **Predictive maintenance programme** — immediate inspection of the 24 critical inverters, quarterly preventive maintenance, scheduled replacement of degraded equipment
- **Smart alerting** — fault detection in <24h (vs. >15 days today), automatic prioritisation by economic impact, direct integration with the maintenance team

## 6. Expected Benefits

| Metric | AS-IS | TO-BE | Improvement |
|---|---|---|---|
| Generation loss (kWh/year) | 721,485 | 144,297 | −80% |
| Revenue loss (€/year) | 50,504 | 10,101 | −80% |
| Fault detection time | > 15 days | < 24 hours | −95% |
| Unattended critical inverters | 24 | 0 | −100% |

| Source of value | Annual benefit |
|---|---|
| Reduced generation losses | €40,403 |
| Reduced reactive maintenance | €9,000 |
| Diagnosis optimisation | €6,000 |
| Reduced site visits | €3,500 |
| **Total** | **€58,903** |

## 7. Investment & Costs

| Initial investment (Year 0) | Cost |
|---|---|
| Software platform (3-year licence) | €18,000 |
| Integration with existing systems | €8,000 |
| Additional hardware (sensors) | €4,000 |
| Inspection + repair of 24 inverters | €21,000 |
| Training & consulting | €5,000 |
| **Total investment** | **€56,000** |

| Annual operating cost (Years 1–3) | Cost/year |
|---|---|
| Software licence + support | €6,000 |
| Quarterly preventive maintenance | €8,000 |
| Data analyst (20% dedication) | €10,000 |
| Minor spares & repairs | €3,000 |
| **Total annual** | **€27,000** |

## 8. ROI & Financial Metrics

Net annual benefit = €58,903 − €27,000 = **€31,903/year**

| Metric | Value |
|---|---|
| NPV (3 years, 8% discount rate) | €29,847 |
| IRR | 38.5% |
| Payback period | 1.75 years (~21 months) |
| Cumulative ROI (3 years) | 75% |

*Benefit projection includes a +2%/year increase in energy price.*

## 9. Recommendation

**Recommended decision: approve the project.** A 38.5% IRR and a payback period under 2 years justify immediate approval.

**Approval conditions**
- Phased rollout, starting with a pilot on Plant 2
- Review at month 3 to validate results
- Budget: €56,000 + 10% contingency
- Minimum target: 70% anomaly reduction within 6 months

**Immediate next steps**

| Action | Owner | Timeline |
|---|---|---|
| Budget approval | CFO | 1 week |
| Vendor tender | Procurement | 2 weeks |
| Critical inverter inspection | Maintenance | 1 month |
| Implementation kick-off | Project Manager | 1 month |

**Cost of inaction:** continuing to lose ~€50,000/year indefinitely.

---
*This report summarises the business case derived from the exploratory analysis in [`notebooks/03_AnalisisInsights.ipynb`](../notebooks/03_AnalisisInsights.ipynb).*
