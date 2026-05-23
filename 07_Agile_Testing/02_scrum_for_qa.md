# Scrum for QA

Scrum is the most widely used Agile framework. To deliver high-quality increments, QA must participate in all scrum events.

---

## The QA Role in Scrum Ceremonies

### 1. Backlog Refinement (Grooming)
- **QA Action:** Review upcoming user stories. Flag ambiguous requirements, define expected edge cases, and clarify acceptance criteria.
- **Outcome:** Story points estimate is more accurate because QA effort is included.

### 2. Sprint Planning
- **QA Action:** Commit to stories based on team velocity. Highlight cross-browser, security, and automated regression needs.
- **Outcome:** Subtasks for writing test cases and testing execution are added to the sprint board.

### 3. Daily Standup (Daily Scrum)
- **QA Action:** Give a quick summary of what was tested yesterday, what will be tested today, and state any **Blockers** (e.g., QA env down, API broken).
- **Outcome:** Clear visibility of testing progression.

### 4. Sprint Review (Demo)
- **QA Action:** Assist developers or PO in demonstrating finished user stories to stakeholders.
- **Outcome:** Stakeholders see the verified features working correctly.

### 5. Sprint Retrospective
- **QA Action:** Share feedback on the sprint workflow.
  - *What went well:* "Automated smoke tests cut our release verification in half."
  - *What went wrong:* "Deployments to the QA environment were erratic, reducing our testing window."
- **Outcome:** Concrete action items to improve QA processes.

---

## 📌 Key Takeaways
- QA is **not** a separate team—QA engineers are integrated members of the Scrum team.
- Testing occurs *during* the sprint, not in a dedicated testing sprint afterward.
- Help the team avoid "Mini-Waterfalls" inside the 2-week sprint window.
