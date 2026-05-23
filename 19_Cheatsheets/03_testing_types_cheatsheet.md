# Testing Types Cheatsheet

> Quick reference for all testing types — perfect for interview prep and daily use.

---

## Functional Testing Types

| Type | Purpose | Level | When |
|------|---------|-------|------|
| **Unit** | Test individual functions/methods | Code | During development |
| **Integration** | Test component interactions | Component | After unit testing |
| **System** | Test entire application E2E | System | After integration |
| **UAT** | Business users verify requirements | System | Before go-live |
| **Smoke** | Quick stability check (new build) | System | Every new build |
| **Sanity** | Verify specific fix/feature | Module | After a bug fix |
| **Regression** | Verify no breakage after changes | System | After any code change |
| **Exploratory** | Unscripted experience-based | System | Any time |
| **Monkey** | Random inputs to crash the app | System | Stability testing |

---

## Non-Functional Testing Types

| Type | Purpose | Tool |
|------|---------|------|
| **Performance** | Speed, responsiveness under load | JMeter, k6 |
| **Load** | Behavior at expected user volume | JMeter, Gatling |
| **Stress** | Behavior beyond normal capacity | JMeter, Locust |
| **Spike** | Sudden sharp traffic increase | JMeter, k6 |
| **Soak/Endurance** | Long duration stability | JMeter |
| **Scalability** | Scales proportionally with load | JMeter |
| **Security** | Vulnerabilities, OWASP Top 10 | OWASP ZAP, Burp Suite |
| **Usability** | User-friendliness, UX | Manual, UserTesting |
| **Accessibility** | WCAG compliance for disabilities | Axe, Lighthouse |
| **Compatibility** | Different browsers, OS, devices | BrowserStack |
| **Reliability** | Consistent behavior over time | — |
| **Recovery** | Behavior after failure/crash | — |
| **Portability** | Works in different environments | — |

---

## Testing Approaches

| Approach | Description |
|----------|-------------|
| **Black Box** | No code knowledge — tests requirements |
| **White Box** | Full code knowledge — tests logic/paths |
| **Grey Box** | Partial knowledge — API/DB access |
| **Static** | No execution — reviews, walkthroughs |
| **Dynamic** | Code executed — actual testing |
| **Manual** | Human executes tests |
| **Automated** | Scripts execute tests |

---

## Smoke vs Sanity vs Regression

| | Smoke | Sanity | Regression |
|--|-------|--------|------------|
| **Trigger** | New build | After bug fix | After any code change |
| **Scope** | Entire app (wide) | Specific feature (narrow) | Full or selective |
| **Depth** | Shallow | Deep (for that feature) | Deep |
| **Duration** | 30–60 min | 15–30 min | Hours |
| **Documentation** | Sometimes | Rarely | Always |
| **Goal** | Stable build? | Fix works? | Nothing broken? |

---

## Test Design Techniques

| Technique | When to Use | Example |
|-----------|------------|---------|
| **EP (Equiv. Partitioning)** | Input ranges/groups | Age: <18, 18-60, >60 |
| **BVA (Boundary Value)** | Numeric ranges | Age: 17,18,19,59,60,61 |
| **Decision Table** | Multiple conditions → outcomes | Loan eligibility rules |
| **State Transition** | Systems with states | Login/Logout/Locked |
| **Use Case** | User journeys | Complete checkout flow |
| **Error Guessing** | Experience-based | "What if null is passed?" |

---

## Defect Severity Levels

| Severity | Impact | Example |
|----------|--------|---------|
| 🔴 **Critical/Blocker** | App broken, data loss | Login doesn't work |
| 🟠 **High/Major** | Core feature broken | Payment fails |
| 🟡 **Medium** | Feature degraded, workaround exists | Search sorts wrong |
| 🟢 **Low/Minor** | Cosmetic issue | Button color off |

---

## Defect Priority Levels

| Priority | Urgency | SLA |
|----------|---------|-----|
| **P1** | Fix immediately | Same day |
| **P2** | Fix this sprint | 24–48 hrs |
| **P3** | Fix next sprint | 1 week |
| **P4** | Fix when time permits | Backlog |

---

## Testing in Agile

| Sprint Activity | QA Role |
|----------------|---------|
| Sprint Planning | Review stories, identify test cases |
| Daily Standup | Report testing progress/blockers |
| Three Amigos | Clarify requirements, edge cases |
| Sprint Review | Demo tested features |
| Retrospective | Improve QA process |

---

## Key Metrics

| Metric | Formula |
|--------|---------|
| Test Execution % | (Executed / Total) × 100 |
| Pass Rate | (Passed / Executed) × 100 |
| Defect Density | Defects / Feature or Module |
| Defect Leakage | (Prod bugs / Total bugs) × 100 |
| DRE | (Bugs in testing / Total bugs) × 100 |

---

*Shivam Rai | Software Testing MasterGuide*
