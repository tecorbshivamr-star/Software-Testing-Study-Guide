# Apache JMeter Guide

## What is Apache JMeter?
**Apache JMeter** is a standard, open-source, Java-based desktop application designed to load test functional behavior and measure system performance under heavy load.

---

## 5 Core Components of a JMeter Test Plan

### 1. Thread Group
Represents the users. Defines how many virtual users (threads) will run, and the Ramp-Up time.
- **Ramp-Up Time:** The duration it takes to spin up all defined threads (e.g., 100 threads with 50s ramp-up = 2 threads spawned per second).

### 2. Samplers
The actual requests (HTTP, SOAP, FTP, JDBC, etc.) that the threads execute.
- *Example:* **HTTP Request** sampler configured to fetch `/api/v1/products`.

### 3. Listeners
Visualizers that capture, display, and analyze test execution results.
- *Examples:* **View Results Tree** (detailed request/response debug), **Aggregate Report** (overall average/min/max latency stats).
- 🔴 *Warning:* Listeners consume massive JVM memory. Disable them during real load runs!

### 4. Assertions
Validations placed on samplers to verify that response contents and status codes are correct.
- *Example:* **Response Assertion** verifying that HTTP code equals 200.

### 5. Config Elements
Used to manage headers, cookies, variables, or read external CSV parameters.
- *Example:* **CSV Data Set Config** used to parameterized logins.

---

## Running JMeter in CLI (Non-GUI Mode)

Never run real load tests in GUI mode—it will crash your local computer due to JVM overhead. Always run load tests in non-GUI mode:

```bash
jmeter -n -t search_load_test.jmx -l results.jtl -e -o reports/dashboard
```

- `-n`: Non-GUI mode.
- `-t`: Path to your `.jmx` test plan file.
- `-l`: Path to save raw transaction execution logs (`.jtl`).
- `-e -o`: Generates a beautiful HTML report dashboard at the target output path.

---

## 📌 Key Takeaways
- GUI mode is strictly for script **authoring and debugging**, not load runs.
- Run load tests from a dedicated machine (not your local workspace).
- Check standard JVM heap configurations in `jmeter.sh` if memory issues occur.
