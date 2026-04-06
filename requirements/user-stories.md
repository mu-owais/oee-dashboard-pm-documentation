# User Stories — OEE Dashboard

## How These Were Developed

User stories were derived from the stakeholder analysis and the problem statement.
Two primary user types were identified: production supervisors and maintenance
engineers. Each has a different workflow, a different question they need answered,
and a different tolerance for complexity.

---

## Persona 1: Production Supervisor

**Name:** Shift Supervisor
**Context:** Responsible for shift performance on the production floor.
Attends shift handover meetings. Accountable to the Production Manager
for OEE results. Currently reads Excel reports prepared by an analyst —
often 30 to 60 minutes delayed from actual production events.
**Primary frustration:** Making shift decisions without knowing what is
actually happening on the line right now.
**What they are trying to avoid:** Being caught off guard by a downtime
problem they could have responded to earlier if they had real-time data.

---

### User Stories — Supervisor

**US-01: Shift-Level OEE Summary**
As a production supervisor,
I want to see the current OEE score for my shift broken into
Availability, Performance, and Quality components,
so that I can understand at a glance whether the line is performing
to target and which component is causing any gap.

Acceptance criteria:
- OEE, Availability, Performance, and Quality each displayed as a gauge
- Values update within 5 minutes of production data changes
- Color coding indicates above target, at risk, or below target
- Visible on the Overview page without any filter changes

---

**US-02: Downtime Root Cause**
As a production supervisor,
I want to see what category of downtime is causing the most efficiency loss,
so that I can decide whether to intervene now or flag it for the
maintenance team.

Acceptance criteria:
- Downtime displayed by OEE category (planned stop, unplanned breakdown,
  speed loss, quality loss)
- Sortable by duration
- Filterable by machine and date
- Visible on the Overview page

---

**US-03: Shift Comparison**
As a production supervisor,
I want to compare OEE performance across shifts,
so that I can identify whether a performance problem is shift-specific
or systematic across the line.

Acceptance criteria:
- OEE by shift displayed as a donut chart on the Overview page
- Filterable by date range
- Each shift segment clearly labeled

---

**US-04: Historical Trend**
As a production supervisor,
I want to see OEE trend over time,
so that I can tell whether performance is improving, stable, or declining
across multiple shifts and weeks.

Acceptance criteria:
- OEE Net trend line displayed on Overview page
- Supports drill-down by year, quarter, month
- Filterable by machine

---

**US-05: Machine Filter**
As a production supervisor,
I want to filter the entire dashboard to a single machine,
so that I can focus on one line without switching between reports.

Acceptance criteria:
- Machine slicer available on Overview, Availability, and Performance pages
- Selection applies to all visuals on the page simultaneously

---

## Persona 2: Maintenance Engineer

**Name:** Maintenance Engineer / Line Manager
**Context:** Responsible for diagnosing and resolving machine faults.
Responds to downtime events flagged by supervisors. Needs to identify
the specific machine, failure type, and duration to prioritize repairs.
Currently relies on verbal reports from operators and manual log books.
**Primary frustration:** Arriving at a fault without knowing its history —
how long it has been occurring, whether it is a recurring pattern,
which machine is the source.
**What they are trying to avoid:** Spending time diagnosing the wrong
machine or misidentifying the fault category.

---

### User Stories — Maintenance Engineer

**US-06: Availability by Machine**
As a maintenance engineer,
I want to see Availability rate broken down by individual machine,
so that I can identify which machine is the primary source of downtime
without asking the supervisor.

Acceptance criteria:
- Bar chart showing Availability Net by machine on the Availability page
- Filterable by date range and shift
- Machines ranked by availability so lowest performer is immediately visible

---

**US-07: Downtime Trend Over Time**
As a maintenance engineer,
I want to see total downtime over time at daily and monthly granularity,
so that I can identify whether a machine fault is a one-time event
or a recurring pattern.

Acceptance criteria:
- Clustered column chart on Availability page showing downtime over time
- Supports drill-down by year, quarter, month, day
- Filterable by machine

---

**US-08: Planned vs. Runtime Comparison**
As a maintenance engineer,
I want to compare Planned Production Time against actual Runtime,
so that I can quantify the gap between scheduled capacity and
delivered capacity for a given period.

Acceptance criteria:
- Planned Production Time and Effective Runtime displayed as KPI cards
  on the Availability page
- Values update with machine and date filter selections

---

**US-09: Product Performance vs. Target**
As a line manager,
I want to see actual output compared to target output by product,
so that I can identify which products are consistently missing
their production targets.

Acceptance criteria:
- Clustered bar chart on Performance page showing Total Biscuit
  vs. Target Biscuit by product
- Filterable by date and machine
- Gap between actual and target visible at a glance

---

## Stories Not Delivered in This Sprint

**US-10: Quality Rate by Product (deferred)**
As a quality control team member,
I want to see the percentage of good versus wasted units by product,
so that I can identify which products have the highest defect rates
and prioritize quality improvement efforts.

Status: Deferred to next sprint. Data model supports this story —
Good Biscuit, Wasted Biscuit, and Quality measures exist in
FACT_PRODUCTION. The Quality dashboard page was not completed
in Milestone 3. See dashboard/quality-scope-note.md.
