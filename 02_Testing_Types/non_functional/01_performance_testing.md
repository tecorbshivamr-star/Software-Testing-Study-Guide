# Performance Testing

## What Is Performance Testing?

**Performance Testing** is a type of non-functional testing that determines how a system performs in terms of **speed, scalability, stability, and responsiveness** under a given workload.

> *"Performance testing answers: Can the system handle real-world usage without degrading user experience?"*

---

## Why Performance Testing Matters

| Without Performance Testing | With Performance Testing |
|-----------------------------|-------------------------|
| App crashes on launch day | Capacity planned in advance |
| Slow pages → users leave | Response times optimized |
| Revenue lost during peak | Bottlenecks identified & fixed |
| Reputation damaged | Confident release |

### Real-World Failures
- **Amazon (2013):** 1 second delay = $1.6B revenue loss/year
- **Flipkart Big Billion Day:** Site crashed due to unexpected traffic spike
- **Healthcare.gov (2013):** Couldn't handle 250,000 users on launch day

---

## Types of Performance Testing

### 1. 📈 Load Testing
Tests system behavior under **expected normal load**.
- How does the app perform with 1000 concurrent users?
- Response time, throughput, error rate measured

### 2. 💪 Stress Testing
Tests system behavior **beyond normal capacity** until it breaks.
- What happens at 5000, 10000 users?
- Find the breaking point

### 3. 🔥 Spike Testing
Tests system with **sudden, sharp increases** in load.
- Flash sale scenario: 0 → 10,000 users in 10 seconds

### 4. 🏊 Soak/Endurance Testing
Tests system under **sustained load over extended period**.
- Can app handle 500 users continuously for 8 hours?
- Identifies memory leaks, degradation over time

### 5. 📊 Scalability Testing
Tests how well system **scales** as load increases.
- Does adding more servers proportionally increase capacity?

### 6. 🏔️ Volume Testing
Tests with **large amounts of data** in the database.
- How does app perform with 10 million records in DB?

---

## Key Performance Metrics

| Metric | Definition | Target |
|--------|-----------|--------|
| **Response Time** | Time from request to response | < 2 seconds (web) |
| **Throughput** | Requests processed per second | Depends on system |
| **Error Rate** | % of failed requests | < 1% |
| **Concurrent Users** | Simultaneous active users | Per business requirement |
| **CPU Utilization** | Server CPU usage | < 70-80% under load |
| **Memory Usage** | RAM consumption over time | Stable, no leaks |
| **Latency** | Network delay | < 200ms |

---

## Performance Testing Process

```
1. Define Performance Requirements
   (e.g., "Page load < 3s for 1000 users")
         ↓
2. Create Test Environment
   (mirroring production)
         ↓
3. Create Test Scenarios
   (user journeys to simulate)
         ↓
4. Configure & Execute Tests
   (JMeter, k6, Gatling)
         ↓
5. Monitor & Collect Results
   (APM tools: New Relic, Grafana)
         ↓
6. Analyze Results
   (Find bottlenecks)
         ↓
7. Report & Optimize
```

---

## Performance Testing Tools

| Tool | Type | Language | Best For |
|------|------|----------|---------|
| **Apache JMeter** | Load | GUI/XML | Web apps, APIs |
| **k6** | Load | JavaScript | Modern APIs, CI/CD |
| **Gatling** | Load | Scala | High-performance testing |
| **Locust** | Load | Python | Pythonic, scriptable |
| **Artillery** | Load | JavaScript | APIs, microservices |
| **New Relic** | Monitoring | N/A | Production monitoring |
| **Grafana** | Monitoring | N/A | Metrics dashboards |

---

## Sample JMeter Test Plan Structure

```
Thread Group (1000 users, 60 sec ramp-up, 5 min duration)
├── HTTP Request: Login API
├── HTTP Request: Get Products
├── HTTP Request: Add to Cart
├── HTTP Request: Checkout
└── Listeners:
    ├── Summary Report
    ├── Response Time Graph
    └── Active Threads Over Time
```

---

## 📌 Key Takeaways

- Performance testing ≠ just load testing — it's a category of many test types
- Always test in an environment that **mirrors production**
- Define **clear acceptance criteria** before testing (SLAs)
- Performance issues found in production = **very expensive**
- Automate performance tests in **CI/CD** pipelines

---

*Related: [Load Testing](./02_load_testing.md) | [Stress Testing](./03_stress_testing.md) | [JMeter Guide](../../10_Performance_Testing/03_jmeter_complete_guide.md)*
