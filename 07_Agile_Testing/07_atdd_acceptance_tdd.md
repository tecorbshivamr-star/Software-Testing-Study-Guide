# Acceptance Test-Driven Development (ATDD)

## What is ATDD?
**Acceptance Test-Driven Development (ATDD)** is a collaborative development methodology that extends the principles of TDD. Instead of developers writing isolated unit tests, ATDD involves the **Three Amigos (Developer, QA, Product Owner)** writing high-level **Acceptance Tests** before any coding begins.

> *"Ensure the code does exactly what the business expects before writing a single line of implementation."*

---

## TDD vs BDD vs ATDD

| Aspect | TDD | BDD | ATDD |
|---|---|---|---|
| **Level** | Unit / Developer level | Business / Behavioral level | Requirements / Acceptance level |
| **Focus** | How the system is coded | How the user behaves | What features must be accepted |
| **Participant** | Developer | Developer, QA, Business | PO, Developer, QA (Collaboration) |
| **Example** | Code: `assert calculate(5) == 10` | Gherkin: `Given user has 5 points...` | Spec: Table of Input & Expected Outputs |

---

## The ATDD Process Flow

```
1. Discuss & Define Requirements (Three Amigos)
                 ↓
2. Design Acceptance Tests (Real examples/tables)
                 ↓
3. Code Development (Develop code to pass acceptance tests)
                 ↓
4. Automated Test Run & Validation
                 ↓
5. Feature Accepted & Signed Off
```

---

## 📌 Key Takeaways
- ATDD aligns developers, testers, and stakeholders to the exact same goals.
- Reduces requirements gaps and re-work rates to nearly zero.
- Acceptance tests are verified automatically during integration.
