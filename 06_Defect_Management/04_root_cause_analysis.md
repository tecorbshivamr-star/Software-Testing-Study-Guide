# Root Cause Analysis (RCA)

## What is RCA?
**Root Cause Analysis (RCA)** is a structured problem-solving methodology used to identify **why** a defect occurred, rather than simply fixing the immediate symptom.

> *"Fixing the symptom stops the leak today; finding the root cause stops the flood forever."*

---

## Top 2 Root Cause Analysis Methodologies

### 1. The "5 Whys" Technique
Ask "Why?" progressively (typically five times) until you discover the deep organizational or structural cause of a bug.

- **Symptom:** The production database crashed.
  1. *Why?* The disk space filled up completely.
  2. *Why?* A debug log file grew to 500GB.
  3. *Why?* The logger was accidentally left in `VERBOSE` mode in the production build config.
  4. *Why?* There was no automated code configuration check during deployment.
  5. *Why?* The CI/CD pipeline does not include static environment config validation. (← **Root Cause**)

---

### 2. Ishikawa Fishbone Diagram
A visual tool used to categorize potential causes of a defect into standard buckets:
- **People:** Lack of training, developer misunderstanding.
- **Process:** Missing code reviews, poor testing window.
- **Technology:** Outdated frameworks, network latency.
- **Environment:** Staging mismatches with production.

```
      People          Process
        │               │
  No training ──┐   No reviews ──┐
                │                │
                ├────────────────┼─────── [ Defect: App Crash ]
                │                │
  Slow API ─────┘   QA Env down ─┘
        │               │
    Technology     Environment
```

---

## 📌 Key Takeaways
- RCA ensures the same bug never happens twice.
- Share RCAs in retrospective meetings to improve development processes.
- Leads to long-term quality increases and lower regression rates.
