# Credit Risk Analysis & ERM Monitoring Dashboard

## Business Context

When a bank extends credit to thousands of customers, it cannot review every account manually. It needs automated, data-driven systems to continuously monitor risk exposure, flag accounts showing early signs of distress, and report portfolio health to senior governance forums — before losses occur.

This project simulates exactly that workflow, replicating how an **Enterprise Risk Management (ERM)** team at a retail bank would monitor credit risk on a live portfolio.

---

## Dataset

UCI Credit Card Default Dataset — **30,000 real customer records** from a Taiwanese bank, with variables covering credit limits, payment history, bill amounts, and demographic information.

---

## What This Project Does

### 1. Data Quality Assessment
Identified and documented undocumented categorical codes in the raw data (education levels 0, 5, 6 and marriage code 0 absent from the official data dictionary) — flagged and cleaned before analysis, mirroring internal audit standards.

### 2. Portfolio Risk Segmentation
Segmented the portfolio by credit limit band, age group, and education level to identify which sub-portfolios carry disproportionate default risk.

### 3. Risk Appetite Monitoring
Defined four risk appetite thresholds (portfolio default rate, average credit utilisation, chronic delinquency rate, and segment-level default rate) and built an automated monitoring engine that compares actuals against thresholds and flags breaches for escalation.

| Metric | Threshold | Status |
|--------|-----------|--------|
| Portfolio Default Rate | ≤ 25% | 🟢 Within |
| Avg Credit Utilisation | ≤ 0.80 | 🔴 Breach |
| Chronic Delinquency Rate | ≤ 10% | 🔴 Breach |
| Segment Default Rate | ≤ 35% | 🟢 Within |

### 4. Automated Account-Level Flagging
Built a rule-based flagging engine that tags individual accounts with risk flags (`OVER_LIMIT`, `CHRONIC_DELINQUENT`, `RECENT_DELAY`, `HIGH_BILL_LOW_PAYMENT`) — replicating how operational risk teams identify accounts for review.

### 5. Automated Report Export
Generated a structured Excel report with three sheets — Portfolio Summary, Segment Risk Analysis, and Flagged Accounts — ready to share with a governance committee.

---

## Key Findings

- Credit utilisation ratio breaches the risk appetite threshold and is a strong leading indicator of default — defaulted accounts show significantly higher utilisation than non-defaulted ones.
- The lowest credit limit band (<50K) carries the highest default rate, suggesting concentration risk in lower-income borrowers.
- Chronic delinquency (3+ consecutive missed payments) affects more than 10% of the portfolio, breaching the early warning threshold and warranting immediate escalation.

---

## Tools & Libraries

Python · Pandas · NumPy · Matplotlib · Seaborn · OpenPyXL

---

## Files in This Repo

| File | Description |
|------|-------------|
| `credit_risk_analysis.ipynb` | Full analysis notebook with commentary |
| `chart_1_default_overview.png` | Portfolio default split & default rate by education |
| `chart_2_risk_heatmap.png` | Default rate heatmap: age group × credit limit band |
| `chart_3_payment_behaviour.png` | Missed payments distribution & credit utilisation boxplot |
| `chart_4_risk_appetite.png` | Risk appetite monitoring dashboard |
| `credit_risk_monitoring_report.xlsx` | Automated governance report (3 sheets) |

---

**Author:** Anika | B.A. Economics (Hons.), Kamala Nehru College, Delhi University
