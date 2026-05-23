# API Testing Interview Q&A

> Covers REST APIs, HTTP methods, status codes, Postman, and API validation strategies.

---

## 🔵 Section 1: API Fundamentals

**Q1. What is an API?**
Application Programming Interface. It acts as a bridge allowing two different software systems to communicate and exchange data.

**Q2. What is the difference between REST and SOAP?**
- **REST:** Architectural style, uses HTTP methods, supports multiple formats (JSON, XML, text), lightweight, stateless.
- **SOAP:** Protocol, strictly uses XML, requires a WSDL contract, heavy bandwidth, highly secure (built-in ACID compliance).

**Q3. Explain the common HTTP Methods.**
- **GET:** Retrieve data. (Safe, Idempotent)
- **POST:** Create new data. (Not safe, Not idempotent)
- **PUT:** Update/replace entire existing data. (Idempotent)
- **PATCH:** Partially update existing data.
- **DELETE:** Remove data. (Idempotent)

**Q4. What does "Idempotent" mean in REST?**
Making the same request multiple times produces the exact same result/system state as making it once. (e.g., `DELETE /user/1` multiple times still results in user 1 being deleted).

**Q5. Explain common HTTP Status Codes.**
- **200 OK:** Success.
- **201 Created:** Success for POST requests.
- **204 No Content:** Success but no body returned (common for DELETE).
- **400 Bad Request:** Client sent invalid data/format.
- **401 Unauthorized:** Missing or invalid authentication token.
- **403 Forbidden:** Authenticated, but lacks permission to access the resource.
- **404 Not Found:** Endpoint or resource doesn't exist.
- **500 Internal Server Error:** Server crashed or encountered an unhandled exception.

---

## 🟡 Section 2: API Testing Strategy

**Q6. What do you verify when testing an API?**
1. **Status Code:** Is it correct for the operation?
2. **Response Body:** Does the JSON match the expected schema and contain accurate data?
3. **Headers:** Are required headers present (e.g., `Content-Type: application/json`)?
4. **Performance:** Does it respond within acceptable time limits (< 500ms)?
5. **Security/Auth:** Are unauthorized requests properly rejected?

**Q7. How do you test API Authentication?**
- Try accessing without a token $\to$ Expect 401.
- Try accessing with an expired/invalid token $\to$ Expect 401.
- Try accessing a resource belonging to another user $\to$ Expect 403.
- Access with a valid token $\to$ Expect 200.

**Q8. What is a Payload?**
The actual data sent in the body of an HTTP request (usually POST/PUT) or returned in the response.

**Q9. What are Query Parameters vs. Path Variables?**
- **Path Variable:** Identifies a specific resource. e.g., `/users/123` (123 is the path variable).
- **Query Parameter:** Filters or sorts a list of resources. e.g., `/users?status=active&age=25`.

---

## 🔴 Section 3: Tools (Postman & Automation)

**Q10. How do you pass data between requests in Postman?**
Using Postman Environment or Global variables. In the "Tests" tab of Request A, parse the JSON response, extract the value, and set it to a variable:
`pm.environment.set("token", pm.response.json().token);`
Then in Request B, use `{{token}}` in the headers.

**Q11. What are Pre-request scripts in Postman?**
JavaScript code that executes *before* the API request is sent. Useful for generating dynamic test data (like random emails) or calculating authentication signatures.

**Q12. How do you run Postman collections in a CI/CD pipeline?**
Using **Newman**, the command-line collection runner for Postman. Command: `newman run collection.json -e environment.json`

---

*Related: [HTTP Methods & Status Codes](../08_API_Testing/05_http_methods_status_codes.md) | [Postman Guide](../08_API_Testing/06_postman_complete_guide.md)*
