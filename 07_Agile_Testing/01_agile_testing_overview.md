# Agile Testing Overview

## What Is Agile Testing?

**Agile Testing** is a testing practice that follows the principles of Agile software development. Testing is not a separate phase that happens after development — it is **continuous, collaborative, and integrated throughout every sprint**.

> *"In Agile, QA is not a gatekeeper at the end — it's a collaborator throughout the journey."*

---

## Agile vs Traditional (Waterfall) Testing

| Aspect | Waterfall Testing | Agile Testing |
|--------|-----------------|---------------|
| **When** | After development is complete | Throughout every sprint |
| **Feedback** | Late (weeks/months) | Immediate (days) |
| **Documentation** | Heavy | Lightweight (just enough) |
| **QA Role** | Separate phase | Integrated team member |
| **Test Cases** | Planned upfront | Evolve with user stories |
| **Defect Discovery** | Late (expensive) | Early (cheap) |
| **Release** | Big bang | Continuous, every sprint |

---

## The Agile Testing Quadrants

Defined by Brian Marick — 4 quadrants covering all test types:

```
                   Supporting Development
                            ↑
         Q2                 |                Q1
  [Business Facing]         |         [Technology Facing]
  Functional Tests          |         Unit Tests
  Story Tests               |         Component Tests
  Prototypes                |         (Automated)
  Simulations               |
  ─────────────────────────────────────────────────────
  Q3                        |                Q4
  [Business Facing]         |         [Technology Facing]
  Exploratory Testing       |         Performance Testing
  Usability Testing         |         Security Testing
  UAT                       |         Load Testing
  (Manual)                  |         (Tools)
                            ↓
                    Critiquing Product
```

---

## QA's Role in Agile Ceremonies

### Sprint Planning
- Review user stories, identify ambiguities
- Raise **"Definition of Done"** criteria
- Estimate test effort for each story

### Daily Standup
- Report testing progress and blockers
- Flag defects early

### Sprint Review / Demo
- Show tested features to stakeholders
- Verify against acceptance criteria

### Sprint Retrospective
- Discuss what went well in QA
- Identify process improvements

### Backlog Refinement (Three Amigos)
- QA + Dev + Product Owner review stories together
- QA asks: "What could go wrong? What edge cases exist?"

---

## Agile Testing Principles

1. **Test early and often** — Don't wait for "code complete"
2. **Collaborate** — QA, Dev, and PO work together
3. **Automate** — Repetitive tests must be automated
4. **Feedback first** — Prioritize fast feedback loops
5. **Test the right things** — Risk-based approach
6. **Working software over documentation** — Light-touch test docs
7. **Respond to change** — Test cases evolve with requirements

---

## Definition of Done (DoD) for QA

A user story is only **Done** when:
- [ ] Code implemented and reviewed
- [ ] Unit tests written (by developer)
- [ ] Test cases written and reviewed
- [ ] Functional tests executed — Pass
- [ ] Regression tests pass
- [ ] No open Critical/High defects
- [ ] Exploratory testing completed
- [ ] Acceptance criteria verified
- [ ] Performance acceptable
- [ ] QA sign-off given

---

## Agile Testing Approaches

| Approach | Description |
|----------|-------------|
| **TDD** | Write tests first, then code |
| **BDD** | Tests written in plain English (Gherkin) |
| **ATDD** | Acceptance tests drive development |
| **Shift-Left** | Start testing earlier in the cycle |
| **Continuous Testing** | Tests run automatically in CI/CD |
| **Exploratory Testing** | Unscripted, experience-based testing |

---

## 📌 Key Takeaways

- Agile testing = **continuous** testing, not a final phase
- QA must be involved from **Sprint Planning** to **Retrospective**
- The **Testing Quadrants** help plan the right tests at the right time
- **Definition of Done** is the QA team's contract with the sprint
- Without automation, Agile testing **cannot scale**

---

*Related: [Scrum for QA](./02_scrum_for_qa.md) | [TDD](./05_tdd_test_driven_development.md) | [BDD](./06_bdd_behavior_driven_development.md)*
