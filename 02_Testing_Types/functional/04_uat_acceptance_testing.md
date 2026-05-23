# User Acceptance Testing (UAT)

## What is UAT?
**User Acceptance Testing (UAT)**, also called **Beta Testing** or **End-User Testing**, is the final phase of the software testing process. It determines whether the software is fit for operational use and meets the business requirements.

> *"Does the system actually solve the customer's problem in their real-world workflow?"*

---

## Types of Acceptance Testing

### 1. Alpha Testing
- **Who:** Performed by internal QA and business teams in the development environment.
- **When:** Before releasing to external users.

### 2. Beta Testing
- **Who:** Performed by actual customers/end-users in their own environments.
- **Goal:** Gather real-world feedback and expose unexpected environment issues.

### 3. Operational Acceptance Testing (OAT)
- **Who:** System administrators/operations.
- **Focus:** Backup/restore, disaster recovery, security checks, and maintenance procedures.

### 4. Contract and Regulation Acceptance Testing
- Checks compliance with legal contracts or governmental safety regulations (e.g., GDPR, HIPAA).

---

## The UAT Workflow

```
Receive Requirements & Specs
         ↓
Develop UAT Test Scenarios (Business cases)
         ↓
Set Up UAT Environment (Production mirror)
         ↓
Business Users / QA Execute Scenarios
         ↓
Log & Resolve Blockers
         ↓
Sign Off (Go / No-Go Decision)
```

---

## 📌 Key Takeaways
- It is the ultimate boundary before the software goes to Production.
- Focuses on **business utility and usability**, not just code correctness.
- The outcome is a formal **"Sign-Off"** from the business sponsors.
