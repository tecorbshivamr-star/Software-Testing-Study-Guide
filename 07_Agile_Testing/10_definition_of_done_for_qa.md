# Definition of Done (DoD) for QA

## What is DoD?
The **Definition of Done (DoD)** is a shared, standardized checklist that a Scrum team uses to ensure all quality gates are met before a user story is declared complete and releasable.

> *"If a story does not satisfy the Definition of Done, it is NOT done and cannot be released."*

---

## Typical QA Definition of Done Checklist

For every user story, verify the following are completed:

### 1. Development & Quality
- [ ] Code compiles successfully with no warnings.
- [ ] Unit tests pass with $\ge 80\%$ line coverage.
- [ ] Peer code review completed and approved.

### 2. Functional & Regression Testing
- [ ] All specified Acceptance Criteria verified.
- [ ] Functional test cases executed and passed.
- [ ] Exploratory testing conducted on the changed modules.
- [ ] Automated regression test suite passes with $100\%$ green status.

### 3. Defect Clearance
- [ ] Zero open Critical, Blocker, or High-severity defects.
- [ ] All logged defects tracked and linked to the story card.

### 4. Release & Documentation
- [ ] Documentation updated (Confluence, Wiki, or README).
- [ ] QA Sign-off given.

---

## 📌 Key Takeaways
- DoD is a **non-negotiable contract** between QA, Developers, and Product Owners.
- Helps teams deliver a high-quality product increment every single sprint.
- Protects the production build from slipping quality standards under deadline pressure.
