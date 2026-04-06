# Change Management Plan — OEE Dashboard

## Why Change Management Was a Product Requirement

The OEE dashboard was not just a technical deployment. It was a behavior change
initiative. The goal was not to install software — it was to change how production
supervisors and operators make decisions during shifts.

A dashboard that operators do not use delivers zero operational value regardless
of how accurate its calculations are. Change management was therefore treated as
a product requirement, not a communications task added after the build was complete.

---

## The Adoption Challenge

Three factors made adoption the primary risk after technical delivery:

**Familiarity with existing tools:** Production staff had used Excel-based reporting
for years. The mental model was established. Any new tool competes against a workflow
that already works — imperfectly, but predictably.

**Fear of surveillance:** OEE dashboards can be perceived as performance monitoring
tools aimed at individual operators rather than process improvement tools. If operators
believe the dashboard is being used to evaluate them personally, they will resist it
or game the data.

**Cognitive load on the production floor:** Operators and supervisors work in a
high-pressure, time-constrained environment. A tool that requires interpretation or
training to read will be ignored in favor of faster, simpler alternatives.

---

## Communication Strategy

**What was communicated:**
- Why OEE is being introduced — the business case, not the technical capability
- How the data will be used — process improvement, not individual performance evaluation
- What changes for each role — supervisors get a faster view, operators get clearer
  feedback on line performance

**How it was communicated:**
- Direct explanation to each stakeholder group before any system access was given
- Emphasis on replacing a broken process, not replacing people
- Regular demonstrations during Milestones 2 and 3 to maintain alignment before
  the final handover

---

## User Involvement Strategy

Early involvement was built into the project structure rather than added at the end.

**Supervisors:** Informed the information hierarchy decision. The Overview page was
designed around the question a supervisor asks at the start of a shift: how did the
last shift perform and what caused any downtime? This question drove the layout —
single OEE gauge at the top, downtime category breakdown below, shift comparison
on the right.

**Operators:** Feedback on dashboard simplicity was incorporated during Milestone 3
UI refinement. Large gauges, minimal text, and clear color coding were direct
responses to the cognitive load concern identified in the PEST analysis.

**Maintenance engineers:** Availability and Performance pages were designed to
support their diagnostic workflow — machine-level drill-down, downtime patterns
over time, product-level performance gaps.

---

## Resistance Management

Resistance was anticipated and planned for rather than treated as a failure.

**The adoption curve recognized three groups:**
- Early adopters — supervisors who immediately see the value of real-time data
  over delayed Excel reports. These users drive momentum by demonstrating value
  to peers.
- The majority — follow once the value becomes visible through early adopter behavior.
  The pilot strategy was designed to create this visibility before broader rollout.
- Resistant users — addressed through education and reassurance, not pressure.
  The surveillance concern was addressed directly in communications.

**The simplicity decision as resistance mitigation:**
The single most effective resistance management strategy was the UI design itself.
A dashboard that takes 30 seconds to read does not generate resistance. Complexity
generates resistance. Every design choice that reduced cognitive load — large gauges,
shift-level summary as the default view, minimal navigation — was simultaneously
a user experience decision and a change management decision.

---

## Rollout Plan

**Phase 1 — Pilot (immediate post-deployment)**
- Deploy to the single target production line only
- Integrate into daily shift handover meetings as a reference tool
- Conduct short onboarding sessions focused on practical interpretation,
  not system mechanics
- Collect usability feedback within the first two weeks

**Phase 2 — Refinement (weeks 3-6)**
- Implement minor adjustments to KPIs, filters, and visuals based on real usage
- Identify which features supervisors use daily versus ignore
- Establish the dashboard as the primary reference for shift-level OEE discussion

**Phase 3 — Expansion (month 2 onward)**
- Extend to additional production lines based on pilot confidence
- Use adoption data from Phase 1 and 2 to inform training for new lines
- Review OKR progress: unclassified downtime reduction, Excel reporting reduction

---

## What Was Not Resolved

The change management plan defined the strategy. The project ended at delivery of
the dashboard, before Phase 1 of the rollout began.

Whether supervisors actually changed their shift handover behavior, whether operators
trusted the data, and whether the 20 percent downtime reduction OKR was achieved —
these questions were left open at project close.

This is the gap that Insight 1 in insights.md addresses: deployment success and
adoption success are not the same metric, and this project measured only the first.
