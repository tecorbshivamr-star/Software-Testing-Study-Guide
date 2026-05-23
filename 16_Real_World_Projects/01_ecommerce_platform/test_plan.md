# E-Commerce Platform — Test Plan

| Field | Value |
|-------|-------|
| **Project** | E-Commerce Platform |
| **Version** | 1.0 |
| **Date** | 2026-05-15 |
| **Prepared By** | Shivam Rai |
| **Status** | Approved |

---

## 1. Introduction

This test plan covers QA for an **E-Commerce web application** built on React (frontend) + Node.js (backend) + PostgreSQL. Key modules: User Registration, Login, Product Catalog, Shopping Cart, Checkout, Payment, Order History, Admin Panel.

---

## 2. Test Scope

### In Scope
- User registration and login (email, Google OAuth, OTP)
- Product catalog (search, filter, sort, pagination)
- Shopping cart (add, remove, update quantity)
- Checkout flow (address, shipping, payment)
- Payment gateway (Razorpay integration)
- Order management (order history, tracking)
- Admin panel (product management, order management)
- Cross-browser testing (Chrome, Firefox, Safari, Edge)
- Mobile responsiveness

### Out of Scope
- Third-party payment gateway internals
- Infrastructure/server configuration
- iOS/Android native apps (separate plan)

---

## 3. Test Strategy

| Test Type | Modules | Priority |
|-----------|---------|----------|
| Smoke Testing | Login, Home, Cart | 🔴 Critical |
| Functional Testing | All modules | 🔴 Critical |
| Regression Testing | All modules after each sprint | 🟠 High |
| Security Testing | Login, Payment, Admin | 🔴 Critical |
| Performance Testing | Product search, Checkout | 🟠 High |
| Compatibility Testing | 4 browsers × 2 OS | 🟠 High |
| UAT | All user-facing modules | 🟠 High |

---

## 4. Test Environment

| Component | Details |
|-----------|---------|
| **URL** | https://qa.ecommerce-demo.com |
| **OS** | Windows 11, macOS 14 |
| **Browsers** | Chrome 124, Firefox 125, Safari 17, Edge 124 |
| **Backend** | Node.js v20, Express |
| **Database** | PostgreSQL 15 |
| **Payment** | Razorpay Test Mode |
| **Build** | Sprint 5 — Build #23 |

---

## 5. Entry & Exit Criteria

### Entry Criteria
- [ ] Build #23 deployed to QA
- [ ] Smoke test passes
- [ ] Test data seeded (users, products, orders)
- [ ] Payment gateway in test mode

### Exit Criteria
- [ ] 100% test execution
- [ ] Pass rate ≥ 95% Critical/High
- [ ] Zero Critical/Blocker open defects
- [ ] Performance: pages load < 3 sec

---

## 6. Risk Analysis

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Payment gateway sandbox instability | Medium | Critical | Use backup test cards |
| Database performance degradation | Low | High | Monitor query times |
| Browser-specific CSS breaks | Medium | Medium | BrowserStack grid |
| Delivery deadline pressure | High | High | Risk-based testing priority |

---

## 7. Test Schedule

| Phase | Dates | Owner |
|-------|-------|-------|
| Test Preparation | May 15–16 | Shivam Rai |
| Smoke Testing | May 17 | Shivam Rai |
| Functional Testing | May 18–21 | Shivam Rai |
| Security Testing | May 22 | Security QA |
| Performance Testing | May 22 | Shivam Rai |
| Regression | May 23 | Automation |
| UAT | May 24–25 | Business Team |
| Test Closure | May 26 | Shivam Rai |

---

*Shivam Rai | QA AI Studio*
