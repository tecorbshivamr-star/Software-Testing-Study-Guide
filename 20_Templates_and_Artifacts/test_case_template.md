# Test Case Template

*This is the standard tabular format for writing manual test cases. It ensures that any tester, even a new hire, can pick up the script and execute it perfectly.*

---

## Feature: [Feature Name]
**Test Case ID:** `TC_001`  
**Test Case Name:** `[Short, descriptive name of what is being tested]`  
**Author:** `[Your Name]`  
**Priority:** `[High / Medium / Low]`  

### **Pre-conditions:**
*What must be true before this test can start?*
1. e.g., "User is registered in the database."
2. e.g., "User is logged in and on the homepage."

### **Test Data:**
*Exact data values required for the test.*
- Email: `qa_test@example.com`
- Password: `Password123!`

---

## **Execution Steps**

| Step # | Action Description | Expected Result | Actual Result | Pass/Fail |
| :---: | :--- | :--- | :--- | :---: |
| **1** | Navigate to the login page `url/login`. | Login page renders correctly with Email and Password fields. | *[To be filled during execution]* | `[ ]` |
| **2** | Enter valid email `qa_test@example.com`. | Email is accepted in the input field. | *[To be filled]* | `[ ]` |
| **3** | Enter valid password `Password123!`. | Password is masked (bullet points). | *[To be filled]* | `[ ]` |
| **4** | Click the "Log In" button. | User is authenticated and redirected to the `/dashboard`. A welcome banner appears. | *[To be filled]* | `[ ]` |

---

### **Post-conditions:**
*What cleanup is required after the test finishes?*
- e.g., "User session is destroyed (logged out)."

### **Execution History:**
| Date Executed | Executed By | Status | Linked Defect | Notes |
| :--- | :--- | :--- | :--- | :--- |
| `YYYY-MM-DD` | `[Tester Name]` | Pass | N/A | Executed on Chrome v120 |
| `YYYY-MM-DD` | `[Tester Name]` | Fail | `BUG-402` | Server threw 500 error on step 4 |
