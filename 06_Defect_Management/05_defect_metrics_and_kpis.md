# Defect Metrics and KPIs

Tracking defect metrics allows QA Managers and Engineering Leaders to objectively measure the quality of the software and the efficiency of the testing process.

---

## Top 5 Defect Metrics

### 1. Defect Density
Measures the number of defects found per unit of code (usually per 1000 lines of code, or KLOC).
- **Formula:** $\frac{\text{Total Defect Count}}{\text{Size of the Release (KLOC or Function Points)}}$
- **Purpose:** Identifies which modules are the most buggy and might require a complete code refactor rather than just patch fixes.

### 2. Defect Leakage (Escaped Defects)
The percentage of defects that were *missed* by the QA team and found by end-users in production.
- **Formula:** $\frac{\text{Defects Found in Production}}{\text{Total Defects Found (QA + Production)}} \times 100$
- **Purpose:** The ultimate measure of QA effectiveness. A high leakage rate means the test cases or environments are inadequate. Target is usually $< 5\%$.

### 3. Defect Rejection Ratio
The percentage of defects logged by QA that were rejected by developers (marked as "Not a Bug", "Working as Designed", or "Cannot Reproduce").
- **Formula:** $\frac{\text{Total Rejected Defects}}{\text{Total Defects Logged}} \times 100$
- **Purpose:** Measures the QA team's understanding of the requirements. A high rejection ratio means testers need better training on the product specifications.

### 4. Defect Removal Efficiency (DRE)
Measures how effectively the development team is removing defects before they reach production.
- **Formula:** $\frac{\text{Defects Fixed Prior to Release}}{\text{Total Defects Found Prior to Release} + \text{Defects Found in Production}}$
- **Purpose:** Assesses the overall quality of the development and testing lifecycle. Target is usually $> 95\%$.

### 5. Defect Age (Time to Resolve)
The average time it takes for a defect to move from "New" to "Closed".
- **Formula:** $\text{Date Fixed} - \text{Date Logged}$
- **Purpose:** Highlights bottlenecks in the development pipeline. If critical bugs sit open for 14 days, there is a severe resource or prioritization issue.

---

## 📌 Key Takeaways
- Metrics should be used to improve processes, not to punish individual testers or developers.
- **Defect Leakage** is the most critical metric for assessing the ROI (Return on Investment) of a QA department.
