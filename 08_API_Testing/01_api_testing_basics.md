# API Testing Complete Guide

## What Is API Testing?

**API Testing** is a type of software testing that validates **Application Programming Interfaces (APIs)** — ensuring they work correctly, reliably, and securely. It tests at the **business logic layer**, between the UI and database.

> *"API testing is faster, more reliable, and more stable than UI testing. It's the backbone of modern QA automation."*

---

## Why API Testing?

| Advantage | Description |
|-----------|-------------|
| **Fast** | No browser rendering — 10–100x faster than UI tests |
| **Stable** | APIs change less often than UIs |
| **Early** | Test backend before UI is built |
| **Precise** | Direct data validation |
| **Automation-friendly** | Easy to integrate in CI/CD |

---

## REST API Fundamentals

### HTTP Methods

| Method | Purpose | Idempotent? | Body? |
|--------|---------|-------------|-------|
| **GET** | Retrieve data | ✅ Yes | ❌ No |
| **POST** | Create data | ❌ No | ✅ Yes |
| **PUT** | Replace/update (full) | ✅ Yes | ✅ Yes |
| **PATCH** | Partial update | ✅ Yes | ✅ Yes |
| **DELETE** | Delete data | ✅ Yes | Optional |

### HTTP Status Codes

| Code | Meaning | When |
|------|---------|------|
| **200** | OK | Successful GET/PUT/PATCH |
| **201** | Created | Successful POST |
| **204** | No Content | Successful DELETE |
| **400** | Bad Request | Invalid request body/params |
| **401** | Unauthorized | Missing/invalid auth token |
| **403** | Forbidden | Authenticated but no permission |
| **404** | Not Found | Resource doesn't exist |
| **422** | Unprocessable Entity | Validation errors |
| **429** | Too Many Requests | Rate limit exceeded |
| **500** | Internal Server Error | Server-side bug |

---

## What to Test in APIs

### Functional Testing
- ✅ Does the endpoint return correct data?
- ✅ Correct status code returned?
- ✅ Response schema matches documentation?
- ✅ All required fields present in response?

### Validation Testing
- ✅ Invalid input returns 400 with clear error message?
- ✅ Missing required fields handled?
- ✅ Field type validation works (string/int/date)?
- ✅ Max length validation enforced?

### Authentication Testing
- ✅ Unauthenticated requests return 401?
- ✅ Expired tokens rejected?
- ✅ Invalid tokens rejected?
- ✅ Correct permissions enforced (403 for unauthorized roles)?

### Performance Testing
- ✅ Response time < 500ms for standard calls?
- ✅ API handles concurrent requests?

### Security Testing
- ✅ SQL injection in query params?
- ✅ Sensitive data not exposed in response?
- ✅ CORS configured correctly?

---

## Sample API Test: Login Endpoint

**Endpoint:** `POST /api/v1/auth/login`

### Test 1: Valid Login
```
Request:
POST /api/v1/auth/login
Content-Type: application/json

{
  "email": "testuser@qa.com",
  "password": "Test@1234"
}

Expected Response: 200 OK
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": 123,
    "email": "testuser@qa.com",
    "name": "Test User"
  }
}

Assertions:
✅ Status code = 200
✅ token field exists and is non-empty
✅ token is a valid JWT format
✅ user.email matches request email
```

### Test 2: Invalid Password
```
Request:
POST /api/v1/auth/login
{"email": "testuser@qa.com", "password": "WrongPass"}

Expected: 401 Unauthorized
{"error": "Invalid email or password"}

Assertions:
✅ Status = 401
✅ Response body has "error" field
✅ No token in response
```

### Test 3: Missing Email Field
```
Request:
POST /api/v1/auth/login
{"password": "Test@1234"}

Expected: 400 Bad Request
{"error": "email is required"}

Assertions:
✅ Status = 400
✅ Error mentions "email"
```

---

## API Testing Tools

| Tool | Best For | Language |
|------|---------|---------|
| **Postman** | Manual + Collection runs | GUI |
| **Rest Assured** | Java automation | Java |
| **Pytest + requests** | Python automation | Python |
| **Newman** | Postman in CI/CD | CLI |
| **Insomnia** | Manual testing | GUI |
| **k6** | Performance + API | JavaScript |

---

## Pytest API Test Example

```python
import requests
import pytest

BASE_URL = "https://qa.api.example.com"

class TestLoginAPI:

    def test_valid_login_returns_200_and_token(self):
        payload = {"email": "testuser@qa.com", "password": "Test@1234"}
        response = requests.post(f"{BASE_URL}/auth/login", json=payload)

        assert response.status_code == 200, f"Expected 200, got {response.status_code}"
        data = response.json()
        assert "token" in data, "Token missing in response"
        assert len(data["token"]) > 0, "Token should not be empty"

    def test_invalid_password_returns_401(self):
        payload = {"email": "testuser@qa.com", "password": "WrongPass"}
        response = requests.post(f"{BASE_URL}/auth/login", json=payload)

        assert response.status_code == 401
        assert "error" in response.json()

    def test_missing_email_returns_400(self):
        payload = {"password": "Test@1234"}
        response = requests.post(f"{BASE_URL}/auth/login", json=payload)

        assert response.status_code == 400
```

---

## 📌 Key Takeaways

- API testing is **faster, cheaper, and more stable** than UI testing
- Always test: status codes, response body, schema, headers, performance, security
- Use **Postman** for manual exploration, **pytest/requests** for automation
- API tests belong in the **Integration layer** of the testing pyramid
- Automate API tests in **CI/CD** for fast regression feedback

---

*Related: [Postman Guide](./06_postman_complete_guide.md) | [REST Assured](./07_rest_assured_java_guide.md)*
