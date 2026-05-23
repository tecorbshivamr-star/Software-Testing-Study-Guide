# Postman Complete Guide

Postman is the industry-standard tool for testing APIs manually and conducting automated runner tests.

---

## Postman Core Variables

- **Global Variables:** Accessible across the entire workspace.
- **Environment Variables:** Specific to individual environments (e.g., QA, Staging, Prod).
  - *Usage:* `{{baseUrl}}/api/v1/login`
- **Collection Variables:** Local to one specific collection only.

---

## Writing Assertions in Postman (Tests Tab)

Postman allows you to write JavaScript assertions that run automatically after every response.

```javascript
// 1. Assert status code is 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// 2. Assert response time is less than 500ms
pm.test("Response time is less than 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
});

// 3. Parse JSON and assert data values
pm.test("Token is present and valid", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property("token");
    pm.expect(jsonData.token).to.not.be.empty;
});

// 4. Save token dynamically to environment variables (Chaining)
var token = pm.response.json().token;
pm.environment.set("jwtToken", token);
```

---

## Pre-request Scripts
Scripts that run **before** the API call is made. Excellent for dynamically generating timestamps, random emails, or signing headers.

```javascript
// Generate a unique email for registration tests
var randomInt = Math.floor(Math.random() * 10000);
pm.variables.set("randomEmail", "qauser" + randomInt + "@gmail.com");
```

---

## Automated Collection Running
1. Use **Postman Collection Runner** to run all tests in a collection sequentially.
2. Use **Newman** (CLI tool) to run Postman collections inside CI/CD pipelines:
```bash
newman run my_collection.json -e my_environment.json -r html
```

---

## 📌 Key Takeaways
- Use **Environment Variables** to easily switch between QA and Staging servers.
- Use **Pre-request Scripts** to prevent duplicate data errors (e.g., generating unique emails).
- Extract and set tokens dynamically to avoid hardcoding auth tokens.
