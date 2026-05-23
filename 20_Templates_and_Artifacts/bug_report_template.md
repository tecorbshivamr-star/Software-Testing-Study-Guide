# Bug Report Template

*Copy this structure into Jira, Bugzilla, or your preferred defect tracking tool to ensure developers have all the necessary information to fix the issue quickly.*

---

## [Defect Title]
*Format: [Module/Feature] - Summary of the issue.*
*Example: [Checkout] - Payment gateway returns 500 Server Error when using AMEX card.*

---

### **1. Description**
*Provide a clear, concise explanation of the bug and the context in which it occurs.*

### **2. Environment Details**
- **Environment:** (e.g., QA, Staging, Production)
- **App Version / Build #:** (e.g., Sprint 45 - v2.1.0)
- **OS:** (e.g., Windows 11, iOS 17)
- **Browser/Device:** (e.g., Chrome v124, iPhone 15 Pro)
- **User Account Used:** (e.g., `qa_test_user@gmail.com`)

### **3. Steps to Reproduce**
*Numbered, sequential steps that anyone can follow to replicate the bug.*
1. Navigate to the login page (`https://qa.example.com/login`).
2. Enter valid credentials and click "Submit".
3. Add any product to the cart.
4. Proceed to the checkout page.
5. Select "AMEX" as the payment method.
6. Enter valid dummy card details and click "Pay".

### **4. Expected Result**
*What SHOULD have happened according to the requirements.*
- The payment should process successfully, and the user should be redirected to the "Order Success" confirmation page.

### **5. Actual Result**
*What ACTUALLY happened (the bug).*
- The system spins for 5 seconds and displays a red "500 Internal Server Error" banner. The payment is not processed.

### **6. Attachments**
*(Always attach visual proof and logs!)*
- `[Screenshot.png]`
- `[Screen_recording.mp4]`
- `[Browser_Console_Log.txt]` or `[Server_Error.log]`

---

### **Bug Classification**
- **Severity:** (e.g., Critical / Major / Minor / Trivial)
- **Priority:** (e.g., High / Medium / Low) *(Note: Usually set by PO during triage)*
