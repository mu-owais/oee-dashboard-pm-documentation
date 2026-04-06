# Data Dictionary — OEE Dashboard

This file defines every table and key field in the data model.
It exists so that anyone reading this repo understands what the data
represents — without needing to open the Power BI file.

---

## FACT_PRODUCTION

The central fact table. One row per production run on one machine in one shift.

| Field | Type | What It Means |
|---|---|---|
| OEE | Measure | Overall Equipment Effectiveness — composite score of Availability x Performance x Quality |
| OEE Net | Measure | OEE calculated using net available time (excludes planned stops) |
| Availability Net | Measure | Percentage of net available time the machine was actually running |
| Availability Gross | Measure | Percentage of total scheduled time the machine was running (includes planned stops) |
| Performance | Measure | Actual output rate as a percentage of the theoretical maximum rate |
| Quality | Measure | Percentage of total units produced that met quality standards |
| Runtime (Min) | Measure | Actual minutes the machine was running and producing |
| Planned Production Time (Min) | Measure | Total minutes the machine was scheduled to run |
| Total Biscuit | Measure | Total units produced in the run |
| Good Biscuit | Measure | Units that passed quality inspection |
| Wasted Biscuit | Measure | Units that failed quality inspection or were scrapped |
| Target Biscuit | Measure | Expected output based on machine speed and run time |

---

## FACT_DOWNTIME

Aggregated downtime records per production run.

| Field | Type | What It Means |
|---|---|---|
| Total Downtime (Min) | Measure | Total minutes of downtime recorded in the run |
| Total Duration (Min) | Measure | Total duration of downtime events, grouped by category |

---

## FACT_DOWNTIME_EVENTS

Individual downtime event records. More granular than FACT_DOWNTIME —
one row per downtime event rather than one row per run.
Used for event-level analysis without distorting production-level aggregations.

---

## DIM_DATE

Date dimension table enabling time-based filtering and drill-down.

| Field | What It Enables |
|---|---|
| Date | Filter the dashboard to a specific date range |
| Year | Drill up to annual view |
| Quarter | Drill up to quarterly view |
| Month | Standard monthly trend analysis |
| Day | Day-level granularity for detailed investigation |

The date hierarchy (Year > Quarter > Month > Day) is what makes the trend
charts on the Overview and Availability pages interactive — users can
expand or collapse time granularity without changing the report.

---

## DIM_MACHINE

One row per machine on the production floor.

| Field | What It Enables |
|---|---|
| Machine | Filter entire dashboard to a single machine. Enables the Availability page bar chart comparing performance across machines. |

---

## DIM_SHIFT

One row per shift type.

| Field | What It Enables |
|---|---|
| Shift | Break OEE, Availability, and Performance down by shift. The donut charts on Overview, Availability, and Performance pages all use this dimension. Shift-level comparison is how supervisors identify whether a problem is systematic or shift-specific. |

---

## DIM_PRODUCT

One row per product type produced on the line.

| Field | What It Enables |
|---|---|
| Product | Compare output by product type. The Performance page bar charts use this to show which products are hitting target biscuit counts and which are not. |

---

## DIM_DOWNTIME_CAT

One row per downtime category, mapped to OEE loss category.

| Field | What It Enables |
|---|---|
| OEE_Category | Classify downtime by type — planned stops, unplanned breakdowns, speed losses, quality losses. This is what turns a downtime number into an actionable diagnosis. The bar charts on Overview and Availability pages use this to answer not just how much downtime occurred but why. |

---

## Key Calculations

**OEE = Availability x Performance x Quality**

The three components multiply — a machine that is available 90% of the time,
running at 90% of target speed, and producing 90% good units has an OEE of
72.9%, not 90%. This multiplicative relationship is why small improvements
across all three components have a compounding effect on overall OEE.

**Availability Net vs. Availability Gross**

Net excludes planned stops (scheduled maintenance, planned changeovers).
Gross includes them. The dashboard shows both because Net is the operational
efficiency metric supervisors act on, while Gross is the metric used for
capacity planning and scheduling decisions.

**DAX validation target: ±3% accuracy**

All measures were validated against known ground-truth values using synthetic
data before connecting to live production data. See decisions.md Decision 2
for the rationale behind this sequencing.
