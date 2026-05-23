# Black Box vs White Box vs Grey Box Testing

## Overview

| | Black Box | White Box | Grey Box |
|--|-----------|-----------|----------|
| **Knowledge of code** | None | Full | Partial |
| **Done by** | QA Testers | Developers | QA + Dev collaboration |
| **Based on** | Requirements/specs | Code logic | Architecture + requirements |
| **Technique** | Functional | Structural | Combined |
| **Also called** | Specification-based | Code-based, Glass box | Translucent box |

---

## 🟥 Black Box Testing

Tester has **NO knowledge** of internal code. Testing is based purely on input/output behavior against requirements.

### Techniques
- Equivalence Partitioning
- Boundary Value Analysis
- Decision Table Testing
- State Transition Testing
- Use Case Testing

### Advantages
- No programming knowledge required
- Tests from user's perspective
- Unbiased — tester doesn't know implementation

### Disadvantages
- Can't verify internal logic
- May miss code paths
- Redundant test cases possible

### When to Use
- Functional testing, UAT, System testing
- When requirements are well-defined

---

## ⬜ White Box Testing

Tester has **FULL knowledge** of internal code structure, logic, and implementation.

### Techniques
- **Statement Coverage** — every line of code executed at least once
- **Branch Coverage** — every branch (if/else) executed
- **Path Coverage** — every possible execution path
- **Condition Coverage** — every boolean condition tested

### Example
```python
def login(username, password):
    if username == "admin":        # Branch 1
        if password == "pass123":  # Branch 2
            return "Success"
        else:
            return "Wrong Password"
    else:
        return "User Not Found"
```
White box testing would create test cases to cover ALL branches above.

### Advantages
- Thorough — tests internal logic
- Finds hidden bugs in code paths
- Optimizes code quality

### Disadvantages
- Requires programming knowledge
- Time-consuming for large codebases
- Missing requirements not caught

### When to Use
- Unit testing, code reviews
- Security testing, optimization

---

## 🔷 Grey Box Testing

Tester has **PARTIAL knowledge** — knows the architecture and database schema but not the internal code.

### Common in
- API Testing (you know the endpoint contracts but not the implementation)
- Database Testing (you can query the DB to verify results)
- Integration Testing

### Example
Testing a "Transfer Funds" API:
- **Known (grey knowledge):** API endpoint, DB schema (transactions table)
- **Not known:** Internal banking logic code
- **Test approach:** Call API, then query DB to verify record was created correctly

### Advantages
- More effective than pure black box
- Finds integration issues
- Realistic — most QA engineers work this way

---

## Comparison Summary

| Factor | Black Box | White Box | Grey Box |
|--------|-----------|-----------|----------|
| Code Access | ❌ No | ✅ Full | 🔶 Partial |
| Requirement Focus | ✅ High | 🔶 Medium | ✅ High |
| Technical Skill Needed | Low | High | Medium |
| Coverage | Functional | Structural | Both |
| Best for | UAT, System | Unit | API, Integration |

---

## 📌 Key Takeaways

- **Black box** = user's perspective, no code knowledge
- **White box** = developer's perspective, full code knowledge
- **Grey box** = QA engineer's daily reality — partial knowledge
- Most real-world testing is **grey box** in practice

---

*Next → [Static vs Dynamic Testing](./08_static_vs_dynamic_testing.md)*
