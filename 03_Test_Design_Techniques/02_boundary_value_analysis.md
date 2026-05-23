# Boundary Value Analysis (BVA)

## What Is Boundary Value Analysis?

**Boundary Value Analysis (BVA)** is a black-box test design technique that focuses on testing **values at the boundaries** of valid and invalid input ranges, because errors tend to occur at the edges of input domains.

> *"Bugs love boundaries. Test the edges, not just the middle."*

---

## Why Do Boundaries Matter?

Developers commonly make **off-by-one errors**:
- `age > 18` instead of `age >= 18`
- `price < 1000` instead of `price <= 1000`
- Loop running `n-1` times instead of `n` times

These errors are at boundaries — BVA catches them.

---

## The Core Rule: 3-Point BVA

For any valid range [min, max], test:

| Test Point | Value | Expected |
|-----------|-------|---------|
| Just below minimum | min - 1 | ❌ Invalid/Rejected |
| Minimum (boundary) | min | ✅ Valid/Accepted |
| Just above minimum | min + 1 | ✅ Valid/Accepted |
| Just below maximum | max - 1 | ✅ Valid/Accepted |
| Maximum (boundary) | max | ✅ Valid/Accepted |
| Just above maximum | max + 1 | ❌ Invalid/Rejected |

---

## Practical Example: Age Validation

**Requirement:** Age must be between **18 and 60** (inclusive) to register.

| Test Case | Input | Expected | Reason |
|-----------|-------|---------|--------|
| BVA_001 | 17 | ❌ Rejected | Just below minimum |
| BVA_002 | 18 | ✅ Accepted | Minimum boundary |
| BVA_003 | 19 | ✅ Accepted | Just above minimum |
| BVA_004 | 59 | ✅ Accepted | Just below maximum |
| BVA_005 | 60 | ✅ Accepted | Maximum boundary |
| BVA_006 | 61 | ❌ Rejected | Just above maximum |

---

## Example 2: Password Length

**Requirement:** Password must be **8 to 20 characters**.

| TC | Length | Value | Expected |
|----|--------|-------|---------|
| BVA_001 | 7 | `abcdefg` | ❌ Too short |
| BVA_002 | 8 | `abcdefgh` | ✅ Valid |
| BVA_003 | 9 | `abcdefghi` | ✅ Valid |
| BVA_004 | 19 | 19 chars | ✅ Valid |
| BVA_005 | 20 | 20 chars | ✅ Valid |
| BVA_006 | 21 | 21 chars | ❌ Too long |

---

## Example 3: E-Commerce Discount

**Requirement:** Free shipping for orders **₹500 to ₹10,000**.

| TC | Order Value | Expected |
|----|-------------|---------|
| BVA_001 | ₹499 | ❌ No free shipping |
| BVA_002 | ₹500 | ✅ Free shipping |
| BVA_003 | ₹501 | ✅ Free shipping |
| BVA_004 | ₹9,999 | ✅ Free shipping |
| BVA_005 | ₹10,000 | ✅ Free shipping |
| BVA_006 | ₹10,001 | ❌ No free shipping |

---

## BVA vs Equivalence Partitioning

| Aspect | BVA | EP |
|--------|-----|----|
| **Focus** | Boundary values | Partitions/groups |
| **Test points** | Edges of ranges | One value per partition |
| **Defects found** | Off-by-one errors | Wrong range errors |
| **Used together?** | ✅ Yes — complement each other | ✅ Yes |

**Best practice:** Use **EP first** (to identify partitions) then **BVA** (to test edges of those partitions).

---

## 📌 Key Takeaways

- Test **min-1, min, min+1, max-1, max, max+1** for any numeric range
- BVA catches **off-by-one errors** — the most common developer mistake
- Always apply BVA with **Equivalence Partitioning**
- Works for: numbers, dates, string lengths, file sizes, list sizes
- ISTQB exam frequently tests BVA — know the 3-point and 2-point variations

---

*Related: [Equivalence Partitioning](./01_equivalence_partitioning.md) | [Decision Table Testing](./03_decision_table_testing.md)*
