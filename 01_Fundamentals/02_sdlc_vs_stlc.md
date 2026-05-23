# SDLC vs STLC

## Software Development Life Cycle (SDLC)

SDLC is the **overall process of planning, creating, testing, and deploying** software. Testing is one phase within SDLC.

### SDLC Phases

```
1. Requirement Analysis
        ↓
2. System Design
        ↓
3. Implementation (Coding)
        ↓
4. Testing
        ↓
5. Deployment
        ↓
6. Maintenance
```

---

## Software Testing Life Cycle (STLC)

STLC is the **sequence of activities specifically for testing** that ensures software quality objectives are met.

### STLC Phases

```
Phase 1: Requirement Analysis
   → Review requirements, identify testable items, create RTM

Phase 2: Test Planning
   → Effort estimation, resource allocation, risk assessment, test plan

Phase 3: Test Case Design
   → Write test cases, prepare test data, review test cases

Phase 4: Test Environment Setup
   → Configure hardware/software, deploy build, smoke test env

Phase 5: Test Execution
   → Execute test cases, log defects, retest fixed bugs

Phase 6: Test Closure
   → Test summary report, lessons learned, archive artifacts
```

---

## SDLC vs STLC Comparison

| Aspect | SDLC | STLC |
|--------|------|------|
| **Scope** | Entire software development | Only testing activities |
| **Owner** | Development team + all stakeholders | QA team |
| **Goal** | Build the product | Verify the product quality |
| **Output** | Working software | Quality-assured software |
| **Phases** | 6 phases (Req → Maintenance) | 6 phases (Req Analysis → Closure) |
| **Starts when** | Project kickoff | Requirements are available |
| **Ends when** | Product is in production | Test closure report is signed off |

---

## STLC Entry & Exit Criteria

### Phase 1: Requirement Analysis
| | Criteria |
|---|---|
| **Entry** | Requirements document available |
| **Exit** | RTM created, testable requirements identified |

### Phase 2: Test Planning
| | Criteria |
|---|---|
| **Entry** | Requirements signed off |
| **Exit** | Test plan document approved |

### Phase 3: Test Case Design
| | Criteria |
|---|---|
| **Entry** | Test plan approved |
| **Exit** | Test cases reviewed and approved |

### Phase 4: Test Environment Setup
| | Criteria |
|---|---|
| **Entry** | Test plan ready, environment specs defined |
| **Exit** | Environment ready, smoke test passed |

### Phase 5: Test Execution
| | Criteria |
|---|---|
| **Entry** | Test cases ready, environment stable, build deployed |
| **Exit** | All high-priority test cases executed, critical bugs fixed |

### Phase 6: Test Closure
| | Criteria |
|---|---|
| **Entry** | Test execution complete |
| **Exit** | Test closure report signed off |

---

## SDLC Models and Their Impact on Testing

| SDLC Model | Testing Approach |
|------------|-----------------|
| **Waterfall** | Testing after development complete — risky, late defect detection |
| **V-Model** | Testing planned at each dev phase — better traceability |
| **Agile/Scrum** | Continuous testing in every sprint — fast feedback |
| **DevOps** | Automated testing in CI/CD pipeline — shift-left |
| **Spiral** | Risk-driven testing at each iteration |

---

## 📌 Key Takeaways

- SDLC is the **parent** process; STLC is a **subset** within it
- STLC starts as soon as **requirements are available** (not after coding!)
- Each STLC phase has defined **Entry and Exit criteria**
- In Agile, STLC is compressed into **2-week sprints**

---

*Next → [Seven Testing Principles](./03_seven_testing_principles.md)*
