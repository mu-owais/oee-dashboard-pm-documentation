# Project Charter — Real-Time OEE Dashboard

## Project Title
Constantia Flexibles Operational Excellence — Real-Time OEE Dashboard

## Problem Statement

Constantia Flexibles production data existed in siloed systems and was logged
manually, causing three critical problems:

- **Opacity** — no visibility into root causes of downtime or efficiency loss
- **Inaccuracy** — human data entry errors corrupting shift performance records
- **Latency** — reports delayed by hours, forcing supervisors to make operational
  decisions on stale data

The consequence: supervisors were running blind. Decisions about machine allocation,
shift handovers, and maintenance scheduling were made without reliable real-time data.

## Project Goal

Develop a Power BI dashboard connected to the SQL production database via a Star
Schema data model — replacing manual Excel reporting with automated, real-time OEE
visibility for the target production line.

## SMART Analysis

**Specific:** An automated Power BI dashboard was built and deployed providing
real-time OEE visibility for the target production line, broken into Availability,
Performance, and Quality components.

**Measurable:** Reporting latency reduced to a real-time refresh rate of under 5
minutes. Manual data entry eliminated for the target production line.

**Achievable:** The system integrates three key data sources — production logs,
downtime records, and scrap data — using a validated Star Schema data model
and DAX measures accurate to within plus or minus 3 percent.

**Relevant:** Addresses the direct operational need: supervisors can now access
shift-level OEE data without waiting for manual reports or analyst support.

**Time-bound:** Project completed on defined timeline. Final release delivered
December 4, 2025.

## Scope

**In scope:**
- Power BI dashboard with Overview, Availability, and Performance pages
- Star Schema data model (8 tables)
- DAX measures for OEE, Availability, Performance, and Quality
- Synthetic data generation for validation
- Stakeholder demo and documentation

**Out of scope (this phase):**
- Quality dashboard page (data model foundation built; page deprioritized in M3)
- Live MES integration (architecture designed for future extension)
- Rollout beyond the pilot production line
- Predictive analytics or AI-based recommendations

## Team

| Role | Owner |
|---|---|
| Project Manager | Muhammad Awais |
| Data Engineering | Zohaib Sultan + Muhammad Awais |
| BI Frontend | Kashif Sultan + Muhammad Awais |
| QA and Logic | Muhammad Awais |
| Team Member | Husain Sultan |
| Team Member | Imran Khan |

**Examiner:** Prof. Andreas Dörner, OTH Amberg-Weiden

## Timeline

| Milestone | Period | Status |
|---|---|---|
| M1: Data and Foundations | Oct 16-29, 2025 | Released |
| M2: Dashboard Design | Oct 30-Nov 12, 2025 | Released |
| M3: Validation and Testing | Nov 13-28, 2025 | Released |
| M4: Pitch Deck and Report | Nov 29-Dec 4, 2025 | Released |

## Cost Estimate

Total estimated personnel cost: 15,801 EUR
Total effort: 530 hours across 6 role types
Rates based on average market salaries for IT working students in Bavaria,
with 25 percent surcharge for non-wage labor costs and 40 percent surcharge
for student recruitment and administration.
