# Banking Application: Security Test Cases

Below are critical security and boundary test cases specific to a banking environment.

---

### TC_SEC_01: Verify Session Timeout
- **Priority:** Critical
- **Steps:**
  1. Log in to the banking portal.
  2. Leave the browser idle for exactly 15 minutes.
  3. Attempt to click on "Transfer Funds".
- **Expected:**
  - System intercepts the click.
  - User is immediately logged out.
  - Redirected to login page with message: "Session expired due to inactivity."

### TC_SEC_02: Verify Concurrent Login Handling
- **Priority:** High
- **Steps:**
  1. Log in to the application on Browser A (Chrome).
  2. While keeping Browser A open, open Browser B (Firefox) on a different machine.
  3. Attempt to log in with the exact same credentials.
- **Expected:**
  - Login on Browser B is successful.
  - The active session on Browser A is immediately terminated.
  - If the user clicks anything on Browser A, they receive a "Session invalidated" error.

### TC_SEC_03: Verify SQL Injection on Fund Transfer Note Field
- **Priority:** Critical
- **Steps:**
  1. Log in and initiate a fund transfer.
  2. In the "Optional Transfer Note" field, input: `'; DROP TABLE transactions; --`
  3. Submit the transfer.
- **Expected:**
  - Transfer is processed successfully.
  - The text is sanitized and stored literally as a string.
  - No database errors are thrown, and no tables are dropped.

### TC_SEC_04: Verify Role-Based Access Control (RBAC) Escalation
- **Priority:** Critical
- **Pre-conditions:** Logged in as a standard retail customer.
- **Steps:**
  1. Identify the URL pattern for an admin dashboard (e.g., `https://bank.com/user/dashboard`).
  2. Manually modify the URL in the browser address bar to `https://bank.com/admin/dashboard`.
  3. Press Enter.
- **Expected:**
  - User is blocked.
  - System returns a `403 Forbidden` error.
  - Security event is logged in the backend audit trail.

### TC_SEC_05: Verify Race Condition on Withdrawals
- **Priority:** Critical
- **Pre-conditions:** Account balance is exactly $100.
- **Steps:**
  1. Open the application on two different devices simultaneously.
  2. Attempt to withdraw $100 on both devices at the exact same millisecond (using an automated script like JMeter to synchronize requests).
- **Expected:**
  - Transaction isolation locks the database row.
  - Only *one* withdrawal of $100 succeeds.
  - The second request is rejected with "Insufficient Funds."
  - Final account balance is $0 (not -$100).
