# ISTQB Foundation Level — Chapter 2: Testing Throughout the SDLC

> Study notes for **ISTQB CTFL (Certified Tester Foundation Level)** exam preparation.

---

## 2.1 Software Development Lifecycle Models

Testing must adapt to the software development lifecycle (SDLC) model being used.

### Sequential Development Models
- **Waterfall:** Phases occur sequentially (Requirements $\to$ Design $\to$ Code $\to$ Test $\to$ Deploy). Testing happens at the very end.
- **V-Model:** Integrates testing throughout the SDLC. For every development phase, there is a corresponding testing phase (e.g., Requirements Analysis $\leftrightarrow$ Acceptance Testing, System Design $\leftrightarrow$ System Testing).

### Iterative and Incremental Development Models
- **Iterative:** Groups of features are specified, designed, built, and tested together in a series of cycles (e.g., Agile, Scrum, Kanban).
- **Incremental:** Establishing requirements, designing, building, and testing a system in pieces.

---

## 2.2 Test Levels

Test levels represent groups of test activities that are organized and managed together.

### 1. Component Testing (Unit Testing)
- **Focus:** Modules, programs, objects, classes.
- **Performed By:** Developers.
- **Basis:** Detailed design, code, data model.

### 2. Integration Testing
- **Focus:** Interactions between components or systems.
- **Types:** Component Integration (interactions between units) and System Integration (interactions between different systems/microservices).
- **Performed By:** Developers (Component) or Testers (System).

### 3. System Testing
- **Focus:** The behavior of the whole system/product.
- **Performed By:** Independent testing team.
- **Basis:** System and software requirement specifications, use cases.
- **Environment:** Should resemble production as closely as possible.

### 4. Acceptance Testing
- **Focus:** Validation that the system meets user needs and is ready for deployment.
- **Performed By:** Customers, end-users, or business stakeholders.
- **Types:**
  - *User Acceptance Testing (UAT)*
  - *Operational Acceptance Testing (OAT)*
  - *Contractual/Regulatory Acceptance Testing*
  - *Alpha & Beta Testing*

---

## 2.3 Test Types

Test types are a group of test activities aimed at testing specific characteristics of a software system.

1. **Functional Testing:** Evaluating functions the system should perform ("What" the system does). Evaluated via Black-box techniques.
2. **Non-functional Testing:** Evaluating attributes of the system ("How well" the system behaves - e.g., usability, performance, security).
3. **White-box Testing:** Testing based on an analysis of the internal structure of the component or system.
4. **Change-related Testing:**
   - *Confirmation Testing (Re-testing):* Executing tests that previously failed to verify a defect fix.
   - *Regression Testing:* Executing tests to ensure that changes (fixes or enhancements) haven't broken existing functionality.

---

## 2.4 Maintenance Testing

Done on an existing operational system, triggered by modifications, migration, or retirement.
- **Impact Analysis:** Done to evaluate the changes made for a maintenance release and identify the intended consequences as well as expected side effects. This helps decide how much regression testing is needed.

---

## Sample Exam Questions — Chapter 2

**Q1.** Which of the following is a characteristic of good testing applicable to any lifecycle model?
- A) Testing starts only after coding is complete.
- B) Testers should only be involved in execution.
- C) For every development activity, there is a corresponding test activity. ✅
- D) Only developers should perform component and integration testing.

**Q2.** What is the main purpose of confirmation testing (re-testing)?
- A) To ensure no new defects were introduced.
- B) To verify that the original defect has been successfully fixed. ✅
- C) To test the integration of new modules.
- D) To test the system's performance under load.

---
*ISTQB Foundation Level — Chapter 2 Complete*  
*Next: [Chapter 3: Static Testing](./03_chapter3_static_testing.md)*
