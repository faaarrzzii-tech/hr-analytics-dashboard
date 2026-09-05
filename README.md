# HR Analytics Dashboard

An HR analytics dashboard built on top of the companion project
[`sap-hcm-employee-data-`](https://github.com/faaarrzzii-tech/sap-hcm-employee-data-),
turning the mock SAP HCM employee dataset into decision-ready metrics — the
kind an HR Business Partner or People Analytics function would track monthly.

> **Background:** MBA in Human Resources, SAP HCM Certified. This project
> demonstrates the ability to turn HRIS data into metrics leadership actually
> uses, not just a static employee list.

## What's inside

`HR_Analytics_Dashboard.xlsx` — one workbook, live formulas (no hardcoded
numbers — every metric recalculates if the underlying employee data changes):

| Metric | What it shows | Why it matters |
|---|---|---|
| Active Headcount | Current active employee count | Baseline for every other metric |
| Attrition Rate (Trailing 12 Months) | Exits in the last 12 months ÷ current active headcount | Core retention health indicator |
| Headcount by Department | Active employees per department (chart included) | Shows where the org is top- or bottom-heavy |
| Average Tenure (Years) | Mean tenure of active employees | Signals retention strength / flight risk |
| Average Leave Utilization | % of leave entitlement actually used | Surfaces burnout risk (very low) or planning gaps (very high) |
| Gender Diversity (Active) | Active headcount split by gender (chart included) | Standard DEI reporting baseline |

## Data model extension

The original dataset didn't include employment status or exit dates, so a
real attrition metric wasn't calculable — this project adds:
- **Employment Status** (`Active` / `Terminated`) to `Personnel_Administration`
- **Exit Date** for terminated employees

~12% of the 120 mock employees are marked `Terminated` with plausible exit
dates, so the attrition calculation is genuine, not illustrative.

## Why formulas, not static numbers

Every dashboard cell is a live formula referencing the source data sheets
(`Personnel_Administration`, `Organizational_Assignment`, `Time_Management`).
This means the dashboard **recalculates automatically** if employee records
change — the same principle behind any real HRIS reporting layer, and a
detail that shows the difference between "filled in numbers" and an actual
working model.

## Design choices

- **Trailing 12-month attrition window** — a standard HR reporting period,
  rather than lifetime attrition, which would understate current risk.
- **Charts limited to two** (department headcount bar chart, gender pie
  chart) — enough to demonstrate visualization without cluttering a one-page
  dashboard.
- All data remains **entirely fictional**, generated for demonstration
  purposes only.

## Possible next steps

- Add a headcount trend over time (hires vs. exits by month).
- Break attrition down by department to spot high-risk teams.
- Add a cost-center-level compensation summary from `Payroll_Basics`.

---
*Built by Buddy — MBA (HR), SAP HCM Certified.*
