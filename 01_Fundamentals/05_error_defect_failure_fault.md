# Error vs Defect vs Failure vs Fault

## The Chain of Events

```
Human makes ERROR
      ↓
Code contains FAULT/DEFECT
      ↓
Software exhibits FAILURE
```

---

## Definitions

### 🧠 Error
An **error** is a human mistake made by a developer, analyst, or tester that introduces a problem.

> **Example:** A developer misunderstands the requirement that "age must be ≥ 18" and writes code checking `age > 18` (missing the equals case — 18-year-olds are rejected).

---

### 🐛 Defect (Bug / Fault)
A **defect** is the result of the error — a flaw in the code, design, or document that causes the system to behave incorrectly.

> **Example:** The code `if age > 18` instead of `if age >= 18` is the defect in the source code.

---

### 💥 Failure
A **failure** is the observable incorrect behavior of the software when the defect is executed.

> **Example:** A user aged exactly 18 tries to register and gets the error "You must be 18 or older" — this is the failure the user experiences.

---

### 🔧 Fault
A **fault** is often used interchangeably with defect. In some standards (IEEE), fault specifically refers to the **incorrect step, process, or data definition** in a program.

---

## Comparison Table

| Term | Who Creates It | Where It Lives | When Visible |
|------|---------------|----------------|--------------|
| **Error** | Human (dev, analyst, QA) | In the mind | When person makes a mistake |
| **Defect/Bug/Fault** | Error introduces it | In code/doc/design | When code is reviewed or executed |
| **Failure** | Defect causes it | In the running system | When user/tester observes wrong behavior |

---

## Can a Defect Exist Without a Failure?

**YES!** A defect in code may never cause a failure if:
- That code path is never executed
- The defect is masked by another defect
- The environment doesn't trigger it

> **Example:** A bug in the "dark mode" color of the error message exists, but only users in dark mode who trigger that specific error will ever see the failure.

---

## Real-World Examples

| Error | Defect | Failure |
|-------|--------|---------|
| Dev forgot to add null check | `if (user.name)` missing null check | App crashes when user has no name |
| Analyst wrote wrong formula | Discount calculated as 10% instead of 15% | Customer overcharged at checkout |
| QA wrote wrong expected result | Test passes incorrectly | Bug ships to production undetected |

---

## Defect Vs Bug Vs Issue

| Term | Usage |
|------|-------|
| **Bug** | Informal, common term in Agile/daily use |
| **Defect** | Formal term in test documentation |
| **Issue** | Jira term — broader (includes questions, tasks, improvements) |
| **Incident** | Production failure report |

---

## 📌 Key Takeaways

- **Error** → Human mistake  
- **Defect** → Flaw in artifact (code/design)  
- **Failure** → Visible wrong behavior  
- Not all defects cause failures (dormant bugs)
- ISTQB exam uses these terms precisely — know the chain!

---

*Next → [Testing Pyramid](./06_testing_pyramid.md)*
