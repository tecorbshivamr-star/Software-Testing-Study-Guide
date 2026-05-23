# Test Case vs. Test Scenario

Understanding the distinction between a Test Scenario and a Test Case is a fundamental skill for any QA engineer.

---

## What is a Test Scenario?
A **Test Scenario** is a high-level, one-line statement that describes *what* needs to be tested. It represents a real-world user action or a specific end-to-end functionality.
- **Focus:** The "What".
- **Detail Level:** Low.
- **Example:** "Verify the User Login Functionality."

---

## What is a Test Case?
A **Test Case** is a detailed, step-by-step document that specifies *how* to test the scenario. It includes prerequisites, exact input data, execution steps, and the expected result.
- **Focus:** The "How".
- **Detail Level:** Extremely High.
- **Example:** "Verify that a user can login successfully when providing a valid registered email and the correct password."

---

## The Relationship (1 to Many)

A single Test Scenario usually generates multiple Test Cases (covering positive, negative, and edge-case paths).

```
[ Test Scenario: Verify Checkout Flow ]
       │
       ├─── Test Case 1: Checkout with valid Credit Card (Positive)
       ├─── Test Case 2: Checkout with expired Credit Card (Negative)
       ├─── Test Case 3: Checkout with empty cart (Negative)
       └─── Test Case 4: Checkout using PayPal (Positive)
```

---

## Comparison Table

| Feature | Test Scenario | Test Case |
|---|---|---|
| **Definition** | A high-level functionality to be tested. | A set of detailed steps and data to verify a specific path. |
| **Creation Time** | Faster to write. | Slower to write. |
| **Flexibility** | High (Adaptable as requirements evolve). | Low (Must be rewritten if UI changes). |
| **Best Used For** | Agile environments, Exploratory testing. | Strict regulatory environments, Automation scripting. |
| **Example** | "Check Login" | "Enter 'user@test.com', enter 'Pass123', click Login, verify welcome banner." |

---

## 📌 Key Takeaways
- Modern Agile teams often rely heavily on **Test Scenarios** (often written as BDD Given/When/Then criteria) to save documentation time.
- Automation scripts strictly require the granular detail of a **Test Case**.
