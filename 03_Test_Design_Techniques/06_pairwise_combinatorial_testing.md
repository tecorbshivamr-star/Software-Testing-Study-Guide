# Pairwise Combinatorial Testing

## What is Pairwise Testing?
**Pairwise Testing** (or **All-Pairs Testing**) is a black-box test design technique based on the observation that most defects are caused by either a single input parameter or an **interaction between two parameters**. 

Instead of testing all possible combinations (which grows exponentially), Pairwise Testing tests **every unique pair** of parameters at least once.

---

## The Combinatorial Explosion Problem
Suppose you are testing an application setup wizard with:
- **OS:** Windows, macOS, Linux (3 values)
- **Browser:** Chrome, Firefox, Safari (3 values)
- **Database:** PostgreSQL, MySQL (2 values)

**Total Exhaustive Combinations:** $3 \times 3 \times 2 = 18$ combinations.

If you have 10 parameters with 3 options each, exhaustive testing is **59,049** combinations. Impossible!

Pairwise reduces this dramatically while maintaining outstanding defect-detection rates.

---

## How Pairwise Works
Using a mathematical tool (like Orthogonal Arrays or PICT), the combinations are collapsed.

**Pairwise Test Suite (Only 9 Tests instead of 18):**

| Test Case | OS | Browser | Database |
|---|---|---|---|
| **TC1** | Windows | Chrome | PostgreSQL |
| **TC2** | Windows | Firefox | MySQL |
| **TC3** | Windows | Safari | PostgreSQL |
| **TC4** | macOS | Chrome | MySQL |
| **TC5** | macOS | Firefox | PostgreSQL |
| **TC6** | macOS | Safari | MySQL |
| **TC7** | Linux | Chrome | PostgreSQL |
| **TC8** | Linux | Firefox | MySQL |
| **TC9** | Linux | Safari | PostgreSQL |

*Notice:* Every pair (e.g., Windows + Chrome, macOS + MySQL, Safari + PostgreSQL) is tested at least once.

---

## Pairwise Testing Tools
- **PICT:** Microsoft's command-line tool (open-source).
- **AllPairs:** Python library for generating pairwise test vectors.
- **Hexawise:** Advanced SaaS combinatorial testing tool.

---

## 📌 Key Takeaways
- Saves massive time and execution costs in complex systems.
- Ensures excellent coverage for configuration matrices, operating systems, and form setups.
- Scientifically proven to catch up to $80-90\%$ of configuration defects.
