# Use Case Testing

## What is Use Case Testing?
**Use Case Testing** is a black-box testing technique that helps identify test cases that cover the system from end-to-end (entire transactions) based on **Use Cases** defined by Business Analysts or Product Owners.

> *"Tests designed to verify that actors can achieve their specific goals using the system."*

---

## Key Terms
- **Actor:** A user class, device, or external system interacting with the software.
- **Use Case:** A sequence of actions a system performs that yields an observable result of value to an actor.
- **Basic Flow (Happy Path):** The standard sequence of steps where everything works perfectly.
- **Alternative/Extension Flow:** Branching steps to handle variations or errors.

---

## Example Use Case: Withdraw Cash (ATM)

- **Actor:** Customer
- **Basic Flow:**
  1. Insert card.
  2. Enter valid PIN.
  3. Select withdraw cash.
  4. Enter amount.
  5. Collect cash & card.
- **Alternative Flow (Invalid PIN):**
  - Card remains, displays "Incorrect PIN", allows retry.
- **Extension Flow (Low Cash in ATM):**
  - Displays "ATM low cash", cancels transaction, ejects card.

---

## Designing Test Cases from Use Cases

Create test cases to cover:
1. **The Basic Flow:** TC_01: Withdraw ₹500 successfully.
2. **Alternative Flows:** TC_02: Enter wrong PIN once.
3. **Extension Flows:** TC_03: Try to withdraw ₹10,000 when ATM has only ₹5,000.

---

## 📌 Key Takeaways
- Focuses on real-world business value and integration points.
- Extremely useful for validating end-to-end integration and system testing.
- Helps identify requirements gaps and missing business rules early.
