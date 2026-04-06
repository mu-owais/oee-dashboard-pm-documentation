# Milestone Timeline — OEE Dashboard Project

## Overview

The project ran from mid-October to December 4, 2025 — approximately 7 weeks.
Four milestones structured delivery into sequential phases, each building on
the previous one.

All four milestones were released on schedule.

---

## Milestone Detail

### Milestone 1: Data Understanding, Modeling and Foundations
- **Period:** October 16 – October 29, 2025
- **Status:** Released
- **Deliverables:**
  - Dataset exploration and import
  - Star Schema data model (8 tables)
  - Core DAX measures (Availability, Performance, Quality, OEE)
  - Synthetic machine data generation

**Why this milestone came first:**
The two highest-priority risks identified in the risk matrix — incorrect DAX
formulas and inconsistent legacy sensor data — both lived in this phase.
Building and validating the data foundation before any UI work began was a
deliberate risk mitigation decision. A visually impressive dashboard built
on unvalidated DAX logic would have been worse than no dashboard at all.
See decisions.md Decision 2 for the full rationale.

---

### Milestone 2: Dashboard Design and Layout Creation
- **Period:** October 30 – November 12, 2025
- **Status:** Released
- **Deliverables:**
  - Corporate Identity canvas setup
  - KPI and slicer panel implementation
  - Trend and detailed visualizations
  - All four dashboard page layouts

**Why this milestone came second:**
Only after the data model and DAX measures were validated could frontend
work begin with confidence. Building UI against unvalidated measures creates
rework risk — visual components need to be redesigned if the underlying
calculation logic changes. Milestone 1 eliminated that risk before
Milestone 2 started.

---

### Milestone 3: Validation, Testing and Improvements
- **Period:** November 13 – November 28, 2025
- **Status:** Released
- **Deliverables:**
  - OEE calculation validation against accuracy target
  - UI refinement based on review feedback
  - Slicer and filter testing across all pages

**Scope decision in this milestone:**
The Quality dashboard page was deprioritized during this milestone to
protect validation time for the three completed pages. See
dashboard/quality-scope-note.md for the full rationale.

---

### Milestone 4: Pitch Deck and Report
- **Period:** November 29 – December 4, 2025
- **Status:** Released
- **Deliverables:**
  - Final stakeholder presentation
  - Project documentation (written report)
  - Two stakeholder demo videos published

---

## Sequencing Rationale

The milestone sequence was not arbitrary. It followed a risk-first logic:

1. Resolve the highest-risk elements first (data foundations, DAX accuracy)
2. Build visible features only after foundations are validated (dashboard UI)
3. Validate the complete product before final delivery (testing milestone)
4. Document and present after the product is stable (pitch and report)

This sequence protected the project from the most common failure mode in
BI projects: discovering a fundamental data or calculation problem in the
final week when there is no time to fix it.
