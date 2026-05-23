# Reliability Testing

## What is Reliability Testing?
**Reliability Testing** is a non-functional testing type that verifies whether the software can perform its specified functions without failure under defined conditions for a specified period of time.

> *"Can we trust the software to run continuously without crashing?"*

---

## Key Metrics for Reliability

1. **MTTF (Mean Time To Failure):** The average time a system operates correctly before a failure occurs. (Higher is better).
2. **MTTR (Mean Time To Repair/Recover):** The average time it takes to fix a failure and restore the system to working order. (Lower is better).
3. **MTBF (Mean Time Between Failures):** $\text{MTBF} = \text{MTTF} + \text{MTTR}$. Represents the total operational cycle.

---

## 3 Core Types of Reliability Testing

### 1. Feature Testing
Verifying all features execute correctly. This overlaps heavily with functional testing, but specifically tracks if a feature fails intermittently over many executions.

### 2. Load / Endurance (Soak) Testing
Running the application under a normal or high load for an *extended duration* (e.g., 48 hours) to detect memory leaks, database connection drops, and long-term degradation.

### 3. Regression Testing
Repeatedly running tests to ensure that bug fixes or new features haven't introduced new instability into the system over time.

---

## Reliability vs. Availability
- **Reliability:** Probability that the system will not fail during a specific time period. (e.g., A pacemaker must be 100% reliable).
- **Availability:** The percentage of time the system is operational and accessible to users. (e.g., "Five Nines" availability means $99.999\%$ uptime, allowing for ~5 minutes of downtime per year). A system can be highly available but unreliable if it crashes often but reboots in milliseconds.

---

## 📌 Key Takeaways
- Essential for critical systems (aviation, medical devices, banking).
- Often requires simulating long-term usage using automation tools.
