# Equivalence Partitioning

## What Is Equivalence Partitioning?

**Equivalence Partitioning (EP)** is a black-box test design technique that **divides input data into groups (partitions)** where all values in a partition are expected to behave the same way. Only one value from each partition needs to be tested.

> *"If one value in a group works, all values in that group will work. If one fails, all fail."*

---

## Why Use Equivalence Partitioning?

- Reduces the number of test cases **without sacrificing coverage**
- Applies the principle: testing all values in a group is redundant
- Makes testing **systematic** and **efficient**

---

## Types of Partitions

| Partition Type | Description |
|---------------|-------------|
| **Valid partition** | Inputs the system should accept |
| **Invalid partition** | Inputs the system should reject |

---

## Step-by-Step Example: Age Validation

**Requirement:** Only users aged 18–60 can register.

### Step 1: Identify Partitions

| Partition | Range | Type |
|-----------|-------|------|
| P1 | Age < 18 | ❌ Invalid |
| P2 | Age 18–60 | ✅ Valid |
| P3 | Age > 60 | ❌ Invalid |

### Step 2: Pick One Value from Each Partition

| TC | Partition | Test Value | Expected |
|----|-----------|-----------|---------|
| EP_001 | P1 (invalid) | 15 | ❌ Rejected |
| EP_002 | P2 (valid) | 30 | ✅ Accepted |
| EP_003 | P3 (invalid) | 70 | ❌ Rejected |

**Result:** 3 test cases instead of testing every possible age (0–120+)!

---

## Example 2: Email Validation

**Requirement:** Email must be a valid email format.

| Partition | Examples | Type |
|-----------|---------|------|
| Valid email | `user@gmail.com`, `name@company.org` | ✅ Valid |
| Missing @ | `usergmail.com`, `userATgmail` | ❌ Invalid |
| Missing domain | `user@`, `user@.com` | ❌ Invalid |
| Empty field | _(blank)_ | ❌ Invalid |
| Special chars | `user!#$@gmail.com` | ❌ Invalid |

Test one value from each partition → 5 test cases cover the whole space.

---

## Example 3: Discount Code

**Requirement:** Discount code must be exactly 8 alphanumeric characters.

| Partition | Example | Type |
|-----------|---------|------|
| Valid: 8 alphanumeric | `SAVE2024` | ✅ Valid |
| Invalid: < 8 chars | `SAVE` | ❌ Invalid |
| Invalid: > 8 chars | `DISCOUNT99` | ❌ Invalid |
| Invalid: special chars | `SAV!@#$%` | ❌ Invalid |
| Invalid: empty | _(blank)_ | ❌ Invalid |

---

## EP + BVA Together (Best Practice)

EP identifies the **partitions**. BVA tests the **edges** of those partitions.

```
     Invalid     |      Valid      |    Invalid
   (age < 18)    |  (age 18–60)   |   (age > 60)
─────────────────|─────────────────|─────────────
 EP: Test age=15 | EP: Test age=30 | EP: Test age=70
 BVA: Test 17,18 |  BVA: Test 18, |  BVA: Test 60,
                 |        19,59,60 |        61
```

---

## 📌 Key Takeaways

- EP **reduces test cases** while maintaining good coverage
- Always identify **valid AND invalid** partitions
- Pick **one representative value** from each partition
- Combine with **BVA** for maximum effectiveness
- EP is a core ISTQB exam topic

---

*Related: [Boundary Value Analysis](./02_boundary_value_analysis.md) | [Decision Table Testing](./03_decision_table_testing.md)*
