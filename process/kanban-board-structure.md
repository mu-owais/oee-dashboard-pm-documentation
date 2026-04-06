# Kanban Board Structure — Jira

## Board Setup

- **Space name:** Constantia X OTH OEE Dashboard
- **Board type:** Kanban, team-managed
- **Project lead:** Muhammad Awais
- **Tool:** Jira (Atlassian)

Screenshots of the board are in /assets.

---

## Work Items — Full Ticket List

| Ticket | Milestone | Title | Owner | Status |
|---|---|---|---|---|
| KAN-1 | M4 | Final Presentation | Muhammad Awais | Done |
| KAN-2 | M4 | Documentation (Project Report) | Muhammad Awais | Done |
| KAN-3 | M1 | Dataset Exploration and Import | Muhammad Awais | Done |
| KAN-4 | M1 | Build Star Schema Data Model | Muhammad Awais + Zohaib Sultan | Done |
| KAN-5 | M1 | Synthetic Machine Data Generation | Zohaib Sultan | Done |
| KAN-6 | M1 | Develop Core DAX Measures | Muhammad Awais | Done |
| KAN-7 | M2 | Corporate Canvas Setup | Muhammad Awais | Done |
| KAN-8 | M2 | Data Cleaning and Validation | Muhammad Awais | Done |
| KAN-9 | M2 | Four Dashboard Panel Creation | Muhammad Awais + Kashif Sultan | Done |
| KAN-10 | M2 | Develop Trend Visualizations | Muhammad Awais | Done |
| KAN-11 | M3 | OEE Calculation Validation | Muhammad Awais | Done |
| KAN-12 | M3 | Design Refinement and UI Polish | Muhammad Awais | Done |

---

## Workflow States

Each ticket moved through four states:

- **To Do** — defined and ready to start
- **In Progress** — actively being worked on
- **In Review** — completed, pending validation or feedback
- **Done** — validated and closed

---

## How the Board Was Managed

Tickets were written by the Project Manager (Muhammad Awais) at the start
of each milestone. Descriptions were written to be actionable without
requiring a follow-up meeting — owner, deliverable, and acceptance condition
were included in every ticket.

Progress was tracked by milestone release in Jira. Four release versions
were created (Milestone 1 through Milestone 4), each with a defined start
date, release date, and list of deliverables. All four releases were
marked as Released on schedule.

The Kanban approach was chosen over Scrum sprints because the team was
working across multiple work packages simultaneously rather than in
synchronized sprint cycles. Kanban allowed parallel progress on data
engineering, frontend, and QA tracks without enforcing artificial sprint
boundaries on work that did not naturally align to two-week cycles.
