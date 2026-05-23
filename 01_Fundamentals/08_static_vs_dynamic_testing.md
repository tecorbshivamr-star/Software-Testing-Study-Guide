# Static vs Dynamic Testing

## Overview

| | Static Testing | Dynamic Testing |
|--|---------------|-----------------|
| **Code execution** | ❌ Not required | ✅ Required |
| **When** | Early SDLC phases | After code is written |
| **Goal** | Find defects in artifacts | Find failures in running software |
| **Done on** | Docs, design, code | Running system |
| **Types** | Reviews, walkthroughs, static analysis | Functional, performance, security testing |

---

## 🔍 Static Testing

Testing performed **without executing** the software. It involves reviewing documents and code.

### Types of Static Testing

#### 1. Reviews
Manual examination of documents by human reviewers.

| Review Type | Description | Formality |
|-------------|-------------|-----------|
| **Informal Review** | Colleague checks your work casually | Lowest |
| **Walkthrough** | Author guides team through document | Low-Medium |
| **Technical Review** | Peers review technical accuracy | Medium |
| **Inspection** | Formal, structured process with defined roles | Highest |

#### 2. Static Analysis (Tool-based)
Automated tools analyze code without executing it.

| Tool | Language | What It Checks |
|------|----------|----------------|
| SonarQube | Java, Python, JS | Code quality, security, duplications |
| ESLint | JavaScript | Code style, errors |
| Pylint | Python | Code style, errors |
| Checkstyle | Java | Coding standards |
| Bandit | Python | Security vulnerabilities |

### What Static Testing Can Find
- Spelling/grammar errors in requirements
- Missing requirements
- Design flaws
- Code violations (naming, standards)
- Security vulnerabilities in code
- Dead code, unused variables

---

## ▶️ Dynamic Testing

Testing performed by **executing** the software with test inputs and observing outputs.

### Types of Dynamic Testing

| Category | Examples |
|----------|---------|
| **Functional** | Unit, Integration, System, UAT |
| **Non-Functional** | Performance, Security, Usability |
| **Regression** | Re-running tests after changes |
| **Confirmation** | Retesting fixed defects |

### Black Box vs White Box in Dynamic Testing
- **Black box dynamic** — Execute and check output against requirements
- **White box dynamic** — Execute and check code coverage

---

## What Each Can Find

| Defect Type | Static | Dynamic |
|-------------|--------|---------|
| Requirements errors | ✅ | ❌ |
| Design flaws | ✅ | 🔶 |
| Code violations | ✅ | ❌ |
| Runtime errors | ❌ | ✅ |
| Performance issues | ❌ | ✅ |
| Security vulnerabilities | ✅ (partial) | ✅ |
| Business logic errors | 🔶 | ✅ |
| Usability issues | ❌ | ✅ |

---

## Cost Benefit: Start Static, Then Dynamic

```
Requirements → [Static: Review] → Design → [Static: Inspect] → Code → [Static: Analyze]
                                                                          ↓
                                                              [Dynamic: Execute Tests]
```

Static testing finds bugs **before** they become expensive to fix.

---

## 📌 Key Takeaways

- Static = **review** (no execution) | Dynamic = **execute** (run the system)
- Static testing is **cheaper** — find bugs in documents before code is written
- **Both are necessary** — static finds different defects than dynamic
- Inspections are the most effective static technique (finds up to 70% of defects)

---

*Next → [Software Quality Attributes](./09_software_quality_attributes.md)*
