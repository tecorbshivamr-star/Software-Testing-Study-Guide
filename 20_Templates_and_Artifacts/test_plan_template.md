# Test Plan Template

**Copy this template for every new project or release.**

---

# Test Plan: [Feature / Project Name]

| Field | Value |
|-------|-------|
| **Document Version** | 1.0 |
| **Date** | |
| **Prepared By** | |
| **Status** | Draft / In Review / Approved |
| **Reviewed By** | |
| **Project / Release** | |

---

## 1. Introduction & Background

_Brief description of the feature/project being tested and the business context._

---

## 2. Test Scope

### 2.1 In Scope
_What WILL be tested:_
- 
- 

### 2.2 Out of Scope
_What will NOT be tested (and why):_
- 
- 

---

## 3. Test Objectives

1. 
2. 
3. 

---

## 4. Test Strategy

| Test Type | Coverage | Priority | Automated? |
|-----------|----------|----------|------------|
| Smoke Testing | | 🔴 Critical | ✅ |
| Functional Testing | | 🔴 Critical | 🔶 Partial |
| Regression Testing | | 🟠 High | ✅ |
| Sanity Testing | | 🟠 High | ❌ |
| Security Testing | | 🔴 Critical | 🔶 Partial |
| Performance Testing | | 🟡 Medium | ✅ |
| UAT | | 🟠 High | ❌ |
| Accessibility | | 🟡 Medium | 🔶 Partial |

---

## 5. Test Environment

| Component | Details |
|-----------|---------|
| **URL** | |
| **OS** | |
| **Browsers** | |
| **Mobile Devices** | |
| **Database** | |
| **Build / Version** | |
| **Auth Service** | |

---

## 6. Entry Criteria

- [ ] Build deployed to QA environment
- [ ] Test environment stable and accessible
- [ ] Test data seeded in QA database
- [ ] Test cases reviewed and approved
- [ ] All Critical bugs from previous sprint resolved

---

## 7. Exit Criteria

- [ ] 100% test case execution
- [ ] Pass rate ≥ ___% for Critical/High priority
- [ ] Zero open Critical/Blocker defects
- [ ] Regression suite passing
- [ ] Test report signed off

---

## 8. Test Schedule

| Phase | Activity | Owner | Start | End |
|-------|----------|-------|-------|-----|
| Phase 1 | Test Case Preparation | | | |
| Phase 2 | Environment Setup | | | |
| Phase 3 | Smoke Testing | | | |
| Phase 4 | Functional Testing | | | |
| Phase 5 | Regression Testing | | | |
| Phase 6 | UAT | | | |
| Phase 7 | Test Closure | | | |

---

## 9. Resource Allocation

| Role | Name | Responsibility |
|------|------|---------------|
| QA Lead | | |
| QA Engineer | | |
| Dev Lead | | |
| Product Owner | | |

---

## 10. Risk Analysis

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Environment instability | Medium | High | Daily health checks |
| | | | |
| | | | |

---

## 11. Defect Management

| Severity | Fix SLA |
|----------|---------|
| 🔴 Critical | Same day |
| 🟠 High | 24 hours |
| 🟡 Medium | 48 hours |
| 🟢 Low | Next sprint |

**Defect Tool:** Jira / Azure DevOps / TestRail

---

## 12. Deliverables

- [ ] Test Plan (this document)
- [ ] Test Cases
- [ ] Test Data Sheet
- [ ] Test Execution Report
- [ ] Defect Report

---

## 13. Assumptions & Dependencies

- 
- 

---

*Template v1.0 | QA AI Studio | Shivam Rai*
