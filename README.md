# Real-Time OEE Dashboard — Product Management Documentation

**Client:** OTH Amberg-Weiden x Constantia Flexibles
**Course:** Project Management and Agile Methods — OTH Amberg-Weiden
**Team:** 5 members · **Duration:** Mid-October – December 4, 2025 (~7 weeks)
**My role:** Project Manager + cross-functional contributor across all four work packages

---

## The Problem

Constantia Flexibles tracked production performance using manual Excel reports.
Three failure modes resulted:

- **Opacity** — no visibility into root causes of downtime
- **Inaccuracy** — human data entry errors corrupting shift records
- **Latency** — reports delayed by hours, forcing supervisors to make decisions on stale data

The project replaced this with an automated Power BI dashboard connected directly to the
SQL production database — reducing reporting latency to a real-time refresh rate of under
5 minutes and eliminating manual data entry for the target production line.

---

## What Was Built

A real-time OEE dashboard designed for two distinct user types at Constantia Flexibles:

**For production supervisors (shift-level decisions):**
- Single OEE score with Availability, Performance, and Quality breakdown
- OEE trend line over time
- Downtime by category — what is causing efficiency loss
- Output by product — total vs. good vs. wasted units per shift
- Shift-level OEE comparison

**For maintenance engineers and line managers (machine-level diagnosis):**
- Availability drill-down by machine and shift
- Total downtime over time — identifying patterns across weeks
- Planned Production Time vs. Effective Runtime — where time is being lost
- Performance vs. target by product — which lines are underperforming

**Data model:** Star Schema — 8 tables (2 fact tables, 6 dimension tables)
**DAX measures:** Validated to ±3% accuracy target
**Technology:** Power BI · SQL · Python · DAX

---

## My Contributions

I was the most cross-functional contributor on the team, responsible for all four
work packages either as sole owner or co-owner.

**WP1 — Project Management (sole owner)**
- Wrote the project charter, defined four milestone releases, configured and led
  the Kanban board in Jira as project lead
- Wrote ticket descriptions specific enough to act on without a follow-up meeting
- Delivered final stakeholder presentation and project documentation

**WP2 — Data Engineering (co-owner)**
- Generated synthetic machine data to simulate production floor inputs before
  connecting to live sensors — a deliberate risk mitigation decision
- Cleaned and validated data before Power BI ingestion
- Co-designed the Star Schema data model connecting production logs,
  downtime records, and scrap data

**WP3 — BI Frontend (co-owner)**
- Built all four dashboard panels
- Developed trend and historical visualizations
- Enforced Corporate Identity standards across all views

**WP4 — QA and Logic (sole owner)**
- Developed all core DAX measures: Availability, Performance, Quality
- Ran OEE calculation validation against the ±3% accuracy target

---

## How the Project Was Managed

Kanban methodology in Jira, structured around four milestone-based releases.
All four milestones delivered on schedule.

| Milestone | Period | Deliverables |
|---|---|---|
| M1: Data and Foundations | Oct 16-29 | Dataset import, Star Schema, DAX measures |
| M2: Dashboard Design | Oct 30-Nov 12 | KPI panels, slicers, trend visualizations |
| M3: Validation and Testing | Nov 13-28 | OEE validation, UI refinement, slicer testing |
| M4: Pitch Deck and Report | Nov 29-Dec 4 | Final presentation, project documentation |

Jira board screenshots are in /assets.

---

## Three Frameworks Applied — With PM Rationale

**Scoring Matrix (pairwise comparison) — solution selection**
Three alternatives evaluated: Power BI dashboard, commercial cloud OEE software, MES-based
OEE module. Accuracy weighted highest. Power BI scored 4.75/6 (79%) — selected for best
balance of cost, usability, and scalability.

**Stakeholder Power/Interest mapping — adoption strategy**
Four groups mapped. Production Manager drove the information hierarchy decision —
supervisor summary view came first because supervisors are the decision-makers who act
on OEE data in real time.

**Risk Matrix — sprint sequencing**
Two risks scored 9/9: incorrect DAX formulas and inconsistent legacy sensor data. Both
were addressed in Milestone 1, before any UI work began. This is why synthetic data
generation preceded live sensor connection.

---

## OKRs Defined for Post-Deployment Phase

**Objective 1: Improve production transparency**
- Enable automated shift-level OEE reporting
- Reduce unknown or unclassified downtime by 20%
- Ensure supervisors can access all key KPIs without analyst support

**Objective 2: Support faster operational decisions**
- Reduce manual Excel-based reporting effort by 30%
- Establish the dashboard as the single source of truth for OEE metrics
- Improve response time to production issues during shifts

---

## Stakeholder Demo Videos

Two videos produced during the project to validate the dashboard with stakeholders:

- [The Reality of Running Blind](https://www.youtube.com/watch?v=j0w1c7zDR3k) — problem framing for production stakeholders
- [Stakeholder Validation: The Impact of Real-Time Data](https://www.youtube.com/watch?v=qycPhzhmyJ4) — live dashboard demonstration

---

## What This Project Raised

Building this dashboard surfaced a question the project did not answer: does making
OEE data more visible actually change supervisor behavior — or does it just make the
problem more legible?

The gap between data visibility and behavior change is the difference between a
dashboard and a product. I am building a measurement framework to address this gap
directly in my bachelor's thesis.

---

## Repo Contents

| File / Folder | What It Contains |
|---|---|
| decisions.md | Three key decisions — options considered, choice made, trade-off accepted |
| insights.md | Five PM lessons extracted from this project |
| data-model/star-schema-overview.md | Plain-English explanation of the 8-table data model |
| data-model/data-dictionary.md | What each table and key field means |
| dashboard/ | Power BI file and panel screenshots |
| dashboard/quality-scope-note.md | Why the Quality page was not completed |
| docs/project-charter.md | SMART goals and project charter |
| docs/stakeholder-analysis.md | Power/Interest map with product implications |
| docs/risk-matrix.md | Risk register with mitigation actions taken |
| docs/change-management-plan.md | Adoption strategy and rollout plan |
| docs/okrs.md | Two objectives with measurable key results |
| requirements/user-stories.md | User stories for supervisor and maintenance personas |
| requirements/solution-scoring-matrix.md | Pairwise comparison of three OEE solutions |
| process/kanban-board-structure.md | Jira Kanban setup and all work items |
| process/milestone-timeline.md | Four milestones with sequencing rationale |
| process/work-breakdown-structure.md | WP1-WP4 ownership, tasks, and hours |
| assets/ | Jira board screenshots from project |

---

## Skills Demonstrated

Agile · Kanban · Jira · Project Charter · Stakeholder Analysis · Risk Management ·
Change Management · OKR Definition · Requirements Management · Power BI · DAX ·
SQL · Python · Pairwise Comparison · MoSCoW Prioritization
