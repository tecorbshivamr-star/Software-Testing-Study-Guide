# Real-World Example: Login Module Test Cases

Below is a professional suite of test cases for a standard web application Login Module, demonstrating positive, negative, and edge-case coverage.

---

### TC_LGN_001: Verify successful login with valid credentials (Happy Path)
- **Priority:** Critical (P0)
- **Pre-conditions:** User account `qa_user@test.com` exists and is active.
- **Test Steps:**
  1. Navigate to `https://qa.example.com/login`.
  2. Enter `qa_user@test.com` in the Email field.
  3. Enter `SecurePass123!` in the Password field.
  4. Click the 'Log In' button.
- **Expected Result:** User is successfully authenticated, redirected to the User Dashboard (`/dashboard`), and a "Welcome" banner is displayed.

---

### TC_LGN_002: Verify login fails with incorrect password
- **Priority:** High (P1)
- **Pre-conditions:** User account `qa_user@test.com` exists.
- **Test Steps:**
  1. Navigate to `/login`.
  2. Enter `qa_user@test.com`.
  3. Enter `WrongPassword99` in the Password field.
  4. Click 'Log In'.
- **Expected Result:** Login is blocked. An error message *"Invalid email or password"* is displayed in red below the form.

---

### TC_LGN_003: Verify login fails with unregistered email
- **Priority:** High (P1)
- **Test Steps:**
  1. Navigate to `/login`.
  2. Enter `doesnotexist@test.com`.
  3. Enter `AnyPassword123!`.
  4. Click 'Log In'.
- **Expected Result:** Login is blocked. An error message *"Invalid email or password"* is displayed. *(Note: For security against email-harvesting, the error message should be generic, not "Email not found").*

---

### TC_LGN_004: Verify validation error when Email field is empty
- **Priority:** Medium (P2)
- **Test Steps:**
  1. Navigate to `/login`.
  2. Leave Email field blank.
  3. Enter `SecurePass123!`.
  4. Click 'Log In'.
- **Expected Result:** Form does not submit. Inline validation error *"Email address is required"* appears under the Email field.

---

### TC_LGN_005: Verify account lockout after 5 consecutive failed attempts
- **Priority:** High (P1)
- **Pre-conditions:** User account `lockout_test@test.com` exists.
- **Test Steps:**
  1. Navigate to `/login`.
  2. Enter `lockout_test@test.com` and `WrongPass` 5 times consecutively, clicking 'Log In' each time.
  3. Attempt a 6th login with the *correct* password.
- **Expected Result:** The 6th login attempt is blocked. An error message *"Account temporarily locked due to multiple failed attempts. Try again in 15 minutes"* is displayed.

---

### TC_LGN_006: Verify SQL Injection protection on login fields
- **Priority:** Critical (P0)
- **Test Steps:**
  1. Navigate to `/login`.
  2. Enter `' OR '1'='1` in the Email field.
  3. Enter `' OR '1'='1` in the Password field.
  4. Click 'Log In'.
- **Expected Result:** Login is blocked. User is not authenticated. Standard "Invalid credentials" error is shown. No database stack traces are exposed on the UI.
