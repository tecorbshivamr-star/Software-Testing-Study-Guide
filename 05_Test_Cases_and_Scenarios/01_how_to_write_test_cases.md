# How to Write Effective Test Cases

## What Is a Test Case?

A **test case** is a set of conditions, steps, and expected results used to verify that a specific aspect of a software application works correctly.

> *"A well-written test case is a contract between the tester and the feature — it defines exactly what 'working correctly' means."*

---

## Test Case vs Test Scenario

| | Test Scenario | Test Case |
|--|-------------|-----------|
| **Definition** | High-level user journey | Detailed step-by-step verification |
| **Granularity** | Broad | Specific |
| **Example** | "Test login functionality" | "TC_001: Verify login with valid email and password redirects to dashboard" |
| **Count** | Few | Many (multiple TCs per scenario) |

---

## Anatomy of a Perfect Test Case

| Field | Description | Example |
|-------|-------------|---------|
| **TC ID** | Unique identifier | `TC_LOGIN_001` |
| **Title** | Clear, concise description | "Valid login with correct credentials" |
| **Module** | Feature/page being tested | Login Page |
| **Priority** | Critical/High/Medium/Low | High |
| **Severity** | Critical/Major/Minor/Trivial | Critical |
| **Test Type** | Functional/Regression/Smoke | Functional |
| **Preconditions** | What must be true before testing | User account exists, app is running |
| **Test Data** | Specific input values | Email: user@test.com, Pass: Test@123 |
| **Steps** | Numbered actions to perform | 1. Open URL 2. Enter email 3. Click login |
| **Expected Result** | What should happen | User redirected to /dashboard |
| **Actual Result** | What actually happened (filled during execution) | _(blank before test)_ |
| **Status** | Pass/Fail/Blocked/Not Executed | ⬜ Not Executed |
| **Remarks** | Notes, defect IDs if failed | — |

---

## 10 Rules for Writing Great Test Cases

### 1. ✅ Write from the User's Perspective
Test cases should reflect how a **real user** interacts with the system.

❌ Bad: "Enter data in field"  
✅ Good: "Enter valid email address 'testuser@example.com' in the Email field"

---

### 2. ✅ Make Test Cases Atomic
Each test case should test **one thing only**. Don't bundle multiple verifications.

❌ Bad: "Test login and verify profile page and check logout"  
✅ Good: Separate TCs for login, profile page, and logout

---

### 3. ✅ Use Specific Test Data
Never use vague test data. Be explicit.

❌ Bad: "Enter a valid email"  
✅ Good: "Enter `testuser@qa.com`"

---

### 4. ✅ Write Clear Expected Results
Expected result must be precise and measurable.

❌ Bad: "User should be logged in"  
✅ Good: "User is redirected to `/dashboard`. Welcome message 'Hello, Test User' is visible. Session cookie is set."

---

### 5. ✅ State Preconditions Clearly
Don't assume — state everything needed before the test.

❌ Bad: (no preconditions listed)  
✅ Good: "User account `testuser@qa.com` must exist and be active in the QA database"

---

### 6. ✅ Cover Positive AND Negative Scenarios
Always test what should work AND what should fail.

- Positive: Valid login → success
- Negative: Wrong password → error message
- Edge case: Password with 256 chars → validation error

---

### 7. ✅ Write Reusable Test Cases
Avoid tying test cases to a specific environment or dataset.

---

### 8. ✅ Use Action Verbs in Steps
Start each step with a verb: Click, Enter, Navigate, Select, Verify, Scroll.

---

### 9. ✅ Keep Steps Short and Numbered
Each step = one action. Never combine two actions in one step.

❌ Bad: "1. Open the browser and navigate to the site and enter credentials"  
✅ Good: "1. Navigate to https://qa.app.com/login  
2. Enter email: testuser@qa.com  
3. Enter password: Test@1234  
4. Click **Login** button"

---

### 10. ✅ Review Before Execution
Have test cases reviewed by a peer or the developer to catch misunderstandings.

---

## Test Case Coverage Checklist

For any feature, ensure you have test cases for:
- [ ] Happy path (positive flow)
- [ ] Invalid/wrong inputs (negative)
- [ ] Empty/null inputs
- [ ] Boundary values (min, max, min-1, max+1)
- [ ] Special characters
- [ ] Duplicate data
- [ ] Long inputs
- [ ] Concurrent access (if applicable)
- [ ] Permission/role variations
- [ ] Error messages and validations

---

*See real examples → [Login Test Cases](./examples/login_module_test_cases.md)*  
*Template → [Test Case Template](./templates/test_case_template.md)*
