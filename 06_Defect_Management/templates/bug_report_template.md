# Bug Report Template

**Use this template when raising defects in Jira, TestRail, Azure DevOps, or any test management tool.**

---

## Bug Report

| Field | Value |
|-------|-------|
| **Bug ID** | BUG_[MODULE]_[NUMBER] |
| **Title** | [One-line clear description of the bug] |
| **Reported By** | |
| **Date Reported** | |
| **Module / Feature** | |
| **Build / Version** | |
| **Environment** | QA / Staging / UAT / Production |
| **Severity** | 🔴 Critical / 🟠 High / 🟡 Medium / 🟢 Low |
| **Priority** | P1 / P2 / P3 / P4 |
| **Status** | New |
| **Assigned To** | |

---

## Environment Details

| Component | Version |
|-----------|---------|
| **OS** | |
| **Browser / App Version** | |
| **URL** | |
| **Test Data Used** | |

---

## Steps to Reproduce

1. 
2. 
3. 
4. 

---

## Expected Result

_What should have happened_

---

## Actual Result

_What actually happened_

---

## Impact

_How does this affect users / the business?_

---

## Attachments

- [ ] Screenshot
- [ ] Screen recording
- [ ] Console log / Error log
- [ ] Network request (HAR file)

---

## Additional Notes

_Any relevant context, related bugs, workaround discovered, etc._

---

## Example (Filled)

| Field | Value |
|-------|-------|
| **Bug ID** | BUG_LOGIN_047 |
| **Title** | Login fails with 500 error for email containing '+' character |
| **Reported By** | Shivam Rai |
| **Date** | 2026-05-15 |
| **Module** | Login Page |
| **Severity** | 🔴 Critical |
| **Priority** | P1 |

**Steps:**
1. Navigate to `https://qa.app.com/login`
2. Enter email: `user+alias@gmail.com`
3. Enter password: `Test@1234`
4. Click **Login** button

**Expected:** User redirected to `/dashboard`  
**Actual:** `500 Internal Server Error` displayed. Network tab shows unhandled exception.

**Impact:** All users with `+` alias in email (Gmail aliases) cannot login — estimated 8% of user base.

---

*Template v1.0 | QA AI Studio*
