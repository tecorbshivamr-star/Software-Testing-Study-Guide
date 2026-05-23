# System Testing

## What is System Testing?
**System Testing** is the first level where the **complete, integrated application** is tested as a whole. It evaluates the system's compliance with its specified requirements.

> *"Evaluate the entire engine, not just the pistons or spark plugs."*

---

## Key Characteristics
- **Done By:** Independent QA team.
- **Approach:** Black-box testing (no knowledge of internal code).
- **Environment:** Staging / QA environment designed to replicate production closely.
- **Focus:** Functional requirements, end-to-end user journeys, and non-functional compliance.

---

## What is Verified in System Testing?
1. **End-to-End Workflows:** Testing complete business processes (e.g., Search Item → Add to Cart → Pay → Get Invoice).
2. **System Resources:** Interactions with external peripherals, file systems, and hardware.
3. **Data Integrity:** Verification that state is correctly updated across databases and third-party systems.
4. **Performance & Reliability:** Response times, error handling, recovery, and security constraints.

---

## System Testing vs Unit Testing

| Feature | Unit Testing | System Testing |
|---|---|---|
| **Scope** | Smallest testable unit | Entire application |
| **Method** | White-box | Black-box |
| **Executed by** | Developers | QA Engineers |
| **Mocks used** | Yes (heavy use of fakes/mocks) | No (uses real DB/APIs) |

---

## 📌 Key Takeaways
- The first time the system is tested from the actual user's perspective.
- Verifies that business requirements are completely fulfilled.
- Prepares the application for the final checkpoint: User Acceptance Testing (UAT).
