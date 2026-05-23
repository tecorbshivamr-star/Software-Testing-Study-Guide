# Defect Triage Process

## What is Defect Triage?
**Defect Triage** is a formal meeting (often weekly or bi-weekly) where the project team reviews newly reported bugs, evaluates them, and decides what action to take. 

The term "triage" comes from the medical field—sorting patients based on the urgency of their need for care.

---

## The Triage Team (The Three Amigos)
A successful triage meeting usually requires representatives from three areas:
1. **QA Lead:** Explains the bug, its severity, and how to reproduce it.
2. **Product Owner / Business Analyst:** Determines the business impact and assigns the *Priority*.
3. **Development Lead:** Assesses the technical complexity of the fix and estimates the effort required.

---

## The Triage Workflow

During the meeting, the team reviews each "New" defect and assigns it one of the following outcomes:

1. **Approve for Fixing:** The bug is valid. It is assigned a priority and placed into the Sprint backlog for a developer to fix.
2. **Reject (Not a Bug):** The behavior is intentional (Working as Designed), or the bug cannot be reproduced. The ticket is Closed.
3. **Defer / Backlog:** The bug is valid, but it is low priority. It will be fixed in a future release, not the current one.
4. **Duplicate:** The bug has already been reported in another ticket. The ticket is linked to the original and closed.
5. **Need More Info:** The developer cannot reproduce the bug with the current steps. Sent back to QA to provide more logs, screenshots, or clearer steps.

---

## Why is Triage Important?
- **Resource Allocation:** Development teams don't have time to fix every single bug. Triage ensures they focus on the bugs that matter most to the business.
- **Prevents Bottlenecks:** Keeps the bug tracking system (like Jira) clean and prevents a massive buildup of unresolved "New" tickets.
- **Alignment:** Ensures Dev, QA, and Product are all aligned on what behavior is actually a bug versus a feature.

---

## 📌 Key Takeaways
- QA identifies the bug, but Triage decides *if* and *when* it gets fixed.
- Triage meetings should be fast-paced and strictly timeboxed.
