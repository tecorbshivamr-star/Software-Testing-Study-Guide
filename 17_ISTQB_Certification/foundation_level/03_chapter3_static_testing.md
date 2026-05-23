# ISTQB Foundation Level — Chapter 3: Static Testing

> Study notes for **ISTQB CTFL (Certified Tester Foundation Level)** exam preparation.

---

## 3.1 Static Testing Basics

**Static Testing** relies on the manual examination of work products (reviews) or tool-driven evaluation of code/models (static analysis) *without executing the code*.

### What Can Be Examined?
Almost any work product:
- Requirements specifications
- Epics, user stories, acceptance criteria
- Architecture and design specifications
- Code
- Test plans, test cases, test scripts
- User manuals

### Static vs. Dynamic Testing
- **Static Testing:** Finds the *causes* of failures (defects) directly. e.g., finding a variable that is not initialized.
- **Dynamic Testing:** Finds the *failures* caused by defects. e.g., the program crashes when it runs.

**Benefits of Static Testing:**
- Detects defects early (Shift-Left).
- Cheaper to fix defects found before execution.
- Finds defects that dynamic testing easily misses (e.g., unreachable code, design flaws).

---

## 3.2 Review Process

Reviews vary from informal to highly formal. 

### Roles in a Formal Review
1. **Author:** Creates the work product, fixes defects found.
2. **Management:** Responsible for planning, assigning resources, and deciding if reviews are needed.
3. **Facilitator (Moderator):** Ensures effective running of meetings, manages time, mediates disputes.
4. **Review Leader:** Takes overall responsibility for the review.
5. **Reviewers (Inspectors):** Subject matter experts who identify and describe anomalies (defects).
6. **Scribe (Recorder):** Documents anomalies, decisions, and new defects found during the meeting.

---

## 3.3 Types of Reviews

| Review Type | Characteristics | Formality |
|---|---|---|
| **Informal Review** | No formal process. e.g., Buddy check, pairing. Widely used in Agile. | Low |
| **Walkthrough** | Led by the Author. Scenario execution, dry runs. Used for learning and gaining consensus. | Low to Medium |
| **Technical Review** | Documented, defined defect-detection process. Led by a trained moderator or tech expert. Peer review. | Medium to High |
| **Inspection** | Most formal. Led by a trained Moderator (not the author). Uses checklists, metrics are collected, defined entry/exit criteria. | High |

---

## 3.4 Review Techniques

Techniques reviewers use to uncover defects during the individual review phase:
1. **Ad hoc:** Reviewers are given little/no guidance. Highly dependent on reviewer skills.
2. **Checklist-based:** Reviewers use a list of questions or rules to guide the review.
3. **Scenarios and dry runs:** Reviewers are provided structured guidelines to process the work product like a user would.
4. **Perspective-based:** Reviewers evaluate the product from different viewpoints (e.g., end-user, system administrator, tester).
5. **Role-based:** Reviewers act as specific stakeholder roles (e.g., experienced user, manager).

---

## Sample Exam Questions — Chapter 3

**Q1.** Which of the following review types is usually led by the author?
- A) Inspection
- B) Technical Review
- C) Walkthrough ✅
- D) Static Analysis

**Q2.** Which defect is easier to find in static testing than dynamic testing?
- A) A memory leak under heavy load.
- B) A deviation from coding standards. ✅
- C) A UI rendering issue on a specific browser.
- D) An integration failure between two APIs.

---
*ISTQB Foundation Level — Chapter 3 Complete*  
*Next: [Chapter 4: Test Techniques](./04_chapter4_test_techniques.md)*
