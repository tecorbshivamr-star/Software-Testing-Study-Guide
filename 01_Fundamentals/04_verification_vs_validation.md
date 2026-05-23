# Verification vs Validation

## The Simple Difference

| | Verification | Validation |
|--|-------------|------------|
| **Question** | "Are we building the product **right**?" | "Are we building the **right** product?" |
| **Focus** | Process | Product |
| **When** | During development | After development |
| **Checks** | Requirements, Design, Code | Working software |
| **Done by** | QA team (reviews, walkthroughs) | QA team + end users (testing, UAT) |
| **Type** | Static testing (no execution) | Dynamic testing (execution needed) |

---

## Verification

Verification ensures the software **conforms to specifications**. It checks whether the product is being built according to the design and requirements.

### Verification Techniques
- **Reviews** — Formal or informal examination of documents
- **Walkthroughs** — Author guides team through the document
- **Inspections** — Formal structured review with roles (moderator, author, inspectors)
- **Static Analysis** — Tools that analyze code without executing it (SonarQube, ESLint)

### Examples of Verification
- Reviewing the System Requirements Specification (SRS)
- Reviewing the design document against requirements
- Code review by peers
- Reviewing test cases against requirements

---

## Validation

Validation ensures the software **meets user needs and expectations**. It confirms the final product works correctly.

### Validation Techniques
- **Functional Testing** — Does it do what users need?
- **User Acceptance Testing (UAT)** — End users verify the system
- **Integration Testing** — Do all components work together?
- **System Testing** — End-to-end system behavior

### Examples of Validation
- Running the application and testing login functionality
- Executing test cases and comparing with expected results
- UAT where business users test real workflows
- Performance testing to check response times

---

## The V-Model (Verification & Validation Model)

```
Requirements Analysis  ←──────────────────→  Acceptance Testing
        ↓                                              ↑
System Design          ←────────────────→  System Testing
        ↓                                      ↑
Architecture Design    ←──────────→  Integration Testing
        ↓                              ↑
Module Design          ←──→  Unit Testing
        ↓              ↑
       Coding ─────────────
```

Each development phase has a corresponding testing phase.

---

## Real-World Example

**Scenario:** Building an online banking fund transfer feature

| Activity | V or V? | Example |
|----------|---------|---------|
| Reviewing SRS for fund transfer requirements | ✅ Verification | Is "max transfer ₹1 lakh/day" documented? |
| Reviewing transfer screen design mock | ✅ Verification | Does UI match UX spec? |
| Code review of transfer module | ✅ Verification | Is input validation code correct? |
| Executing test case: transfer ₹500 | ✅ Validation | Does money actually transfer? |
| UAT by bank operations team | ✅ Validation | Does business flow work end-to-end? |

---

## 📌 Key Takeaways

- Verification = **Static** (no code execution) | Validation = **Dynamic** (code executed)
- Verification = **process** quality | Validation = **product** quality
- Both are essential — a system can pass verification but fail validation
- V-Model maps each development phase to a corresponding test phase

---

*Next → [Error vs Defect vs Failure](./05_error_defect_failure_fault.md)*
