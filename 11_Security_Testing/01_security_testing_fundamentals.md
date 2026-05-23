# Security Testing Fundamentals

## What is Security Testing?
**Security Testing** is a non-functional testing type designed to identify vulnerabilities, threats, and risks in the software application to prevent malicious attacks from hackers.

---

## The CIA Triad

The core foundation of security engineering is the **CIA Triad**:

```
                  🔒 [ Confidentiality ] (Privacy)
                                 │
                   ┌─────────────┴─────────────┐
                   ▼                           ▼
            📝 [ Integrity ]           ⚡ [ Availability ]
         (Anti-Tampering)                (Uptime / DDoS)
```

- **Confidentiality:** Ensures sensitive data is accessible *only* to authorized users (e.g., encryption, passwords).
- **Integrity:** Ensures data is not maliciously altered or modified during transit or storage (e.g., hash keys, checksums).
- **Availability:** Ensures systems, APIs, and databases remain accessible to legitimate users at all times (e.g., mitigation of DDoS attacks).

---

## 4 Security Testing Methodologies

1. **Vulnerability Scanning:** Automated scanning of system files to identify known signatures of software vulnerability.
2. **Security Scanning:** Identifying network weaknesses, incorrect system configurations, and open firewall ports.
3. **Penetration Testing (Pen Testing):** Simulating a malicious cyberattack on the system to discover structural entry points.
4. **Ethical Hacking:** Broad system-wide investigation authorized by the organization to patch all security holes.

---

## 📌 Key Takeaways
- The **CIA Triad** is the core compass of security testing.
- Implement **Static Application Security Testing (SAST)** directly inside your coding pipelines.
- Security should be a built-in architecture choice, not an afterthought.
