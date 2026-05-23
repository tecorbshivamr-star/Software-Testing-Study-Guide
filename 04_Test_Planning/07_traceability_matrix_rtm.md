# Requirements Traceability Matrix (RTM)

## What is an RTM?
A **Requirements Traceability Matrix (RTM)** is a document that maps and traces user requirements with corresponding test cases and defects. It ensures that $100\%$ requirements coverage is met.

---

## Why is RTM Crucial?
- **Zero Gaps:** Ensures no requirement is missed during test execution.
- **Impact Analysis:** Helps understand which test cases need to run if a specific requirement changes.
- **Transparency:** Demonstrates compliance and testing depth to business stakeholders.

---

## Bidirectional Traceability

```
               FORWARD TRACEABILITY
     Requirements ────→ Test Cases ────→ Defects
         
               BACKWARD TRACEABILITY
     Defects ────→ Test Cases ────→ Requirements
```

- **Forward:** Tracks requirements to test cases to verify they are all tested.
- **Backward:** Tracks defects back to requirements to verify why a bug exists and what feature it impacts.

---

## Typical RTM Structure

| Req ID | Requirement Description | Test Case ID | Test Status | Defect ID |
|---|---|---|---|---|
| **REQ_01** | User can reset password | TC_PWD_001, TC_PWD_002 | Passed | — |
| **REQ_02** | User can pay via UPI | TC_PAY_045 | Failed | BUG_PAY_102 |

---

## 📌 Key Takeaways
- Keep the RTM updated as sprint changes happen.
- Use it during sprint reviews to prove $100\%$ validation.
- A critical tool for regulated industries (healthcare, finance).
