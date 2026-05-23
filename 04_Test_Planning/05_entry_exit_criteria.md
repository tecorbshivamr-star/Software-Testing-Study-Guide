# Entry and Exit Criteria

## Core Concept
Quality gates are used to manage transition points in the Software Testing Life Cycle (STLC). They ensure that tasks do not start without proper inputs, and do not stop without satisfying the defined quality standard.

---

## Entry Criteria
The mandatory conditions that must be fulfilled before a testing phase can begin.

| Test Phase | Common Entry Criteria |
|---|---|
| **Unit Testing** | Code compilation successful. |
| **System Testing** | - Code unit tests passed.<br>- Stable build deployed to QA environment.<br>- Test cases ready & approved. |
| **UAT (Acceptance)** | - System testing signed off.<br>- All high-severity bugs resolved.<br>- Customer environment mirrors production. |

---

## Exit Criteria
The quality thresholds that must be met to declare a testing phase complete.

| Test Phase | Common Exit Criteria |
|---|---|
| **System Testing** | - 100% test cases executed.<br>- Pass rate $\ge$ 95%.<br>- Zero open Blocker/Critical defects.<br>- Regression testing completed. |
| **UAT (Acceptance)** | - Business users complete all workflows.<br>- Formal client sign-off received.<br>- User documentation completed. |

---

## 📌 Key Takeaways
- Prevents garbage-in, garbage-out scenarios.
- Serves as an objective contract between developers, QA, and product owners.
- If Exit Criteria are not met, the build should **not** go to Production.
