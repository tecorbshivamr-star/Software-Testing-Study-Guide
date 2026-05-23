# Performance Testing Interview Q&A

> Covers core performance concepts, metrics, JMeter, and load strategies.

---

## 🔵 Section 1: Core Concepts

**Q1. What is the difference between Performance, Load, and Stress Testing?**
- **Performance Testing:** General testing to check speed, response time, and stability under a *particular* workload.
- **Load Testing:** Testing system behavior under the *expected peak* load (e.g., Black Friday traffic).
- **Stress Testing:** Pushing the system *beyond* normal capacity to find its breaking point and observe how it fails/recovers.

**Q2. What is Soak (Endurance) Testing?**
Running a normal load on the system for an extended period (e.g., 24-72 hours) to detect memory leaks, database connection issues, or long-term degradation.

**Q3. What is Spike Testing?**
Testing the system's reaction to sudden, extreme, and brief increases in user traffic (e.g., flash sales, breaking news alerts).

**Q4. What is Latency vs. Throughput?**
- **Latency (Response Time):** The time it takes for a single request to travel to the server and return (measured in ms or seconds). "How fast is it?"
- **Throughput:** The number of requests the server can handle per unit of time (measured in Requests Per Second - RPS). "How much volume can it handle?"

---

## 🟡 Section 2: Metrics & Analysis

**Q5. What are the key performance metrics you monitor?**
1. Response Time (Average, 90th percentile, 95th percentile, 99th percentile).
2. Throughput (RPS / TPS).
3. Error Rate (Percentage of failed requests).
4. CPU / Memory / Disk / Network Utilization on the server.
5. Active Threads (Virtual Users).

**Q6. Why is the 90th or 95th Percentile Response Time more important than the Average?**
Averages hide outliers. If 9 requests take 10ms, and 1 request takes 10,000ms, the average is ~1000ms, which misrepresents the normal user experience. The 95th percentile tells you exactly what 95% of your users are experiencing (ignoring the worst 5% anomalies).

**Q7. What is a Memory Leak?**
A bug where the application fails to release RAM that it no longer needs. Over time (detected via Soak Testing), available memory continuously decreases until the server crashes (OutOfMemoryError).

---

## 🔴 Section 3: Tools (JMeter & k6)

**Q8. What are the core components of a JMeter Test Plan?**
- **Thread Group:** Simulates users and defines load parameters (number of threads, ramp-up time, duration).
- **Samplers:** The actual requests being sent (e.g., HTTP Request, JDBC Request).
- **Logic Controllers:** Determine the order of request execution (e.g., If Controller, Loop Controller).
- **Timers:** Introduce delays (think times) between requests to simulate real user behavior.
- **Assertions:** Validate the response (e.g., Response Assertion to check for status 200).
- **Listeners:** Collect and display results (e.g., View Results Tree, Summary Report).

**Q9. Should you run JMeter load tests in GUI mode?**
No. GUI mode consumes significant memory and CPU, which will skew the test results or cause JMeter to crash. GUI is only for script creation and debugging. Load tests must be executed in CLI (Non-GUI) mode.

**Q10. How do you handle dynamic data (like session IDs) in JMeter?**
Using **Correlation**. You use a Regular Expression Extractor (or JSON Extractor) on the response of the first request (e.g., Login) to capture the dynamic token, save it to a variable, and pass that variable in subsequent requests.

**Q11. How do you feed different test data (like usernames/passwords) to different virtual users in JMeter?**
Using **Parameterization** via the `CSV Data Set Config` element. It reads lines from a CSV file and assigns values to variables for each thread.

---

*Related: [Performance Testing Fundamentals](../10_Performance_Testing/01_perf_testing_fundamentals.md) | [Load vs Stress vs Soak](../10_Performance_Testing/04_load_vs_stress_vs_soak.md)*
