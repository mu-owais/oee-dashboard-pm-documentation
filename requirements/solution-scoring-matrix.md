# Solution Scoring Matrix — OEE Dashboard

## Why a Scoring Matrix Was Used

A scoring matrix was used instead of a simple pros/cons comparison because
the project needed a defensible, repeatable method for evaluating alternatives
against criteria that had different levels of importance.

A pros/cons list treats all criteria as equal. The scoring matrix forces the
team to decide which criteria matter most before evaluating any alternative —
removing the bias of evaluating criteria weights after seeing the scores.

---

## Alternatives Evaluated

**A1 — Custom Power BI Dashboard**
Build a Power BI report connected directly to the SQL production database
using a custom Star Schema data model and DAX measures.

**A2 — Commercial Cloud OEE Software**
Purchase a SaaS OEE platform (e.g., Worximity, OEEsystems, Tulip) and
configure it for Constantia Flexibles production data.

**A3 — MES-Based OEE Module**
Implement the OEE module within a Manufacturing Execution System already
in use or planned at Constantia Flexibles.

---

## Evaluation Criteria

Five criteria were defined before scoring any alternative:

| Criteria | Definition |
|---|---|
| Cost | Total implementation and ongoing operating cost |
| Integration with Business KPIs | Ability to connect OEE with quality, maintenance, and financial KPIs |
| Accuracy and Data Reliability | Trustworthiness of collected and processed OEE data |
| Ease of Implementation | Time, effort, and training required for deployment |
| Customization and Scalability | Flexibility to adapt and scale across machines and facilities |

---

## Criteria Weighting — Pairwise Comparison

A pairwise comparison was used to determine the relative weight of each
criterion. Each criterion was compared against every other criterion.
The criterion that matters more in the context of this project scores a point.

**Result — criteria weights:**

| Criteria | Weight |
|---|---|
| Accuracy and Data Reliability | Highest — wrong OEE data causes operational harm |
| Ease of Implementation | High — project had a fixed 7-week timeline |
| Customization and Scalability | High — solution needed to fit Constantia's specific workflow |
| Integration with Business KPIs | Medium |
| Cost | Medium — student project context limits budget realism |

**Why Accuracy was weighted highest:**
OEE data is used to make real operational decisions — machine allocation,
maintenance scheduling, shift planning. Inaccurate data does not just fail
to help; it actively causes harm by directing resources to the wrong problem.
This made accuracy the non-negotiable criterion.

---

## Scoring Results

Each alternative scored on a 0-6 scale per criterion, multiplied by weight,
then aggregated.

| Criteria | A1 Power BI | A2 Cloud OEE | A3 MES Module |
|---|---|---|---|
| Cost | High score — no licensing cost beyond Power BI | Medium — SaaS subscription required | Low — MES licensing is expensive |
| Integration with Business KPIs | Medium — custom DAX required | Medium — preconfigured KPIs | High — native MES integration |
| Accuracy and Data Reliability | High — direct SQL access, validated DAX | Medium — dependent on vendor data pipeline | High — native sensor integration |
| Ease of Implementation | High — team had Power BI and SQL skills | High — SaaS, minimal setup | Low — MES implementation is complex and slow |
| Customization and Scalability | High — full control over schema and visuals | Low — vendor-constrained customization | Medium — module configuration within MES limits |

**Final weighted scores:**
- A1 Power BI: 4.75 / 6 (79%)
- A2 Commercial Cloud: 4.00 / 6 (67%)
- A3 MES Module: 3.45 / 6 (57%)

---

## Decision

**Power BI dashboard selected.**

Despite the MES module's strong performance on integration and native accuracy,
its low scores on cost and ease of implementation made it the wrong choice for
a single production line pilot with a 7-week delivery window.

The commercial cloud option offered fast deployment but was eliminated on
customization — a SaaS platform's preconfigured KPI structure would not map
cleanly to Constantia Flexibles' specific downtime categories and product types.

Power BI offered the best overall balance and aligned with the team's existing
technical skills, allowing delivery effort to go into the product rather than
into learning a new platform.

---

## What This Framework Revealed

The scoring matrix made one thing visible that a pros/cons list would have
obscured: the MES module's apparent superiority on integration was outweighed
by its implementation complexity once criteria were weighted.

Without the pairwise weighting step, ease of implementation and cost could
easily have been undervalued in a discussion dominated by the technical appeal
of native MES integration. The structured framework prevented that bias.
