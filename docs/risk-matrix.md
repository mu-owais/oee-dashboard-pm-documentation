# Risk Matrix — OEE Dashboard Project

## Methodology

Risks were assessed using a probability/impact scoring matrix.
Each risk scored on two axes (1-3 scale), multiplied to produce a priority score:
- Score 9 = High priority — address immediately
- Score 4-6 = Medium priority — monitor and mitigate
- Score 2-3 = Low priority — monitor only

---

## High Priority Risks — Score 9

### Risk 1: Incorrect DAX Formulas
- **Probability:** 3 (High) — OEE calculations involve multiple interdependent
  measures; formula errors compound across Availability, Performance, and Quality
- **Impact:** 3 (High) — Wrong OEE numbers on a production floor are worse than
  no numbers. Supervisors making decisions on incorrect data causes operational harm.
- **Mitigation planned:** Validate all DAX measures against known ground-truth values
- **What actually happened:** Synthetic data was generated in WP2 specifically to
  create a controlled validation environment. DAX measures were developed and tested
  against synthetic data with known outputs before any live data connection.
  Final validation in Milestone 3 confirmed accuracy within the plus or minus 3
  percent target.
- **Connection to decisions.md:** This risk is the reason for Decision 2 —
  synthetic data generation before live sensor connection.

### Risk 2: Inconsistent Machine Data from Legacy Sensors
- **Probability:** 3 (High) — Constantia Flexibles production floor uses legacy
  hardware with known blind spots in data continuity during system downtime
- **Impact:** 3 (High) — Inconsistent source data produces unreliable OEE metrics
  regardless of how correct the DAX logic is
- **Mitigation planned:** Data cleaning and validation pipeline before Power BI ingestion
- **What actually happened:** WP2 included a dedicated data cleaning step (KAN-8)
  before any data entered the Star Schema model. Synthetic data provided a clean
  baseline to distinguish formula errors from data quality problems.
- **Connection to sprint sequencing:** Both Score 9 risks were addressed in
  Milestone 1 — before any dashboard UI work began. This is the direct reason
  M1 focused entirely on data foundations rather than visible features.

---

## Medium Priority Risks — Score 4-6

### Risk 3: User Adoption Failure
- **Probability:** 2 (Medium) — Operators are accustomed to Excel; new tools
  face resistance on the production floor
- **Impact:** 3 (High) — A dashboard that operators route around delivers no
  operational value regardless of technical quality
- **Score:** 6
- **Mitigation planned:** Simple UI design, role-specific training, pilot on
  single production line
- **What actually happened:** SWOT and PEST analyses both independently flagged
  this risk. The UI design decision prioritized simplicity — large gauges,
  minimal text, clear visual hierarchy. The change management plan defined a
  pilot rollout strategy rather than immediate full deployment. Training was
  designed to be role-specific and focused on practical interpretation,
  not tool mechanics.

### Risk 4: Team Miscommunication
- **Probability:** 2 (Medium) — Five-person student team working across
  multiple work packages simultaneously
- **Impact:** 2 (Medium) — Misalignment on requirements or technical decisions
  causes rework
- **Score:** 4
- **Mitigation planned:** Jira Kanban board with clear ticket ownership
- **What actually happened:** All work items tracked in Jira with assigned owners
  and milestone deadlines. Ticket descriptions were written to be actionable
  without requiring follow-up meetings. Four milestone reviews provided
  structured checkpoints for alignment.

### Risk 5: Demo Failure During Final Presentation
- **Probability:** 2 (Medium) — Live dashboard demo introduces technical risk
- **Impact:** 2 (Medium) — Presentation credibility affected
- **Score:** 4
- **Mitigation planned:** Validation and testing milestone before presentation
- **What actually happened:** Milestone 3 (Validation, Testing and Improvements)
  ran for 15 days before the final presentation. All slicers, filters, and
  calculations were tested. The final presentation was delivered without
  technical issues.

---

## Low Priority Risks — Score 2-3

### Risk 6: No MES Data Access
- **Probability:** 1 (Low) — Data pipeline secured early in the project
- **Impact:** 2 (Medium) — Would limit dashboard integration depth
- **Score:** 2
- **What actually happened:** Direct SQL database access was established in
  Milestone 1. MES integration was out of scope by design, with the Star
  Schema architected to support future MES extension.

### Risk 7: Changing Requirements
- **Probability:** 1 (Low) — Project scope was well-defined from the outset
  through the project charter and SMART analysis
- **Impact:** 2 (Medium) — Scope changes mid-project would compress delivery time
- **Score:** 2
- **What actually happened:** No significant scope changes occurred. The only
  scope adjustment was the Quality page deprioritization in Milestone 3,
  which was a deliberate delivery protection decision, not an unplanned change.

---

## Key Insight

The risk matrix did not just identify problems — it determined the sequence
of the entire project.

Addressing the two Score 9 risks first meant Milestone 1 was dedicated entirely
to data foundations and DAX validation, not to building visible dashboard features.
This sequencing decision protected the project from discovering a fundamental
accuracy problem in week 5 when there was no time to fix it.

Risk-driven sprint sequencing is not pessimism. It is how you protect delivery.
