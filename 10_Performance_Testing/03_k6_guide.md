# Grafana k6 Load Testing

## What is k6?
**k6** is a modern, developer-centric, open-source load testing tool developed by Grafana Labs. It is written in Go, but utilizes **JavaScript** to author lightweight, fast performance scripts.

---

## Why Choose k6 over JMeter?
- **Code-First:** Written in pure JS—ideal for developers and automated CI/CD pipelines.
- **Resource Efficient:** Written in Go—runs without JVM overhead, using $10-50\times$ less system RAM than JMeter.
- **Modern CLI:** Beautiful CLI execution output and metrics dashboard integration.

---

## Simple k6 Test Script

Create a file named `checkout_load_test.js`:

```javascript
// checkout_load_test.js
import http from 'k6/http';
import { sleep, check } from 'k6';

// 1. Define load options (Ramp-up, stages)
export const options = {
  stages: [
    { duration: '30s', target: 50 },  // Ramp-up: 0 to 50 users in 30s
    { duration: '1m', target: 50 },   // Maintain: Stay at 50 users for 1 min
    { duration: '15s', target: 0 },   // Ramp-down: 50 to 0 users in 15s
  ],
  thresholds: {
    http_req_duration: ['p(95)<500'], // 95% of requests must complete under 500ms
  },
};

// 2. Main execution flow for each virtual user (VU)
export default function () {
  const url = 'https://qa.api.example.com/products';
  const res = http.get(url);

  // Assertions
  check(res, {
    'status is 200': (r) => r.status === 200,
  });

  sleep(1); // Wait 1 second before repeat
}
```

To execute the load test locally:
```bash
k6 run checkout_load_test.js
```

---

## 📌 Key Takeaways
- **Thresholds** allow you to define strict performance SLAs (e.g., if error rate $> 1\%$, fail the build).
- Lightweight, fast, and highly scriptable.
- Integrates seamlessly with Grafana, Prometheus, or InfluxDB for real-time visualization.
