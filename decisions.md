# Key Decisions — OEE Dashboard Project

> This file documents three significant decisions made during the project:
> what options were considered, what was chosen, and what trade-off was accepted.
> Decisions are recorded because the reasoning matters as much as the outcome.

---

## Decision 1: Power BI over MES-based OEE Module

**Context:** Before committing to a technical approach, three alternatives were
evaluated using a pairwise-weighted scoring matrix: a custom Power BI dashboard (A1),
commercial cloud OEE software (A2), and an MES-integrated OEE module (A3).

**Options considered:**
- A3 (MES module) scored highest on accuracy and system integration — ideal in theory
- A2 (commercial cloud) offered the fastest deployment but lowest customization
- A1 (Power BI) offered the best balance across cost, usability, and scalability

**Decision:** Power BI dashboard — scored 4.75/6 (79%) on weighted criteria.

**Reasoning:** The MES option's superiority in integration did not justify its cost
and implementation complexity for a single production line pilot. Constantia Flexibles
needed something that could be validated quickly and scaled incrementally. Power BI
also gave the team direct access to production floor SQL data without dependency on
MES licensing or vendor timelines.

**Trade-off accepted:** Lower out-of-the-box integration with maintenance systems.
Mitigation: the Star Schema data model was designed to be extensible to MES
integration as a future phase.

---

## Decision 2: Synthetic Data Generation Before Connecting to Live Production Systems

**Context:** Risk assessment identified two highest-priority risks, both scored 9/9:
incorrect DAX formulas and inconsistent machine data from legacy sensors. Either one
would make the dashboard produce wrong OEE numbers — and wrong OEE data on a
production floor is worse than no data at all.

**Options considered:**
- Connect directly to live sensor data and clean iteratively during development
- Build synthetic data first, validate all DAX logic against it, then connect to real data

**Decision:** Synthetic data first, with a clean validated data pipeline established
before any live sensor connection.

**Reasoning:** The legacy hardware at Constantia created real blind spots in data
continuity. Validating DAX calculation logic against synthetic data with known
ground-truth values made it possible to isolate formula errors from data quality
problems. Without this separation, a wrong OEE number in week 3 could have come
from either source — and we would not have known which to fix.

**Trade-off accepted:** Additional upfront work in the data engineering phase.
Milestone 1 consumed the full two-week window on foundations before any UI work
began. This was the correct sequencing — dashboard accuracy was the highest-risk
element of the entire project and had to be resolved first.

---

## Decision 3: Supervisor-First Information Hierarchy Over Maintenance-First

**Context:** Stakeholder analysis identified two distinct primary user types:
production supervisors who make shift-level decisions, and maintenance engineers
who diagnose machine-level faults. The dashboard could not be optimally designed
for both simultaneously without increasing complexity to the point of adoption risk.

**Options considered:**
- Design for maintenance engineers first — maximum technical drill-down depth
- Design for supervisors first — shift-level summary with drill-down as a secondary layer
- Build two entirely separate dashboards for each user type

**Decision:** Supervisor-first design, with maintenance drill-down accessible as
a secondary layer from the same interface.

**Reasoning:** Supervisors were mapped as Manage Closely in the Power/Interest
stakeholder grid — highest power, highest interest in acting on OEE data in real
time. If the dashboard did not change supervisor behavior during shift handovers,
the project would not achieve its operational objectives regardless of how
technically accurate the maintenance view was. Adoption risk from complexity was
also a confirmed threat in the SWOT analysis — a simpler primary view reduced
the risk of operators routing around the tool entirely.

**Trade-off accepted:** The maintenance drill-down view received fewer design
iterations than the supervisor summary. This was flagged as a known gap:
the Availability and Performance pages serve maintenance needs but were not
validated directly with maintenance engineers during the project timeline.
