# Smoke Testing

## What Is Smoke Testing?

**Smoke Testing** is a **preliminary test** that checks whether the most critical functions of a software build work correctly. It determines if the build is **stable enough for further testing**.

> *"Smoke testing is like turning on a new piece of hardware — if it doesn't smoke (catch fire), it's safe to proceed."*

Also called: **Build Verification Test (BVT)** or **Confidence Testing**

---

## Purpose

| Goal | Description |
|------|-------------|
| **Verify stability** | Is the build deployable to QA? |
| **Save time** | Reject unstable builds early |
| **Quick confidence** | Takes 30–60 minutes max |
| **Gate keeper** | Prevents wasted effort on broken builds |

---

## What Does Smoke Testing Cover?

Smoke tests cover the **most critical, high-level functionalities** — NOT edge cases or detailed flows.

### E-Commerce App Example
- ✅ Application launches without crash
- ✅ Homepage loads
- ✅ User can login
- ✅ Product search works
- ✅ Can add item to cart
- ✅ Checkout page opens
- ❌ Does NOT test: coupon edge cases, address validation details, etc.

---

## When Is Smoke Testing Done?

```
Developer delivers new build
          ↓
QA runs Smoke Test (30-60 min)
          ↓
      Pass? ──────→ Proceed to full testing
          ↓
         Fail
          ↓
Build rejected → Back to developers
```

---

## Smoke vs Sanity vs Regression

| Aspect | Smoke | Sanity | Regression |
|--------|-------|--------|------------|
| **When** | New build received | After minor fix/patch | After any code change |
| **Scope** | Entire app (high-level) | Specific feature only | Full or partial suite |
| **Depth** | Shallow | Narrow but deeper | Deep |
| **Who** | QA or automation | QA | QA / Automation |
| **Goal** | Is build stable? | Does fix work? | Did fix break anything? |
| **Duration** | 30–60 min | 15–30 min | Hours/days |
| **Documented?** | Sometimes | Rarely | Always |

---

## Sample Smoke Test Cases — Login Module

| TC ID | Test Step | Expected Result |
|-------|-----------|-----------------|
| SMK_001 | Open application URL | Page loads in <3 sec |
| SMK_002 | Login with valid credentials | Dashboard displayed |
| SMK_003 | Navigate to product page | Products listed |
| SMK_004 | Logout | Redirected to login page |

---

## Smoke Testing in CI/CD

In modern DevOps, smoke tests are **automated** and triggered on every new build:

```yaml
# GitHub Actions example
on: [push]
jobs:
  smoke-test:
    runs-on: ubuntu-latest
    steps:
      - name: Run Smoke Tests
        run: pytest tests/ -m smoke --timeout=60
```

---

## 📌 Key Takeaways

- Smoke = **shallow, wide** (covers everything briefly)
- Must run **before** any detailed testing
- Failure = **reject build** immediately
- Should be **automated** in CI/CD pipelines
- Takes **30–60 minutes** maximum

---

*Related: [Sanity Testing](./06_sanity_testing.md) | [Regression Testing](./07_regression_testing.md)*
