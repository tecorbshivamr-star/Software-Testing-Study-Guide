# Regression Testing

## What Is Regression Testing?

**Regression Testing** is the process of re-testing a software application after **changes (bug fixes, new features, or enhancements)** to ensure that previously working functionality still works correctly.

> *"Regression testing ensures we haven't broken anything that was already working."*

---

## Why Is It Needed?

Every code change, no matter how small, carries the risk of introducing new bugs into previously working features.

### Real-World Example
A developer fixes a bug in the **payment module**. Unknowingly, the change breaks the **order history page** — a completely unrelated feature. Regression testing would catch this.

---

## When to Run Regression Tests

| Trigger | Example |
|---------|---------|
| Bug fix deployed | Fixed login bug → retest entire auth flow |
| New feature added | Added dark mode → retest all UI flows |
| Code refactoring | Optimized DB queries → retest all data flows |
| Configuration change | Changed server settings → retest critical paths |
| Third-party library update | Upgraded payment SDK → retest payment flows |

---

## Types of Regression Testing

### 1. Full Regression
Run the **entire test suite** after major changes.
- Most thorough but time-consuming
- Used before major releases

### 2. Partial/Selective Regression
Run **only tests related to the changed area** plus high-risk areas.
- Faster, risk-based approach
- Used in Agile sprints

### 3. Progressive Regression
Add **new test cases** for the new feature plus run existing suite.
- Used when adding new functionality

### 4. Corrective Regression
Run existing tests when **no major code changes** — just verify nothing changed.

---

## Regression Testing Strategy

```
1. Identify changed components
         ↓
2. Assess impact (which features could be affected?)
         ↓
3. Select test cases (all related + critical paths)
         ↓
4. Execute tests
         ↓
5. Report new defects found
```

---

## Regression Test Selection Criteria

Select test cases that cover:
- ✅ All fixed bugs from this release
- ✅ Features that share code with the changed module
- ✅ All critical business flows (smoke tests)
- ✅ Previously failing tests that were later fixed
- ✅ Boundary condition tests

---

## Automating Regression Tests

Regression testing is the **#1 use case for test automation** because:
- It's repetitive (run every sprint/build)
- It's time-consuming when done manually
- It has stable, well-understood test cases

```python
# Pytest regression suite example
@pytest.mark.regression
def test_login_still_works_after_payment_fix():
    page = LoginPage(driver)
    page.login("user@test.com", "Pass@123")
    assert page.is_dashboard_loaded()

@pytest.mark.regression
def test_order_history_not_broken():
    page = OrderHistoryPage(driver)
    orders = page.get_orders()
    assert len(orders) > 0
```

---

## Regression in Agile/CI-CD

```
Sprint 1: 50 test cases (automated)
Sprint 2: +20 new TCs → Total 70 automated
Sprint 3: +15 new TCs → Total 85 automated

Every build → All 85 regression tests run automatically
```

---

## Tools for Regression Automation

| Tool | Language | Best For |
|------|----------|---------|
| Selenium + Pytest | Python | Web UI regression |
| Playwright | JS/Python | Modern web apps |
| Rest Assured | Java | API regression |
| JMeter | N/A | Performance regression |
| Postman/Newman | JS | API regression in CI |

---

## 📌 Key Takeaways

- **Every code change** should trigger regression testing
- **Automate** regression tests — running manually every sprint is unsustainable
- Use **risk-based selection** to balance speed and coverage
- Regression is the **biggest ROI** area for test automation
- Keep regression suite **fast** — slow suites get skipped

---

*Related: [Smoke Testing](./05_smoke_testing.md) | [Sanity Testing](./06_sanity_testing.md)*
