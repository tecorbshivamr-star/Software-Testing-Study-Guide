# Scenario-Based Interview Questions

> Interviewers use these questions to test your practical thinking, analytical skills, and QA mindset.

---

## Scenario 1: The Vending Machine

**Question:** "How would you test a vending machine?"

**How to Answer:** Don't just list random tests. Structure your answer by testing types.
1. **Functional Testing (Positive):**
   - Insert exact change, press valid code $\to$ gets item.
   - Insert excess change $\to$ gets item + correct change.
2. **Functional Testing (Negative/Edge Cases):**
   - Insert invalid coins/washers $\to$ rejected.
   - Select item that is out of stock $\to$ prompts to select another or returns money.
   - Insert less money than required $\to$ prompts for more.
3. **Mechanical/Physical (Usability):**
   - Does the item fall without breaking?
   - Are the buttons readable and responsive?
4. **Security Testing:**
   - Attempt to pull an item without paying.
   - Attempt to trick the coin sensor (e.g., coin on a string).
5. **Performance/Stress Testing:**
   - Rapidly press multiple buttons simultaneously.
   - Unplug and plug back in during a transaction (Recovery testing).

---

## Scenario 2: The Production Bug

**Question:** "You find a critical bug in production right after a release. What do you do?"

**How to Answer:** Show a calm, systematic approach.
1. **Verify:** Reproduce the bug myself to confirm it's real and not a user error or temporary network glitch.
2. **Assess Impact:** Determine how many users are affected and the business impact (e.g., is the payment gateway down?).
3. **Communicate:** Immediately alert the QA Lead, Dev Lead, and Product Manager.
4. **Containment/Rollback:** Discuss with the team if we need to rollback the deployment or push a hotfix.
5. **RCA (Root Cause Analysis):** Later, analyze *why* QA missed it (e.g., missing test case, missing test data, different environment configs) and update the regression suite so it never happens again.

---

## Scenario 3: Disagreeing with a Developer

**Question:** "A developer marks your bug as 'Not a Bug' or 'Working as Designed'. You disagree. How do you handle it?"

**How to Answer:** Show diplomacy and reliance on documentation.
1. **Don't argue:** Avoid emotional conflicts.
2. **Check the Source:** Review the requirements document, user story, or acceptance criteria.
3. **Discuss:** Have a quick chat with the developer to understand their perspective. Maybe they know a technical limitation I don't.
4. **Escalate (if needed):** If the requirement clearly supports my bug and the developer still refuses, escalate to the Product Owner or Business Analyst for final clarification on business intent.
5. **Document:** Log the decision in the ticket so there is a paper trail.

---

## Scenario 4: Tight Deadlines

**Question:** "You have 100 test cases to execute but only 2 hours before release. What is your strategy?"

**How to Answer:** Emphasize Risk-Based Testing.
1. **Communicate Risk:** Inform stakeholders that 100% coverage is impossible in the timeframe.
2. **Prioritize (Risk-Based Testing):**
   - Execute the **Smoke Test** suite first to ensure basic stability.
   - Execute **High Priority / Critical** test cases related to the new features.
   - Test the core business paths (e.g., Login, Checkout).
3. **Defer:** Skip low-priority, cosmetic, or edge-case tests.
4. **Sign-off with Caveats:** Provide a test report detailing exactly what was tested, what was skipped, and the known risks of releasing.

---

## Scenario 5: No Requirements

**Question:** "You are asked to test a feature, but there are no written requirements or documentation. How do you proceed?"

**How to Answer:** Show initiative and exploratory skills.
1. **Talk to Stakeholders:** Interview the Product Owner, Developer, or Designer to understand the goal of the feature.
2. **Competitor Analysis:** Look at similar apps (e.g., if testing a shopping cart, look at Amazon) to understand standard behavior.
3. **Exploratory Testing:** Use experience-based testing to explore the feature and learn its behavior.
4. **Create Documentation:** Write down the behaviors I observe and confirm with the PO if that is the *intended* behavior.

---

*Related: [Manual Testing Q&A](./01_manual_testing_interview_qa.md) | [Risk-Based Testing](../04_Test_Planning/04_risk_based_testing.md)*
