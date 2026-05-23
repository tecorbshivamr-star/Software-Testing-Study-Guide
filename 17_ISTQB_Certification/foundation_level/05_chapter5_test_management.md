# ISTQB Foundation Level — Chapter 5: Test Management

> Study notes for **ISTQB CTFL (Certified Tester Foundation Level)** exam preparation.

---

## 5.1 Test Organization

### Roles in Testing
1. **Test Manager:** Responsible for overall test planning, monitoring, control, and strategy. Reports on metrics.
2. **Tester:** Responsible for reviewing requirements, setting up the test environment, writing test cases, executing tests, and logging defects.

### Independence of Testing
Degrees of independence (from lowest to highest):
1. No independence: Developers test their own code.
2. Developers test each other's code.
3. Independent test team within the project.
4. Independent test team outside the project (e.g., separate QA department).
5. External test specialists (outsourced QA).

---

## 5.2 Test Planning and Estimation

**Test Plan:** Documents the approach, resources, and schedule of testing activities.
- *Test Strategy:* General approach to testing (Organizational level).
- *Test Approach:* Implementation of the strategy for a specific project.

**Entry Criteria:** Conditions that must be met *before* testing can start (e.g., environment is ready, code is deployed).
**Exit Criteria:** Conditions that must be met to declare testing *finished* (e.g., 100% tests executed, 0 critical defects open).

### Test Estimation Techniques
1. **Metrics-based technique:** Estimating based on metrics of former, similar projects (e.g., Function Point Analysis).
2. **Expert-based technique:** Estimating based on the experience of owners of the testing tasks (e.g., Planning Poker, Wideband Delphi).

---

## 5.3 Test Monitoring and Control

- **Test Monitoring:** Continuously gathering metrics to evaluate progress against the test plan. (e.g., % of test cases executed, defect density).
- **Test Control:** Taking corrective actions when monitoring shows deviation from the plan. (e.g., re-prioritizing tests, adding resources).

---

## 5.4 Configuration Management
Ensures the integrity of work products (code, test scripts, requirements) by tracking versions and managing updates. Ensures testers are testing the correct version of the software with the correct version of test scripts.

---

## 5.5 Risks and Testing

**Risk** involves the possibility of a negative event. $\text{Level of Risk} = \text{Probability} \times \text{Impact}$.

1. **Product Risk (Quality Risk):** The risk that the software fails to satisfy user needs. (e.g., crash, security vulnerability, wrong calculation).
2. **Project Risk:** The risk that the project management processes fail. (e.g., budget run out, key tester gets sick, test environment is offline).

**Risk-Based Testing:** Prioritizing testing effort based on product risks. High-risk areas are tested first and more rigorously.

---

## 5.6 Defect Management

A defect report must provide developers with the information needed to reproduce and fix the bug.

**Common Defect Report Fields:**
- Identifier (ID)
- Title and summary
- Date, author
- Test environment details
- Steps to reproduce
- Expected and Actual results
- Severity (technical impact) and Priority (business urgency)
- Status (Open, Fixed, Closed, etc.)

---

## Sample Exam Questions — Chapter 5

**Q1.** Which of the following is a Product Risk?
- A) The test environment is not ready on time.
- B) A third-party API integration returns incorrect data. ✅
- C) The QA Lead leaves the company.
- D) The project budget is cut by 20%.

**Q2.** Who is typically responsible for setting up the test environment?
- A) Test Manager
- B) Project Manager
- C) Tester ✅
- D) Product Owner

---
*ISTQB Foundation Level — Chapter 5 Complete*  
*Next: [Chapter 6: Tool Support for Testing](./06_chapter6_tool_support.md)*
