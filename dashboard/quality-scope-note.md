# Quality Page — Scope Management Note

## What This Page Was Intended to Show

The Quality component of OEE measures the percentage of total units produced
that met quality standards. For Constantia Flexibles, this translates to:

- Good Biscuit rate — percentage of units passing quality inspection
- Wasted Biscuit analysis — volume and pattern of scrapped units by product,
  machine, and shift
- Quality trend over time — whether the defect rate is improving or worsening
- Quality contribution to OEE loss — how much of the OEE gap is driven by
  quality failures versus availability or performance failures

## Why It Was Not Completed

The Quality page was in scope for the project. It was deprioritized during
Milestone 3 (Validation, Testing and Improvements) to protect the delivery
of validated Availability and Performance views on schedule.

The decision was driven by two factors:

**Time constraint:** Milestone 3 ran from November 13 to November 28 — 15 days
covering OEE calculation validation, UI refinement, and slicer testing across
the three existing pages. Adding a fourth page with new visuals in the same
window would have compressed the validation time for the pages already built.

**Risk priority:** The highest-risk deliverables were the DAX measures underpinning
Availability and Performance. Validating those to the target accuracy of plus or
minus 3 percent took priority over extending scope. A fourth page with unvalidated
logic would have weakened the credibility of the entire dashboard.

## What Exists in the Data Model

The data foundation for the Quality page is fully built. FACT_PRODUCTION contains:
- Quality (DAX measure — percentage of good units)
- Good Biscuit (count of units passing inspection)
- Wasted Biscuit (count of scrapped units)
- Total Biscuit (total units produced)

DIM_PRODUCT, DIM_MACHINE, DIM_SHIFT, and DIM_DATE are all available as
slicing dimensions. A Quality analysis page could be built on top of the
existing data model without any schema changes.

## What the Next Sprint Would Have Contained

Had the project continued into a fifth milestone, the Quality page would have
included:
- Quality gauge (mirroring the Availability and Performance gauges)
- Good vs. Wasted Biscuit by product — identifying which products have the
  highest defect rates
- Quality trend over time — daily and monthly view
- Quality by machine — identifying whether defects are machine-specific
  or systematic across the line
- Quality by shift — identifying whether defect patterns correlate with
  specific shifts or operators

## The PM Principle This Demonstrates

Scope management is not about cutting work because it is difficult. It is about
protecting the value already delivered by not diluting validation time across
more surface area than the sprint can cover.

Three fully validated pages delivered on time is a better outcome than four
partially validated pages delivered late.
