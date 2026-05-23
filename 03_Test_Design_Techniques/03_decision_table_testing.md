# Decision Table Testing

## What Is Decision Table Testing?

**Decision Table Testing** is a black-box test design technique used when a system's behavior depends on **combinations of multiple conditions**. It systematically captures complex business rules in a table format.

> *"Decision table testing ensures every combination of conditions and their resulting actions is tested."*

---

## When to Use Decision Tables

Use decision tables when:
- Multiple **conditions** combine to determine an **action/outcome**
- Business rules are **complex** with many if/else combinations
- You want to ensure **all combinations** are covered

---

## Structure of a Decision Table

```
┌──────────────────┬───┬───┬───┬───┐
│ CONDITIONS       │ R1│ R2│ R3│ R4│
├──────────────────┼───┼───┼───┼───┤
│ Condition 1      │ Y │ Y │ N │ N │
│ Condition 2      │ Y │ N │ Y │ N │
├──────────────────┼───┼───┼───┼───┤
│ ACTIONS          │   │   │   │   │
├──────────────────┼───┼───┼───┼───┤
│ Action 1         │ X │   │   │ X │
│ Action 2         │   │ X │ X │   │
└──────────────────┴───┴───┴───┴───┘
```
- **R1, R2...** = Rules (test cases)
- **Y/N** = Condition true/false
- **X** = Action taken

---

## Practical Example: Loan Eligibility

**Business Rules:**
- Must have **credit score ≥ 700** AND be **employed** → Approve loan
- Credit score ≥ 700 but **unemployed** → Approve with guarantor
- Credit score < 700 but **employed** → Manual review
- Credit score < 700 AND **unemployed** → Reject

| Conditions | R1 | R2 | R3 | R4 |
|------------|----|----|----|----|
| Credit score ≥ 700 | Y | Y | N | N |
| Employed | Y | N | Y | N |
| **Actions** | | | | |
| Approve Loan | ✅ | | | |
| Approve with Guarantor | | ✅ | | |
| Manual Review | | | ✅ | |
| Reject | | | | ✅ |

**Test Cases Generated = 4** (covering all combinations)

---

## Example 2: E-Commerce Discount

**Rules:**
- **Premium member** + order **> ₹1000** → 20% discount
- **Premium member** + order **≤ ₹1000** → 10% discount
- **Regular member** + order **> ₹1000** → 5% discount
- **Regular member** + order **≤ ₹1000** → No discount

| Conditions | R1 | R2 | R3 | R4 |
|------------|----|----|----|----|
| Premium Member | Y | Y | N | N |
| Order > ₹1000 | Y | N | Y | N |
| **Discount Applied** | 20% | 10% | 5% | 0% |

---

## How Many Test Cases?

For **N conditions** with Y/N values:
- Maximum combinations = **2^N**

| Conditions | Max Combinations |
|------------|-----------------|
| 2 | 4 |
| 3 | 8 |
| 4 | 16 |
| 5 | 32 |

Use **condition collapsing** to reduce: when an action is the same regardless of one condition, combine those rules.

---

## Decision Table vs Other Techniques

| Technique | Best For |
|-----------|---------|
| **Decision Table** | Multiple conditions, complex business rules |
| **EP** | Single input field, multiple value ranges |
| **BVA** | Numeric ranges, boundaries |
| **State Transition** | Systems with states (login/logout flow) |

---

## 📌 Key Takeaways

- Decision tables ensure **all condition combinations** are tested
- Creates **one test case per rule (column)**
- Reduces risk of **missed combination scenarios**
- Perfect for: insurance rules, loan eligibility, discount engines, tax calculators
- **2^N** maximum rules for N boolean conditions

---

*Related: [Equivalence Partitioning](./01_equivalence_partitioning.md) | [State Transition Testing](./04_state_transition_testing.md)*
