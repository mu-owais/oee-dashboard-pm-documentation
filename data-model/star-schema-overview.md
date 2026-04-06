# Data Model — Star Schema Overview

## Why a Star Schema

A star schema organizes data into two types of tables: fact tables that store
measurable events, and dimension tables that store the context around those events.
The name comes from the shape — one or more fact tables at the center, dimension
tables radiating outward like points of a star.

For an OEE dashboard, this structure is the correct choice because OEE is not a
single number — it is a calculation across multiple data sources (production logs,
downtime records, scrap data) that needs to be sliced by multiple dimensions
(machine, shift, product, date). A star schema makes those slices fast and the
logic clean.

---

## The 8-Table Model

This dashboard uses 8 tables: 2 fact tables and 6 dimension tables.

### Fact Tables (what happened)

**FACT_PRODUCTION**
The core table. Every row is one production event on one machine in one shift.
Contains all calculated OEE measures:
- OEE and OEE Net
- Availability Net and Availability Gross
- Performance
- Quality
- Runtime (Min) and Planned Production Time (Min)
- Total Biscuit, Good Biscuit, Wasted Biscuit, Target Biscuit

This table is the source for every KPI shown on the Overview, Availability,
and Performance pages.

**FACT_DOWNTIME / FACT_DOWNTIME_EVENTS**
Two tables tracking downtime — one for aggregated downtime totals, one for
individual downtime events. Separating these allows the dashboard to show
both summary-level downtime (total minutes lost per shift) and event-level
detail (what happened, when, for how long) without mixing granularities
in a single table.

### Dimension Tables (the context)

**DIM_DATE**
Enables time-based filtering and drill-down. Supports hierarchy: Year →
Quarter → Month → Day. This is why the trend charts on the dashboard can
display at monthly or daily granularity using the same slicer.

**DIM_MACHINE**
One row per machine on the production floor. Enables the Availability page
to compare performance across machines and lets supervisors filter the
entire dashboard to a single machine.

**DIM_SHIFT**
One row per shift type. Enables the donut charts on Overview, Availability,
and Performance pages to break OEE down by shift — morning, afternoon, night.
This is operationally important: shift-level comparison is how supervisors
identify whether a performance problem is systematic or shift-specific.

**DIM_PRODUCT**
One row per product type produced on the line. Enables the Performance page
to compare total vs. target biscuit counts by product — identifying which
products are hitting efficiency targets and which are not.

**DIM_DOWNTIME_CAT**
One row per downtime category (mapped to OEE category). Enables the bar charts
on Overview and Availability pages to show what type of loss is driving
downtime — planned stops, unplanned breakdowns, speed losses, quality losses.
This categorization is how the dashboard moves from showing that downtime
occurred to showing why.

---

## How the Model Supports Two User Types

The star schema was not designed in isolation — it was designed to serve the
two distinct users identified in the stakeholder analysis.

**Production supervisors** use DIM_SHIFT and DIM_DATE to filter the Overview
page to their shift and see a single OEE number with trend context.

**Maintenance engineers** use DIM_MACHINE and DIM_DOWNTIME_CAT to drill into
the Availability page and identify which machine is causing downtime and what
category of failure is responsible.

The same fact tables serve both users. The dimensions determine what question
each user can ask.

---

## The Quality Page Gap

The data model includes a Quality field in FACT_PRODUCTION and tracks
Good Biscuit and Wasted Biscuit counts. The foundation for a Quality
analysis page exists in the data model.

The Quality dashboard page was not completed during the project timeline.
See dashboard/quality-scope-note.md for the full scope management rationale.
