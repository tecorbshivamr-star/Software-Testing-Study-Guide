# Test Estimation Techniques

## Why Test Estimation is Hard
Estimating test effort requires predicting how long it takes to write test cases, prepare data, set up environments, execute tests, log defects, and retest bug fixes under uncertainty.

---

## Top 4 Test Estimation Techniques

### 1. Work Breakdown Structure (WBS)
Deconstructs the entire testing lifecycle into smaller, manageable tasks.
- **Example:**
  - *Sprint Testing* (10 days)
    - Test Case Creation (3 days)
    - Test Environment Config (1 day)
    - Phase 1 Execution (4 days)
    - Retesting & Reporting (2 days)

### 2. Three-Point Estimation (PERT)
Calculates estimation based on three scenarios to account for risks.
- **Formula:**
  $$\text{Estimate} = \frac{O + 4M + P}{6}$$
  - **O:** Optimistic Estimate (best-case scenario)
  - **M:** Most Likely Estimate (normal case)
  - **P:** Pessimistic Estimate (worst-case scenario)

### 3. Wideband Delphi / Planning Poker
A collaborative, consensus-based estimation technique where a panel of experts discusses user stories and votes anonymously until estimations align.

### 4. Functional Point Analysis (FPA)
Estimates effort based on the size of the application features (Inputs, Outputs, Files, Queries, and Interfaces).

---

## 📌 Key Takeaways
- Never guess an estimation; use **Three-Point Estimation** for statistical accuracy.
- Always add a **Buffer (10-20%)** for unexpected blockers, environment down-time, or complex bugs.
- Revisit estimations as team velocity changes.
