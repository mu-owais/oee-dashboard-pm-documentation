# Stakeholder Analysis — OEE Dashboard

## Methodology

Stakeholders were mapped using a Power/Interest grid — two axes:
- **Power:** ability to influence project success or failure
- **Interest:** degree to which the stakeholder is affected by the outcome

The mapping produced four groups, each requiring a different engagement strategy.
Critically, this analysis did not just inform communication — it determined the
information hierarchy of the dashboard itself.

---

## Stakeholder Map

### Manage Closely — High Power / High Interest

**Production Manager**
- Why high power: primary decision-maker for OEE data on the production floor.
  Can approve or block adoption of the dashboard in daily operations.
- Why high interest: directly responsible for shift performance metrics.
  An accurate dashboard changes how they run shift handovers.
- Engagement strategy: frequent demonstrations, direct feedback loops,
  dashboard designed around their primary workflow.
- **Product implication:** The supervisor summary view on the Overview page
  was designed first and validated against this stakeholder's needs.
  The single OEE gauge, shift-level donut chart, and downtime category bar
  chart all exist because the Production Manager needs to answer one question
  in under 30 seconds: how did this shift perform and why.

**Project Sponsor**
- Why high power: budget holder. Can cancel or extend the project.
- Why high interest: accountable for the operational excellence initiative
  that this dashboard supports.
- Engagement strategy: milestone-based progress updates, clear delivery
  against SMART goals.
- **Product implication:** The SMART analysis and OKR definitions were written
  for this stakeholder — they needed evidence that the project had measurable
  success criteria, not just a working tool.

---

### Keep Satisfied — High Power / Low Interest

**IT Department**
- Why high power: controls data access, licensing, and infrastructure.
  Can block the project by withholding database access or Power BI licenses.
- Why low interest: not an end user of the dashboard. Success or failure
  of OEE reporting does not directly affect their performance metrics.
- Engagement strategy: early involvement to ensure technical compliance.
  No surprises on data access requirements.
- **Product implication:** The decision to use Power BI over a commercial
  cloud OEE platform reduced dependency on external vendor access requests,
  which IT would have needed to approve. This was a direct factor in the
  solution scoring matrix decision.

---

### Keep Informed — Low Power / High Interest

**Machine Operators**
- Why low power: end users of the dashboard but not decision-makers.
  Cannot approve or block adoption.
- Why high interest: daily users. A dashboard that is confusing or that
  feels like surveillance will be ignored or actively resisted.
- Engagement strategy: training sessions, simple interface design,
  framing of OEE as a process improvement tool rather than individual
  performance evaluation.
- **Product implication:** The SWOT and PEST analyses both independently
  identified operator resistance as a threat. This drove the simplicity
  decision in the UI — the Overview page uses large gauges and minimal
  text because operators needed to read it at a glance, not interpret
  a data table. Simplicity was not a design preference. It was a risk
  mitigation decision.

**QC Team**
- Why low power: focused on scrap reduction but not responsible for
  the broader OEE initiative.
- Why high interest: the Quality component of OEE directly intersects
  with their work. Wasted Biscuit data is relevant to their function.
- Engagement strategy: regular updates on Quality data availability.
- **Product implication:** The data model includes Good Biscuit, Wasted
  Biscuit, and Quality measures that serve this stakeholder's needs.
  The Quality dashboard page was planned for this audience. Its
  deprioritization in M3 was noted as a gap for this stakeholder group.

---

### Monitor — Low Power / Low Interest

**External Vendors**
- Why low power and low interest: minimal direct impact on project
  outcomes. Peripheral to the production floor OEE initiative.
- Engagement strategy: periodic observation only.
- **Product implication:** None. Vendor requirements did not influence
  any product or design decisions.

---

## The Key Insight From This Analysis

Stakeholder mapping is not a communication planning exercise.
It is a product prioritization input.

The Production Manager's position in the Manage Closely quadrant is the
reason the Overview page leads with a supervisor summary view rather than
a maintenance drill-down. The Machine Operators' position in Keep Informed
is the reason the UI was designed for simplicity over technical depth.
The IT Department's position in Keep Satisfied is a factor in the solution
selection decision.

Every significant product decision in this project traces back to a
stakeholder position on this grid.
