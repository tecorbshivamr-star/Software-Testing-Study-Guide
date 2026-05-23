# Performance Testing Fundamentals

## What is Performance Testing?
**Performance Testing** is a non-functional testing type that determines how a system performs in terms of **responsiveness, speed, scalability, stability, and reliability** under a specific workload.

> *"Ensure the application is not only correct, but fast and stable under stress."*

---

## 4 Key Performance Metrics

### 1. Response Time / Latency
The total time taken for a request to travel from the client to the server, process, and return the response back to the client.
- *Measurement:* Milliseconds (ms) or seconds (s).
- *Target:* Page load $\le 2\text{s}$, API endpoints $\le 500\text{ms}$.

### 2. Throughput
The number of requests the system can handle successfully per unit of time (e.g., per second or minute).
- *Measurement:* Requests Per Second (RPS) or Transactions Per Second (TPS).

### 3. Error Rate
The ratio of failed requests to total requests sent, expressed as a percentage.
- *Target:* $\le 0.01\%$ under normal load, $0\%$ under optimal conditions.

### 4. Resource Utilization
CPU usage, Memory (RAM) consumption, Network bandwidth utilization, and Database I/O throughput during testing.

---

## The APDEX Score (Application Performance Index)
A standard metric used to measure user satisfaction based on response times:

$$\text{APDEX} = \frac{\text{Satisfactory Count} + \left(\frac{\text{Tolerating Count}}{2}\right)}{\text{Total Samples}}$$

- **Satisfied:** $\le T$ (e.g., $1.5\text{s}$).
- **Tolerating:** $> T$ and $\le 4T$.
- **Frustrated:** $> 4T$.

---

## 📌 Key Takeaways
- Performance testing prevents server crashes during high-traffic events (e.g., Black Friday).
- Establish a **performance baseline** under normal user loads before trying to stress the system.
- Always monitor database CPU usage and slow SQL queries during runs.
