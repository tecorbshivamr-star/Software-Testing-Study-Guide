# Manual Testing Interview Q&A — 100+ Questions

> Covers all levels: Fresher → Mid-level → Senior QA Engineer

---

## 🔵 Section 1: Fundamentals (Fresher Level)

**Q1. What is software testing?**
Testing is the process of evaluating software to find defects, verify it meets requirements, and ensure quality before release.

**Q2. What is the difference between a bug, defect, and failure?**
- **Error:** Human mistake (developer misunderstands requirement)
- **Defect/Bug:** Flaw in code/document introduced by the error
- **Failure:** Visible wrong behavior when defect is executed

**Q3. What are the 7 principles of software testing?**
1. Testing shows presence of defects (not absence)
2. Exhaustive testing is impossible
3. Early testing saves cost
4. Defect clustering (80/20 rule)
5. Pesticide paradox
6. Context-dependent
7. Absence-of-errors fallacy

**Q4. What is the difference between SDLC and STLC?**
SDLC covers the full development process (requirements → maintenance). STLC is the subset covering only testing activities (requirement analysis → test closure).

**Q5. What is the difference between Verification and Validation?**
- **Verification:** "Are we building the product right?" (static, process-focused)
- **Validation:** "Are we building the right product?" (dynamic, product-focused)

**Q6. What is a test case?**
A test case is a set of conditions, inputs, steps, and expected results used to verify a specific feature or behavior.

**Q7. What is a test scenario?**
A test scenario is a high-level description of what needs to be tested (the "what"), while test cases are the detailed steps (the "how").

**Q8. What is the difference between Smoke Testing and Sanity Testing?**
- **Smoke:** Wide, shallow test of entire app on a new build. Checks stability.
- **Sanity:** Narrow, focused test of a specific fix or feature. Checks correctness.

**Q9. What is Regression Testing?**
Re-running tests after code changes to ensure existing functionality still works correctly.

**Q10. What is UAT?**
User Acceptance Testing — end users verify the software meets their business requirements before go-live.

---

## 🟡 Section 2: Test Design (Mid Level)

**Q11. What is Equivalence Partitioning?**
Dividing input data into groups (partitions) where all values behave the same. Test one value per partition.

**Q12. What is Boundary Value Analysis?**
Testing values at the edges of valid ranges: min-1, min, min+1, max-1, max, max+1.

**Q13. What is Decision Table Testing?**
A technique for testing combinations of conditions. Each column is a rule (test case).

**Q14. What is State Transition Testing?**
Testing systems that have defined states. Tests verify transitions between states based on events.
Example: Login states → Logged Out → Logged In → Account Locked

**Q15. When would you use Decision Tables vs BVA?**
Decision Tables: when multiple conditions combine to determine outcome (business rules).
BVA: when single input has a numeric range with boundaries.

**Q16. What is the Testing Pyramid?**
A model showing ideal test distribution: Many unit tests → Some integration tests → Few E2E tests.

**Q17. What are the types of non-functional testing?**
Performance, Load, Stress, Security, Usability, Accessibility, Compatibility, Reliability.

**Q18. What is exploratory testing?**
Unscripted, experience-based testing where the tester simultaneously learns, designs, and executes tests. No predefined test cases.

**Q19. What is the difference between Black Box, White Box, and Grey Box testing?**
- Black Box: No code knowledge, tests based on requirements
- White Box: Full code knowledge, tests internal logic
- Grey Box: Partial knowledge (architecture + requirements)

**Q20. How do you decide what to test and what not to test?**
Risk-based testing: prioritize features based on probability of failure × impact on business.

---

## 🔴 Section 3: Test Planning & Management (Senior Level)

**Q21. What does a Test Plan contain?**
Scope, objectives, test strategy, test types, environment, entry/exit criteria, schedule, resources, risks, deliverables.

**Q22. What is a Test Strategy vs Test Plan?**
- **Test Strategy:** Organization-level document, high-level approach for all projects
- **Test Plan:** Project-specific document with detailed plan for one release

**Q23. What are Entry and Exit Criteria?**
- Entry: Conditions that must be met before testing begins (e.g., build deployed, env stable)
- Exit: Conditions that signal testing is complete (e.g., all TCs executed, no open critical bugs)

**Q24. How do you estimate test effort?**
Techniques: Function Point Analysis, Work Breakdown Structure, Use Case Point Method, Expert Judgment, Three-Point Estimation.

**Q25. What metrics do you track in testing?**
- Test Case Execution % (executed/total)
- Defect Density (defects/feature or module)
- Defect Removal Efficiency (bugs found in testing/total bugs)
- Pass Rate (%)
- Defect Leakage (bugs found in production/total bugs)

**Q26. What is Requirements Traceability Matrix (RTM)?**
A document that maps requirements to test cases, ensuring every requirement has test coverage and every test case traces to a requirement.

**Q27. What is risk-based testing?**
Prioritizing testing based on the probability and impact of potential failures. High-risk areas tested first.

