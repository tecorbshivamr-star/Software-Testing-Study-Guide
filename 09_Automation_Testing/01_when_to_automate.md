# When to Automate Testing

Automating testing is expensive upfront—it requires coding skills, framework setup, and maintenance. QA must strategically decide what to automate to ensure a high Return on Investment (ROI).

---

## What to Automate (High ROI)

```
       Prioritize Automating:
       [ Repetitive Regressions ] ──→ [ High-risk business flows ] ──→ [ Smoke / Sanity Tests ]
```

1. **Repetitive Regression Tests:** Run every sprint/build.
2. **Smoke / Build Verification Tests:** Run on every deployment.
3. **Data-Driven Tests:** Repeating the exact same test actions with $100+$ different data rows.
4. **API Validations:** Fast, stable, and highly repeatable.
5. **Load & Performance Tests:** Impossible to simulate manually.

---

## What NOT to Automate (Low ROI / Don't Do It!)
1. **Ad-hoc / Exploratory Testing:** Relies heavily on human intuition and learning.
2. **UX / Visual Polish:** Checking if a button layout is "visually pleasing" to a human.
3. **Short-lived Features / MVPs:** If a feature will be deprecated or completely changed in a week, automation code is wasted effort.
4. **Highly Unstable Features:** Constant UI changes will constantly break automation scripts (high maintenance cost).

---

## Simple ROI Calculation

$$\text{ROI} = \frac{\text{Manual Testing Cost} - \text{Automation Testing Cost}}{\text{Automation Testing Cost}} \times 100$$

- **Manual Testing Cost:** $(\text{Time to test manually}) \times (\text{Number of runs}) \times (\text{Tester hourly rate})$
- **Automation Cost:** $\text{Initial dev time} + (\text{Maintenance time} \times \text{Runs}) \times (\text{Automation Engineer rate})$

---

## 📌 Key Takeaways
- Never automate $100\%$ of testing—it is a myth. Focus on $70-80\%$ regression automation.
- Only automate **stable** features.
- If a script is too complex to maintain, it is better left as a manual test.
