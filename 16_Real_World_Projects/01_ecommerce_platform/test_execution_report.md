# E-Commerce Project: Test Execution Report

## 1. Executive Summary
The System Testing phase for Sprint 12 (E-Commerce Checkout Revamp) has concluded. The build is stable. The core checkout and payment gateway integrations are functioning correctly. However, a minor calculation bug with promo codes was discovered and deferred to the next sprint.

**Status: APPROVED FOR DEPLOYMENT (with known issues)**

---

## 2. Execution Metrics

| Module | Planned | Executed | Passed | Failed | Blocked | Pass Rate |
|---|---|---|---|---|---|---|
| **Authentication** | 15 | 15 | 15 | 0 | 0 | 100% |
| **Product Catalog** | 20 | 20 | 19 | 1 | 0 | 95% |
| **Shopping Cart** | 10 | 10 | 8 | 2 | 0 | 80% |
| **Checkout & Payment**| 25 | 25 | 25 | 0 | 0 | 100% |
| **Total** | **70** | **70** | **67** | **3** | **0** | **95.7%** |

---

## 3. Defect Summary

Total Defects Logged: **4**
- Critical (S1): 0
- Major (S2): 1
- Minor (S3): 3

### Top Open Defects
1. **[BUG-101]** Cart subtotal is calculated incorrectly when promo code is applied (Major). *Deferred to Sprint 13.*
2. **[BUG-102]** "Add to Cart" button overlaps with product image on mobile view (Minor). *Fix in progress by UI team.*

---

## 4. Test Environments Used
- **QA Environment:** `https://qa.ecom-demo.com` (Used for functional testing)
- **Staging Environment:** `https://staging.ecom-demo.com` (Used for UAT and final regression)
- **Browsers tested:** Chrome, Firefox, Safari (macOS), Edge.

---

## 5. Sign-Off
- **QA Lead:** Approved (John Doe)
- **Product Manager:** Approved (Jane Smith)
