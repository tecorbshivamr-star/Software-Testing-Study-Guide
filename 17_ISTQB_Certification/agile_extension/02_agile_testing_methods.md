# ISTQB Agile Tester Extension — Chapter 2: Agile Testing Methods

> Study notes for **ISTQB Agile Tester Extension** exam preparation.

---

## 2.1 Agile Testing Principles, Practices, and Processes

### Continuous Testing
Testing is not a phase at the end of the sprint; it is an ongoing activity that happens concurrently with development.
- Continuous Integration (CI) and Continuous Delivery (CD) pipelines heavily rely on automated tests to provide immediate feedback.

### Test-Driven Development (TDD)
Writing automated unit tests *before* writing the production code.
- Follows the **Red-Green-Refactor** cycle.
- Primarily a developer practice, but testers help define the test cases.

### Acceptance Test-Driven Development (ATDD)
Writing acceptance tests *before* development begins, collaboratively defined by the whole team (Three Amigos: PO, Dev, Tester).
- Helps clarify requirements and ensure everyone has the same understanding of "Done."

### Behavior-Driven Development (BDD)
A variant of TDD that focuses on the behavior of the system from the user's perspective, using natural language formats (Given/When/Then).
- Facilitates communication between business stakeholders and technical team members.

---

## 2.2 Assessing Quality Risks and Estimating Test Effort

### Quality Risk Analysis in Agile
Risk analysis happens frequently, often during sprint planning or release planning.
- The team identifies risks to product quality and prioritizes testing based on those risks.
- Helps decide what to test manually, what to automate, and what not to test.

### Estimating Test Effort in Agile
Agile teams estimate the effort for the *entire* user story, which includes development, testing, and other tasks required to meet the Definition of Done (DoD).
- **Techniques:** Planning Poker, T-shirt sizing.
- Estimation is a collaborative team effort.

---

## 2.3 Techniques in Agile Projects

### Exploratory Testing
Unscripted, experience-based testing where test design, execution, and learning happen concurrently.
- Highly valuable in Agile because it finds defects that scripted tests miss and adapts quickly to changes.
- Often guided by a **Test Charter** and managed in **Timeboxes** (Sessions).

### Session-Based Testing
A structured approach to exploratory testing.
- Testers document their findings, bugs, and ideas in a session sheet during a fixed, uninterrupted timebox.

---

## Sample Exam Questions — Chapter 2

**Q1.** Which development approach involves writing tests from the user's perspective using natural language (e.g., Given/When/Then)?
- A) Test-Driven Development (TDD)
- B) Behavior-Driven Development (BDD) ✅
- C) Keyword-Driven Testing
- D) Exploratory Testing

**Q2.** How is test estimation typically handled in an Agile team using Planning Poker?
- A) The Test Manager estimates all testing tasks separately.
- B) Testing effort is estimated collaboratively by the whole team as part of the overall user story estimation. ✅
- C) Estimation is not done in Agile; the team just tests until the timebox ends.
- D) Only the developers estimate the effort, and testers adapt to it.

---
*ISTQB Agile Tester Extension — Chapter 2 Complete*
