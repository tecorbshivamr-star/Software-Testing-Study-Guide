# Test Metrics and KPIs

## Why Measure Testing?
> *"You cannot manage what you do not measure."*

Test metrics provide objective data about software quality, test progress, and testing team efficiency.

---

## Core QA Metrics & Formulas

### 1. Defect Density
Measures the number of defects per size of the software unit (e.g., per module or lines of code).
$$\text{Defect Density} = \frac{\text{Total Defects Found}}{\text{Size of Release (Module / KLOC)}}$$

### 2. Defect Removal Efficiency (DRE)
Measures the percentage of bugs found by the testing team versus those found in production by users.
$$\text{DRE} = \frac{A}{A + B} \times 100$$
- **A:** Defects found during testing.
- **B:** Defects found by users in production.
- *Goal:* $> 90\%$.

### 3. Defect Leakage Rate
Measures how many defects leaked into production.
$$\text{Defect Leakage} = \frac{\text{Production Defects}}{\text{Total Defects (Testing + Production)}} \times 100$$

### 4. Test Case Execution Coverage
$$\text{Execution Coverage} = \frac{\text{Executed Test Cases}}{\text{Total Test Cases}} \times 100$$

---

## 📌 Key Takeaways
- Use **DRE** to evaluate testing quality. A high DRE means your testing gates are effective.
- Keep **Defect Leakage** as close to $0\%$ as possible.
- Avoid using *only* raw bug counts; always contextualize with severity and release size.
