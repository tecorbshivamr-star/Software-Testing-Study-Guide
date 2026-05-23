# Severity vs. Priority

Understanding the difference between Defect Severity and Defect Priority is a classic interview question and a crucial daily skill for QA engineers.

---

## What is Defect Severity?
**Severity** defines the degree of impact a defect has on the *technical operation* of the system.
- **Answers the question:** "How badly is the system broken?"
- **Determined by:** QA Engineer / Tester.
- **Scale:** Low, Minor, Major, Critical.

## What is Defect Priority?
**Priority** defines the *business urgency* of fixing the defect. It dictates the order in which developers should resolve bugs.
- **Answers the question:** "How quickly does this need to be fixed?"
- **Determined by:** Product Manager / Business Owner (often in collaboration with QA).
- **Scale:** Low, Medium, High, Urgent.

---

## 4 Classic Severity/Priority Scenarios

### 1. High Severity, High Priority
- **Scenario:** The application crashes immediately upon user login, or the main checkout payment gateway throws a `500 Internal Server Error`.
- **Impact:** System is unusable. Business is losing money. Needs to be fixed *right now*.

### 2. High Severity, Low Priority
- **Scenario:** The application crashes if a user tries to upload an obscure file format (like `.tiff`) into a legacy, hidden profile settings page that almost no one uses.
- **Impact:** The crash is technically severe, but because the user impact is so low, it is not an urgent business priority to fix.

### 3. Low Severity, High Priority
- **Scenario:** The company logo on the main landing page is misspelled as "Micrsoft" instead of "Microsoft".
- **Impact:** The software functions perfectly (low technical severity), but the branding impact is disastrous and embarrassing (high business urgency). Needs to be fixed immediately.

### 4. Low Severity, Low Priority
- **Scenario:** A minor typo in the Terms and Conditions document hidden in the footer of the website.
- **Impact:** Doesn't break the software, doesn't hurt the brand significantly. Will be fixed when developers have spare time.

---

## 📌 Key Takeaways
- **Severity** = Technical Impact.
- **Priority** = Business Urgency.
- A QA tester sets the Severity when logging the bug, but the Product Owner ultimately confirms the Priority during Triage.