**Q28. What is defect leakage?**
Defects that escape testing and are found in production. Formula: (Production bugs / Total bugs) × 100%.

**Q29. What is defect density?**
Number of defects found per unit (module, feature, or KLOC). Helps identify high-defect areas.

**Q30. How do you handle testing under tight deadlines?**
Risk-based testing — identify critical features, prioritize smoke + regression for critical paths, defer low-priority testing, communicate risk to stakeholders.

---

## 🟣 Section 4: Defect Management

**Q31. Explain the defect lifecycle.**
New → Assigned → Open → Fixed → Retest → Closed (or Reopened if fix didn't work)

**Q32. What is the difference between Severity and Priority?**
- **Severity:** Impact on the application (Critical/High/Medium/Low)
- **Priority:** Urgency to fix (P1/P2/P3/P4)
They can differ: High severity + Low priority (bug in rarely used admin report)

**Q33. What makes a good bug report?**
Clear title, environment details, exact reproduction steps, expected vs actual result, severity/priority, attachments (screenshot, logs).

**Q34. What is a showstopper defect?**
A Critical severity defect that blocks all further testing or makes the build unreleasable.

**Q35. What do you do if a developer says "it's not a bug"?**
1. Re-read the requirement
2. Check if there's a workaround
3. Reference the requirement document
4. Escalate to Business Analyst/Product Owner if disagreement continues
5. Document the decision

---

## 🟢 Section 5: Agile & Process

**Q36. How does testing work in Agile/Scrum?**
QA is involved throughout: Sprint Planning (review stories), daily standups (report blockers), Sprint Review (validate features), Retrospective (process improvement).

**Q37. What is the Definition of Done for QA?**
Test cases written, executed, pass rate met, no open Critical/High bugs, regression passed, QA sign-off given.

**Q38. What is Shift-Left testing?**
Starting testing activities earlier in SDLC — reviewing requirements, participating in design discussions, writing test cases during development.

**Q39. What is the Three Amigos meeting?**
Product Owner + Developer + QA discuss each user story before sprint to align on requirements, edge cases, and acceptance criteria.

**Q40. How do you write acceptance criteria?**
Using Given-When-Then (Gherkin) format or plain English. Must be specific, measurable, and testable.

---

## ⭐ Section 6: Scenario-Based Questions

**Q41. You find a critical bug 1 hour before release. What do you do?**
1. Reproduce and confirm the bug
2. Assess impact and business risk
3. Immediately notify QA Lead, Dev Lead, and Product Owner
4. Check if a quick fix is possible
5. If not fixable, recommend deferring release or releasing with known risk
6. Document the decision

**Q42. The developer says the bug you found is a feature, not a bug. How do you handle it?**
Check the requirements document. If requirements support the developer's claim, close the bug. If not, escalate to the Product Owner for clarification.

**Q43. How do you test a feature with no requirements?**
Ask stakeholders, research competitors, use exploratory testing based on common sense, document assumptions, and verify them.

**Q44. How would you test a search functionality?**
- Valid search term → results appear
- No results → "No results found" message
- Special characters in search → handled gracefully
- Empty search → validation or all results
- Very long string → handled
- SQL injection in search box → rejected
- Performance → search completes in <2 sec
- Case-insensitive search
- Partial word matches

**Q45. How would you test a payment gateway?**
- Valid card → payment success
- Invalid card number → rejected
- Expired card → rejected
- Insufficient balance → rejected
- Network timeout → graceful error handling
- Double payment prevention
- Refund flow
- Different card types (Visa, Mastercard, Amex)
- Security: card data not stored, HTTPS
- Performance under load

---

## 💡 Section 7: Tools & Technical

**Q46. What test management tools have you used?**
Jira (with Zephyr/Xray), TestRail, Azure DevOps, qTest, Confluence.

**Q47. What is Jira and how do you use it in QA?**
Jira is a project management tool. QA uses it to: track defects, link bugs to stories, manage test cycles, report on defect trends.

**Q48. How do you write a test plan in 30 minutes?**
Focus on: scope (in/out), test types, environment, entry/exit criteria, key risks, and schedule. Use a template.

**Q49. What is SQL and how do you use it in testing?**
SQL (Structured Query Language) is used to query databases to verify data integrity after UI actions.
Example: After a user registers, verify: `SELECT * FROM users WHERE email='test@qa.com';`

**Q50. What is an API and why do QA engineers test it?**
API is the communication layer between front-end and back-end. QA tests APIs because they're faster, more stable than UI tests, and can validate business logic directly.

---

## 📌 Quick Tips for the Interview

1. **STAR method** for scenario questions (Situation, Task, Action, Result)
2. Always mention **real examples** from your experience
3. Know the difference between **Severity vs Priority** — examiners love this
4. Explain **your testing process** for common features: login, search, payment
5. Mention **tools you've used**: Jira, Postman, Selenium, TestRail
6. Demonstrate **QA mindset**: always think about what can go wrong

---

*Related: [Automation Testing Q&A](./02_automation_testing_interview_qa.md) | [Scenario Based Questions](./05_scenario_based_questions.md)*
