# Software Quality Attributes (ISO 25010)

## What Is Software Quality?

Software quality is the degree to which a software product satisfies stated and implied needs. The **ISO/IEC 25010** standard defines a **Product Quality Model** with 8 main quality characteristics.

---

## ISO 25010 — 8 Quality Characteristics

### 1. 🎯 Functional Suitability
Does the software provide the **right functions**?

| Sub-characteristic | Meaning |
|-------------------|---------|
| Functional completeness | All functions specified are present |
| Functional correctness | Functions produce correct results |
| Functional appropriateness | Functions facilitate task accomplishment |

**Test types:** Functional testing, UAT

---

### 2. ⚡ Performance Efficiency
How well the software performs **under given conditions**?

| Sub-characteristic | Meaning |
|-------------------|---------|
| Time behavior | Response/processing time |
| Resource utilization | CPU, memory, network usage |
| Capacity | Maximum limits (users, data) |

**Test types:** Load, stress, performance testing

---

### 3. 🔒 Security
Degree to which software **protects data and systems**.

| Sub-characteristic | Meaning |
|-------------------|---------|
| Confidentiality | Data only accessible to authorized users |
| Integrity | Data not modified unauthorized |
| Non-repudiation | Actions can be proved to have occurred |
| Authenticity | Identity of users can be verified |

**Test types:** Security, penetration testing

---

### 4. 🔧 Maintainability
How easily the software can be **modified and maintained**?

| Sub-characteristic | Meaning |
|-------------------|---------|
| Modularity | Changes have minimal impact on others |
| Reusability | Components can be reused |
| Analysability | Easily diagnosable |
| Modifiability | Easy to modify without defects |
| Testability | How easily tests can be established |

---

### 5. 🔄 Reliability
Software performs its functions **under specified conditions for a period of time**.

| Sub-characteristic | Meaning |
|-------------------|---------|
| Maturity | Meets reliability needs under normal operation |
| Availability | Operational and accessible when needed (uptime %) |
| Fault tolerance | Operates despite hardware/software faults |
| Recoverability | Recovers data and state after interruption |

**Test types:** Reliability, soak testing

---

### 6. 🤝 Compatibility
Operates with other **products, systems, environments**.

| Sub-characteristic | Meaning |
|-------------------|---------|
| Co-existence | Shares environment without negative impact |
| Interoperability | Exchanges information with other systems |

**Test types:** Compatibility, integration testing

---

### 7. 😊 Usability
How effectively users can **use the product**.

| Sub-characteristic | Meaning |
|-------------------|---------|
| Appropriateness recognizability | Users can recognize if it fits their needs |
| Learnability | How easy to learn |
| Operability | Easy to operate and control |
| User error protection | Protects users from errors |
| Accessibility | Usable by people with disabilities (WCAG) |

**Test types:** Usability, accessibility testing

---

### 8. 📦 Portability
How effectively the software can be **transferred to another environment**.

| Sub-characteristic | Meaning |
|-------------------|---------|
| Adaptability | Can be adapted to different environments |
| Installability | Can be installed/uninstalled effectively |
| Replaceability | Can replace other software for same purpose |

---

## Summary Table

| Quality Attribute | Key Question | Test Type |
|-------------------|-------------|-----------|
| Functional Suitability | Does it do the right things? | Functional |
| Performance Efficiency | Is it fast enough? | Performance |
| Security | Is it safe? | Security |
| Maintainability | Is it easy to change? | Code review |
| Reliability | Does it work consistently? | Reliability/Soak |
| Compatibility | Does it work with others? | Compatibility |
| Usability | Is it easy to use? | Usability |
| Portability | Can it run elsewhere? | Portability |

---

## 📌 Key Takeaways

- Quality is **multi-dimensional** — not just "does it work?"
- Each quality attribute requires a **different testing approach**
- ISO 25010 is the modern standard replacing ISO 9126
- In practice, prioritize attributes based on the **product domain** (e.g., security for banking, performance for gaming)

---

*You've completed Fundamentals! Next → [Testing Types](../02_Testing_Types/)*
