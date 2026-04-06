# PM Insights — OEE Dashboard Project

> These are not project notes. They are product management lessons extracted
> from building this dashboard. Each insight starts from a business implication,
> not a data observation.

---

## Insight 1: Deployment success and adoption success are not the same metric

The dashboard was deployed on schedule. All four milestones released. Power BI
was live and showing correct OEE numbers.

But the project OKRs — reduce unclassified downtime by 20%, reduce Excel-based
reporting by 30% — were defined for the post-deployment phase. The build phase
had no mechanism to measure whether supervisors actually used the dashboard
differently than they had used Excel.

**The implication:** A product is not done when it is deployed. It is done when
it changes the behavior it was built to change. The success metric should have
been defined before the first sprint — not in the Next Steps section of the
final report.

---

## Insight 2: Risk priority should determine sprint sequence, not feature excitement

The two highest-priority risks — DAX formula errors and inconsistent legacy
sensor data — were addressed in Milestone 1, before any dashboard UI work began.
This was the correct decision, driven by the risk matrix score of 9/9 for both.

**The implication:** Sprint sequence in a product build should be determined by
risk ranking, not by what is most visible or most exciting to ship. The most
dangerous thing to discover in week 5 is that the core calculation logic was
wrong in week 1. Risk-driven sequencing is not pessimism — it is how you protect
delivery.

---

## Insight 3: Simplicity in a manufacturing tool is risk mitigation, not compromise

The SWOT and PEST analyses both identified the same threat independently:
operators were accustomed to Excel and would resist any tool that felt more
complex. The change management plan addressed this directly — simple
visualizations, role-specific training, pilot on one production line before
broader rollout.

**The implication:** In manufacturing environments, the adoption risk from
complexity often exceeds the technical risk from the system itself. A technically
accurate dashboard that operators route around is not a working product.
Designing for simplicity was not a concession to user preferences — it was a
deliberate strategy to prevent the highest adoption risk from materializing.

---

## Insight 4: Stakeholder mapping changes what you build, not just who you email

Mapping the Production Manager as Manage Closely and Machine Operators as Keep
Informed did not just shape the communication plan — it determined the
information hierarchy of the dashboard itself. The supervisor summary view came
first because supervisors had the highest power and interest in acting on OEE
data in real time.

**The implication:** Stakeholder analysis is a product prioritization input, not
a communications exercise. Who has the power to make the product succeed or fail
should directly determine what the product shows first, what gets built in
Milestone 2 versus Milestone 3, and what gets cut if time runs short.

---

## Insight 5: The gap this project revealed is bigger than this project

Constantia Flexibles now has OEE data visible in real time. But visibility is
the beginning of the adoption problem, not the end of it. Whether operators
trust the data, whether supervisors change their shift handover process, whether
maintenance response time actually decreases — none of these are answered by a
working dashboard.

This is the same gap that appears in every enterprise AI and digital tool
deployment: measurement stops at deployment, and value is never confirmed.

**The implication:** The real product problem is not building the dashboard.
It is building the measurement system that tells you whether the dashboard
created operational value. I am addressing this gap directly in my bachelor's
thesis — a framework for measuring AI and digital tool adoption success in
German manufacturing environments, not just deployment completion.
