# Load vs. Stress vs. Soak Testing

Performance testing involves configuring different user load patterns (shapes) to verify different structural limits of your infrastructure.

---

## The 3 Key Load Shapes

```
   Load Testing (Normal Expected)     Stress Testing (Break Point)      Soak Testing (Leak Check)
        ┌───┐                              ▲                                 ┌────────────┐
        │   │                              │ \                               │            │
   ─────┘   └─────                  ───────┘  \─────                  ───────┘            └─────
```

---

## Detailed Breakdown

### 1. Load Testing
- **Goal:** Verify system behavior under **normal, expected peak load**.
- **Usage:** Run with 100% of expected peak traffic (e.g., 500 users for 1 hour).
- **Checklist:** Are response times within specifications? Are database CPU cycles stable?

### 2. Stress Testing
- **Goal:** Find the **breaking point** of the application.
- **Usage:** Continually scale user counts until error rate spikes, transactions time out, or server memory crashes.
- **Checklist:** How does the system fail (gracefully with error page or catastrophically)? Does it recover automatically after load ceases?

### 3. Soak (Endurance) Testing
- **Goal:** Identify **memory leaks**, database resource exhaustion, or storage leaks.
- **Usage:** Run normal load patterns for **extended durations** (e.g., 12 to 72 hours).
- **Checklist:** Does RAM usage increase monotonically over time? Are database connections failing to close?

---

## Comparison Table

| Performance Type | Focus | Target Duration | Main Threat Caught |
|---|---|---|---|
| **Load Testing** | Performance SLA verification | 1 hour | Slow page load, low throughput |
| **Stress Testing** | Maximum capacity limit | 10–30 mins | Server crashes, resource exhaustion |
| **Soak Testing** | Long-term stability | 12–48 hours | Memory leaks, connection leaks |

---

## 📌 Key Takeaways
- Perform a **Load Test** to confirm standard operational readiness.
- Perform a **Stress Test** to determine structural weak spots.
- Perform a **Soak Test** before major system overhauls to confirm stable memory release footprints.
