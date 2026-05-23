# Error Guessing

## What is Error Guessing?
**Error Guessing** is an experience-based test design technique where the tester uses their knowledge, intuition, and experience to **predict (guess) where defects are most likely to occur** in the application.

> *"Error guessing is the art of thinking like a bug, anticipating where developers might make mistakes."*

---

## Why Use Error Guessing?
- **Catches hidden bugs** that formal black-box techniques (EP/BVA) miss.
- **Saves time** by zeroing in on high-risk areas immediately.
- Excellent as a **supplement** to structured testing methodologies.

---

## Typical Scenarios / Guessing Checklist

When testing any interface, an experienced tester will guess errors for:

| Input Type | Error Guessing Scenarios |
|---|---|
| **Text Fields** | - Entering blank values / spaces.<br>- Special characters (`!@#$%^&*()_+`).<br>- HTML tags or SQL injection strings.<br>- Exceptionally long strings (buffer overflow checks). |
| **Numeric Fields** | - Zero (0) and negative values.<br>- Decimal inputs where integers are expected.<br>- Alphabetic characters. |
| **Dates** | - Feb 29 on non-leap years.<br>- Past dates when only future dates are valid.<br>- Format mismatches (DD-MM-YYYY vs MM-DD-YYYY). |
| **Buttons** | - Double-clicking a submit button (causes duplicate transactions).<br>- Clicking submit when validation errors are present. |

---

## 📌 Key Takeaways
- Error Guessing is highly dependent on the **experience and product domain knowledge** of the tester.
- It is **not** random monkey testing; it is structured, intuitive guessing.
- Should always be used **after** formal test case design (EP/BVA) is complete.
