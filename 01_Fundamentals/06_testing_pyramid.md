# The Testing Pyramid

## What Is the Testing Pyramid?

The **Testing Pyramid** is a framework that helps teams decide how many tests to write at each level. It was introduced by **Mike Cohn** and shows the ideal distribution of test types for a healthy test suite.

```
          /\
         /  \
        / E2E\          ← Few (Slow, Expensive)
       /──────\
      /        \
     / Integration\     ← Some (Medium speed)
    /──────────────\
   /                \
  /    Unit Tests    \  ← Many (Fast, Cheap)
 /____________________\
```

---

## The Three Layers

### 🔻 Layer 1: Unit Tests (Foundation — Most Tests)
- Test **individual functions/methods** in isolation
- Written by **developers**
- **Fast** — run in milliseconds
- **Cheap** — easy to write and maintain
- **High ROI** — catch bugs at the source

**Example:**
```python
def calculate_discount(price, percent):
    return price * (percent / 100)

def test_calculate_discount():
    assert calculate_discount(1000, 10) == 100
    assert calculate_discount(500, 0) == 0
```

---

### 🔶 Layer 2: Integration Tests (Middle — Some Tests)
- Test **interactions between components** (API + DB, Service + Service)
- Verify that modules work **together correctly**
- **Slower** than unit tests but faster than E2E
- **Medium cost** to write and maintain

**Example:**
- Testing that the `/login` API correctly queries the database and returns JWT token
- Testing that the payment service correctly calls the bank API

---

### 🔺 Layer 3: End-to-End Tests (Top — Few Tests)
- Test **complete user journeys** through the real UI
- Simulate real user behavior (Selenium, Playwright, Cypress)
- **Slowest** — take minutes to hours
- **Most expensive** — brittle, hard to maintain
- Should cover only **critical business flows**

**Example:**
- User opens browser → Goes to /login → Enters credentials → Clicks login → Lands on dashboard → Adds item to cart → Checks out → Sees order confirmation

---

## The Ice Cream Anti-Pattern 🍦

The **Ice Cream Cone** is the anti-pattern of the pyramid — too many E2E tests, few unit tests. This leads to:

```
      /\
     /E2E\           ← Too many! Slow, flaky, expensive
    /──────\
   / Manual \        ← Even worse — not automated
  /──────────\
 /Integration \      ← Some
/──────────────\
(tiny unit base)     ← Almost none
```

**Problems:**
- Slow CI/CD pipelines (hours instead of minutes)
- Flaky tests that fail randomly
- Hard to pinpoint root cause when E2E fails
- High maintenance cost

---

## Ideal Test Distribution

| Level | Percentage | Example Count |
|-------|-----------|---------------|
| Unit | 70% | 700 tests |
| Integration | 20% | 200 tests |
| E2E | 10% | 100 tests |

---

## Cost vs Confidence Matrix

| | Unit | Integration | E2E |
|---|------|------------|-----|
| **Speed** | ⚡ Milliseconds | 🕐 Seconds | 🕐 Minutes |
| **Cost** | 💰 Low | 💰💰 Medium | 💰💰💰 High |
| **Maintenance** | ✅ Easy | 🔶 Medium | ❌ Hard |
| **Confidence** | 🔶 Module level | ✅ System level | ✅✅ Business flow |
| **Failure Isolation** | ✅ Precise | 🔶 Medium | ❌ Hard to trace |

---

## 📌 Key Takeaways

- **Unit > Integration > E2E** in quantity
- Unit tests = developer's responsibility; E2E = QA's specialty
- Avoid the **Ice Cream Anti-Pattern**
- E2E tests should cover **critical happy paths only**
- A fast test suite = faster CI/CD = faster releases

---

*Next → [Black Box vs White Box vs Grey Box](./07_white_box_vs_black_box_vs_grey_box.md)*
