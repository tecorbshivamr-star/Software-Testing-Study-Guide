# ISTQB Foundation Level — Chapter 4: Test Techniques

> Study notes for **ISTQB CTFL (Certified Tester Foundation Level)** exam preparation.

---

## 4.1 Categories of Test Techniques

Test techniques help derive test conditions, test cases, and test data. They are divided into three categories:

1. **Black-box Techniques (Specification-based):** Based on analyzing the test basis (requirements, specs, user stories). Treats software as a black box; no knowledge of internal code.
2. **White-box Techniques (Structure-based):** Based on analyzing the internal structure (code, architecture).
3. **Experience-based Techniques:** Based on the tester's knowledge, experience, and intuition.

---

## 4.2 Black-box Test Techniques

### 1. Equivalence Partitioning (EP)
Divides inputs into partitions where the system is expected to treat all values in that partition the same way.
- **Rule:** Test one value from each valid and invalid partition.

### 2. Boundary Value Analysis (BVA)
Tests the edges of Equivalence Partitions. Defects commonly cluster at boundaries.
- **Rule (2-value approach):** Test the exact boundary and the value just outside it. (e.g., if valid is $1 \le x \le 10$, test $0, 1$ and $10, 11$).
- **Rule (3-value approach):** Test before, at, and after the boundary (e.g., $0, 1, 2$ and $9, 10, 11$).

### 3. Decision Table Testing
Used for testing complex business logic and combinations of conditions.
- Conditions (inputs) and Actions (outputs) are mapped in a table. Each column represents a specific business rule.

### 4. State Transition Testing
Used when the system can be in different states, and transitions from one state to another are triggered by events.
- Derives test cases from a state transition diagram or table (State, Event, Action, Next State).

### 5. Use Case Testing
Tests derived from Use Cases. Focuses on the interactions between actors (users/systems) and the system. Good for end-to-end integration testing.

---

## 4.3 White-box Test Techniques

### 1. Statement Testing and Coverage
Ensures that executable statements in the code are executed at least once.
- **Formula:** $\text{Statement Coverage} = \frac{\text{Number of executed statements}}{\text{Total number of statements}} \times 100\%$

### 2. Decision Testing and Coverage
Ensures that decision outcomes (True and False branches of `if` statements) are executed.
- **Formula:** $\text{Decision Coverage} = \frac{\text{Number of executed decision outcomes}}{\text{Total number of decision outcomes}} \times 100\%$
- *Note:* 100% decision coverage guarantees 100% statement coverage (but not vice-versa).

---

## 4.4 Experience-based Test Techniques

### 1. Error Guessing
Anticipating where errors might occur based on the tester's past experience with similar applications. Often documented in a defect attack list.

### 2. Exploratory Testing
Concurrent test design, test execution, test logging, and learning. Guided by a test charter. Excellent when specifications are poor or time is limited.

### 3. Checklist-based Testing
Testers use a high-level list of items to be noted, checked, or remembered.

---

## Sample Exam Questions — Chapter 4

**Q1.** An input field takes a year of birth between 1900 and 2004. What are the boundary values using the 2-value BVA approach?
- A) 1899, 1900, 2004, 2005 ✅
- B) 1900, 2004
- C) 1899, 1900, 1901, 2003, 2004, 2005
- D) 1899, 2005

**Q2.** Which technique is best for verifying different system behaviors based on previous history/status?
- A) Equivalence Partitioning
- B) Decision Table Testing
- C) State Transition Testing ✅
- D) Use Case Testing

---
*ISTQB Foundation Level — Chapter 4 Complete*  
*Next: [Chapter 5: Test Management](./05_chapter5_test_management.md)*
