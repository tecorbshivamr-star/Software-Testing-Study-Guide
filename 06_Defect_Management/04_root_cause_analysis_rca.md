# Root Cause Analysis (RCA)

## What is Root Cause Analysis?
**Root Cause Analysis (RCA)** is a systematic process of identifying the fundamental, underlying reason why a defect occurred. The goal of RCA is not just to fix the immediate bug, but to prevent the same type of bug from *ever happening again*.

> *"Fix the process, not just the code."*

---

## The 5 Whys Technique

The most common and effective RCA technique is "The 5 Whys". It involves asking "Why?" repeatedly until you drill down to the fundamental process failure.

**Example Scenario:** The application crashed in production during a promotional sale.

1. **Why did the application crash?**
   - Because the database ran out of concurrent connection limits.
2. **Why did the database run out of connections?**
   - Because the new promotional banner generated a massive spike in user traffic.
3. **Why didn't we anticipate this traffic spike?**
   - Because Performance Testing was not conducted for this specific release.
4. **Why wasn't Performance Testing conducted?**
   - Because the release was rushed, and the QA team was told to skip load testing to meet the deadline.
5. **Why was the QA team told to skip load testing?**
   - **Root Cause:** There is no strict "Definition of Done" policy preventing code deployment without performance sign-off.

**Corrective Action:** Implement a hard quality gate in the CI/CD pipeline that automatically blocks deployments if a baseline load test isn't executed.

---

## Other RCA Techniques
- **Fishbone Diagram (Ishikawa Diagram):** A visual tool mapping out categories of causes (People, Processes, Technology, Environment) that lead to a specific problem.
- **Fault Tree Analysis:** A top-down, deductive failure analysis using boolean logic to combine a series of lower-level events.

---

## When to Perform RCA?
RCA is time-consuming and should not be done for every minor UI typo. It should be triggered for:
- Critical Production incidents (Severity 0 / Severity 1 bugs).
- Security breaches or data leaks.
- Bugs that slip past QA and are reported by End Users (Escaped Defects).

---

## 📌 Key Takeaways
- RCA aims to find the "System" failure, not to point fingers at an individual developer or tester.
- The outcome of an RCA must be a concrete, actionable task (e.g., adding a new automated test suite, updating a checklist).
