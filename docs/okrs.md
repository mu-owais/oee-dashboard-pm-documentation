# OKRs — OEE Dashboard Post-Deployment Phase

## What These OKRs Are For

OKRs (Objectives and Key Results) were defined for the post-deployment phase
of the dashboard — not for the build phase. This distinction matters.

The build phase was measured by milestone delivery: four milestones, four
releases, all on schedule. Those are output metrics.

The OKRs below are outcome metrics. They measure whether the dashboard
actually changed operational behavior at Constantia Flexibles after deployment.
They were written to answer the question the build phase could not: did this
product create value, or did it just get deployed?

---

## Objective 1: Improve Production Transparency

**What this means:** Supervisors and managers should be able to answer questions
about production performance using the dashboard — without waiting for a manual
report, without asking an analyst, and without interpreting raw data themselves.

### Key Results

**KR1: Enable automated shift-level OEE reporting**
- Baseline: OEE data reported manually via Excel after each shift
- Target: Dashboard refreshes automatically within 5 minutes of shift data updates
- How to measure: Verify refresh rate in Power BI service settings post-deployment
- Owner: IT Department (data pipeline maintenance)

**KR2: Reduce unknown or unclassified downtime by 20%**
- Baseline: Percentage of downtime logged as unknown category at project start
- Target: 20% reduction within 60 days of deployment
- How to measure: DIM_DOWNTIME_CAT data — track the unknown category proportion
  week over week after go-live
- Owner: Production Manager (responsible for operators logging downtime correctly)
- Note: This KR depends on operator behavior change, not just dashboard accuracy.
  If operators do not log downtime categories correctly, the metric will not move
  regardless of dashboard quality. This is the adoption dependency.

**KR3: Ensure supervisors can access all key KPIs without analyst support**
- Baseline: Supervisors request Excel reports from analyst or admin
- Target: Zero analyst-mediated OEE report requests within 30 days of deployment
- How to measure: Track report request volume from supervisor group post-deployment
- Owner: Production Manager

---

## Objective 2: Support Faster and More Informed Operational Decisions

**What this means:** The time between a production problem occurring and a
decision being made to address it should decrease. The dashboard should be
the tool that enables that faster response.

### Key Results

**KR4: Reduce manual Excel-based reporting effort by 30%**
- Baseline: Hours spent per week on manual OEE data entry and report generation
- Target: 30% reduction within 60 days of deployment
- How to measure: Self-reported time tracking by the staff who previously
  maintained the Excel reports
- Owner: Production Manager

**KR5: Establish the dashboard as the single source of truth for OEE metrics**
- Baseline: Multiple versions of OEE data exist across Excel files, manual logs,
  and verbal shift handover reports
- Target: All OEE-related decisions in shift handover meetings reference the
  dashboard exclusively within 45 days of deployment
- How to measure: Direct observation of shift handover meetings or supervisor
  self-report
- Owner: Production Manager

**KR6: Improve response time to production issues during shifts**
- Baseline: Time from issue occurrence to supervisor awareness (estimated from
  report delay — up to several hours under the Excel system)
- Target: Supervisor awareness of critical downtime events within 10 minutes
  of occurrence
- How to measure: Timestamp comparison between FACT_DOWNTIME_EVENTS log entries
  and supervisor response actions in shift records
- Owner: Production Manager + IT Department (data pipeline latency)

---

## What Was Not Measured

The project closed at dashboard delivery. None of the six KRs above were
tracked during the project timeline because the deployment phase — where
these metrics would be collected — was outside the project scope.

This is the gap documented in insights.md Insight 1: the build was measured
on deployment success, not adoption success. The OKRs exist as a framework
for what the next phase of this product would measure — not as confirmed
outcomes of this project.

Documenting this gap honestly is itself a product management skill. A PM
who cannot distinguish between what was delivered and what was achieved
cannot prioritize the right next action.
