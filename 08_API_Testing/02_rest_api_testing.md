# REST API Testing

## What is REST?
**REST (Representational State Transfer)** is an architectural style for designing networked applications. It relies on a stateless, client-server protocol—almost always **HTTP**.

---

## Core Characteristics of REST APIs

1. **Stateless:** Every API request from a client must contain all the information necessary to understand and process the request. No session state is stored on the server.
2. **Resource-Oriented:** Data and functionality are considered resources and are accessed using Uniform Resource Identifiers (URIs) (e.g., `/api/v1/users/123`).
3. **JSON/XML Support:** Communicates predominantly using JSON (JavaScript Object Notation) or XML payloads.

---

## What to Validate in REST API Testing

When testing a REST endpoint, perform these 5 checks:

### 1. HTTP Status Code
Ensure the correct status code returns (e.g., `201 Created` for POST, `404 Not Found` for missing resources).

### 2. Response Headers
Verify important headers like:
- `Content-Type: application/json`
- `Cache-Control`
- Security headers (e.g., `X-Content-Type-Options`)

### 3. Response Schema
Verify that the JSON response matches the expected structural data types (e.g., `id` is an integer, `email` matches email regex).

### 4. Data Accuracy
Validate that the values in the JSON fields are mathematically correct and correspond directly to the database or parameters sent.

### 5. Performance
Verify that response times are acceptable (usually $< 500\text{ms}$).

---

## 📌 Key Takeaways
- REST APIs are resource-centric—URI pathways represent the nouns, while HTTP methods represent the verbs.
- Validate both **positive paths** (correct data) and **negative paths** (correct validation errors).
- Automated REST API testing is extremely fast and stable.
