# Risk-Based Testing

## What is Risk-Based Testing?
**Risk-Based Testing (RBT)** is a testing methodology that prioritizes testing activities based on the **risk of product failure**. It uses risk analysis to focus resources on critical features first.

$$\text{Risk Score} = \text{Probability of Failure} \times \text{Impact of Failure}$$

---

## Risk Assessment Matrix

| Probability \ Impact | Minor (1) | Major (2) | Critical (3) |
|---|---|---|---|
| **Low (1)** | 1 (Low) | 2 (Medium) | 3 (High) |
| **Medium (2)** | 2 (Medium) | 4 (High) | 6 (Critical) |
| **High (3)** | 3 (High) | 6 (Critical) | 9 (Critical) |

---

## Prioritizing Test Effort Using Risks

- **Critical Risk (Score 6-9):**
  - *Action:* Heavy functional, regression, automated, and edge-case testing. First priority.
  - *Example:* Credit card payment transactions.

- **High/Medium Risk (Score 3-4):**
  - *Action:* Standard functional and regression coverage. Second priority.
  - *Example:* Order cancellation flow.

- **Low Risk (Score 1-2):**
  - *Action:* Basic smoke test or exploratory checks. Defer if time is limited.
  - *Example:* User profile photo update cosmetics.

---

## 📌 Key Takeaways
- Ensures you test the **most critical** aspects of the system first.
- Helps teams make informed decisions when deadlines are compressed.
- Reduces high-impact production failures drastically.
