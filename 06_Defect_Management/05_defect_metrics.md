# Defect Metrics & Leakage

Analyzing defect patterns tells you the health of your engineering processes.

---

## Key Defect Formulas

### 1. Defect Leakage Rate
Measures the percentage of bugs missed by QA that escaped directly to production.

$$\text{Leakage Rate} = \frac{\text{Production Bugs}}{\text{QA Bugs} + \text{Production Bugs}} \times 100$$

*Target:* $< 5\%$.

---

### 2. Defect Removal Efficiency (DRE)
Evaluates the efficiency of your quality gates.

$$\text{DRE} = \frac{\text{Bugs Found in QA}}{\text{Bugs Found in QA} + \text{Bugs Found in Prod}} \times 100$$

*Target:* $> 95\%$.

---

### 3. Defect Age
The average duration between a bug being **Created** and being **Closed** (marked as fixed).

$$\text{Average Bug Age} = \frac{\sum (\text{Resolution Date} - \text{Creation Date})}{\text{Total Fixed Bugs}}$$

---

### 4. Defect Rejection Rate
Indicates test case clarity or communication gaps between QA and Dev.

$$\text{Rejection Rate} = \frac{\text{Rejected Bugs}}{\text{Total Logged Bugs}} \times 100$$

*Note:* A high rejection rate ($> 15\%$) indicates QA might be logging invalid bugs, duplicate bugs, or misunderstanding specifications.

---

## 📌 Key Takeaways
- Track **Defect Leakage** weekly to see if QA regression coverage is slipping.
- Calculate **DRE** at the end of each release cycle to gauge process improvement.
