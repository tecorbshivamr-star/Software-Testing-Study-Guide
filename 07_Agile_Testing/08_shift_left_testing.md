# Shift-Left Testing

## What is Shift-Left Testing?
**Shift-Left Testing** is an Agile practice that involves moving testing activities **earlier (left)** in the Software Development Life Cycle (SDLC) instead of treating testing as the final bottleneck step.

```
Traditional (Water-fall / Late testing):
[ Requirements ] ──→ [ Design ] ──→ [ Coding ] ──→ [ Testing ] (Bottleneck!)

Shift-Left Testing (Continuous / Agile):
[ Requirements ] ──→ [ Design ] ──→ [ Coding ] ──→ [ Deploy ]
       ▲                ▲                ▲
   [ Testing ]      [ Testing ]      [ Testing ]
```

---

## How to Implement Shift-Left in QA

### 1. Requirements Review (Phase: Requirements)
- **QA Action:** Read and analyze user stories as soon as they are drafted. Ask questions about edge cases, system limits, and verification options before the sprint board is populated.

### 2. Design Inspections (Phase: Design)
- **QA Action:** Review UI/UX mockups and database schemas. Validate if buttons, flows, and API endpoints are logically consistent.

### 3. Unit Test Validation (Phase: Coding)
- **QA Action:** Collaborate with developers on their unit test plans to ensure standard code coverage parameters (Statement/Branch) are checked before code check-in.

---

## Benefits of Shift-Left
- **Save Money:** Fixing a requirements bug on Day 1 is $10-100\times$ cheaper than fixing it after it hits Production.
- **Fast Releases:** Prevents massive bugs from blocking releases at the last minute.
- **Better Design:** Helps developers structure clean, testable code modules from the start.

---

## 📌 Key Takeaways
- Don't wait for code to be finished before starting quality checks.
- Shift quality conversations to **Day 1** of requirement planning.
- Increases collaboration across devs, BAs, and QA engineers.
