# Work Breakdown Structure — OEE Dashboard Project

## Total Project Effort

- **Total hours:** 530 hours across 6 role types
- **Personnel cost estimate:** 15,801 EUR
- **Cost basis:** Average market salaries for IT working students in Bavaria,
  25% surcharge for non-wage labor costs, 40% surcharge for student
  recruitment and administration

---

## Work Package Overview

| Work Package | Owner | Jira Tickets | Hours (estimated) |
|---|---|---|---|
| WP1: Project Management and Documentation | Muhammad Awais (sole) | KAN-1, KAN-2 | 80 hrs |
| WP2: Data Engineering | Zohaib Sultan + Muhammad Awais | KAN-3, KAN-5, KAN-8, KAN-4 | 240 hrs combined |
| WP3: Business Intelligence Frontend | Kashif Sultan + Muhammad Awais | KAN-7, KAN-9, KAN-10, KAN-12 | 120 hrs combined |
| WP4: Quality Assurance and Logic | Muhammad Awais (sole) | KAN-6, KAN-11 | 70 hrs |

---

## WP1: Project Management and Documentation
**Owner:** Muhammad Awais (sole owner)

**Responsibilities:**
- Wrote the project charter and defined four milestone releases
- Configured and led the Kanban board in Jira as project lead
- Wrote all ticket descriptions — actionable without requiring follow-up meetings
- Managed milestone tracking and release versioning in Jira
- Delivered the final stakeholder presentation (KAN-1)
- Produced the project documentation and written report (KAN-2)

**Key output:** Four milestone releases delivered on schedule. Project report
and final presentation completed by December 4, 2025.

---

## WP2: Data Engineering
**Owner:** Zohaib Sultan (lead) + Muhammad Awais (co-owner)

**Responsibilities:**
- Dataset exploration and import into the data model (KAN-3)
- Synthetic machine data generation to simulate production floor inputs (KAN-5)
- Data cleaning and validation before Power BI ingestion (KAN-8)
- Star Schema data model design — 8 tables, 2 fact tables, 6 dimensions (KAN-4)

**Key output:** A validated Star Schema data model connecting production logs,
downtime records, and scrap data. Synthetic data pipeline enabling DAX
validation before live sensor connection.

**Why synthetic data was built:**
See decisions.md Decision 2. The two highest-priority risks in the project
both resided in this work package. Synthetic data with known ground-truth
values was the only way to isolate DAX formula errors from sensor data
quality problems.

---

## WP3: Business Intelligence Frontend
**Owner:** Muhammad Awais (co-owner) + Kashif Sultan (co-owner)

**Responsibilities:**
- Corporate Identity canvas setup across all dashboard pages (KAN-7)
- Four dashboard panel creation: Overview, Availability, Performance,
  Quality (KAN-9)
- Trend and historical visualization development (KAN-10)
- UI refinement and design polish based on Milestone 3 review (KAN-12)

**Key output:** Three fully validated dashboard pages with consistent
Corporate Identity. Overview page designed for supervisor workflow.
Availability and Performance pages designed for maintenance engineer
and line manager workflow.

---

## WP4: Quality Assurance and Logic
**Owner:** Muhammad Awais (sole owner)

**Responsibilities:**
- Developed all core DAX measures: Availability Net, Availability Gross,
  Performance, Quality, OEE, OEE Net (KAN-6)
- Ran OEE calculation validation against the plus or minus 3 percent
  accuracy target (KAN-11)

**Key output:** Validated DAX measures producing OEE calculations accurate
to within the defined target. Validation completed against synthetic data
with known ground-truth values before live data connection.

**Why this work package mattered most:**
OEE data is used for real operational decisions. A 5% error in the
Availability calculation changes maintenance scheduling priorities.
Accuracy validation was not a quality-of-life improvement — it was the
core deliverable that made the dashboard trustworthy enough to use.

---

## Staff Cost Matrix

| Role | Level | Base Rate | Loaded Rate | Effort | Total Cost |
|---|---|---|---|---|---|
| BI Developer | Final Year Student | 19 EUR/hr | 31.35 EUR/hr | 120 hrs | 3,762 EUR |
| Data Engineer | Final Year Student | 21 EUR/hr | 34.65 EUR/hr | 100 hrs | 3,465 EUR |
| DE Intern | 1st Year Student | 14 EUR/hr | 23.10 EUR/hr | 140 hrs | 3,234 EUR |
| QA Engineer | Final Year Student | 17 EUR/hr | 28.05 EUR/hr | 70 hrs | 1,964 EUR |
| Project Manager | Final Year Student | 18 EUR/hr | 29.70 EUR/hr | 80 hrs | 2,376 EUR |
| Stakeholder | Full-Time Employee | 40 EUR/hr | 50.00 EUR/hr | 20 hrs | 1,000 EUR |
| **TOTAL** | | | | **530 hrs** | **15,801 EUR** |
