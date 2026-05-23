# OWASP Top 10 Overview

## What is OWASP?
The **Open Worldwide Application Security Project (OWASP)** is a non-profit foundation that works to improve the security of software. The **OWASP Top 10** represents the consensus list of the most critical security risks facing web applications today.

---

## The Current OWASP Top 10 Risk Categories

### A01:2021-Broken Access Control
- *Symptom:* Users can access data or perform actions outside their intended permissions (Privilege Escalation).
- *Example:* Accessing `/api/v1/users/admin` as a guest user.

### A02:2021-Cryptographic Failures
- *Symptom:* Data-in-transit or data-at-rest is unencrypted or uses weak hashing algorithms.
- *Example:* Transmitting credit card information over HTTP instead of HTTPS.

### A03:2021-Injection
- *Symptom:* System executes untrusted input data as commands.
- *Example:* SQL Injection (SQLi) or Cross-Site Scripting (XSS).

### A04:2021-Insecure Design
- *Symptom:* Flaws in business logic or application architecture.
- *Example:* Lacking a rate limit on OTP reset forms.

### A05:2021-Security Misconfiguration
- *Symptom:* Default setup parameters or excessively verbose error pages.
- *Example:* Leaving directory browsing enabled or displaying full database stack traces on error pages.

### A06:2021-Vulnerable and Outdated Components
- *Symptom:* Running obsolete or unpatched external packages.
- *Example:* Using a compromised, old version of Log4j.

### A07:2021-Identification and Authentication Failures
- *Symptom:* Permitting weak passwords, credential stuffing, or session hijacking.
- *Example:* Session token doesn't change after login.

### A08:2021-Software and Data Integrity Failures
- *Symptom:* Accepting third-party updates or plugins without digital signatures.

### A09:2021-Security Logging and Monitoring Failures
- *Symptom:* Lack of central audit logging when security events occur.

### A10:2021-Server-Side Request Forgery (SSRF)
- *Symptom:* The web app fetches a remote resource without validating the user-supplied URL.

---

## 📌 Key Takeaways
- Use the **OWASP Top 10** as your baseline security validation checklist.
- Automate vulnerability checks using tools like **OWASP ZAP** or **Burp Suite**.
