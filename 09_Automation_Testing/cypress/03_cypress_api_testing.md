# Cypress API Testing

Cypress is not just a UI automation tool—it is also highly efficient for testing REST API endpoints directly using `cy.request()`.

---

## Why Test APIs with Cypress?
- **Speed:** API tests run in milliseconds.
- **Chaining:** Use API calls to set up test data (e.g., seeding a user) before running UI validation scripts.
- **No UI Lag:** Fast, direct backend verification.

---

## Simple Cypress API Test Script

Create a file named `cypress/e2e/api_test.cy.js`:

```javascript
// api_test.cy.js
describe('E-Commerce API Testing Suite', () => {

  it('TC_01: Verify valid login returns JWT token', () => {
    cy.request({
      method: 'POST',
      url: 'https://qa.api.example.com/auth/login',
      body: {
        email: 'testuser@qa.com',
        password: 'Test@1234'
      },
      failOnStatusCode: false  // Prevent Cypress from throwing errors immediately on failure status codes
    }).then((response) => {
      // 1. Assert status code
      expect(response.status).to.eq(200)

      // 2. Assert body schema properties
      expect(response.body).to.have.property('token')
      expect(response.body.token).to.not.be.empty

      // 3. Assert nested data
      expect(response.body.user.email).to.eq('testuser@qa.com')
    })
  })

})
```

---

## 📌 Key Takeaways
- Use **`cy.request()`** to send direct HTTP requests (GET, POST, etc.).
- Set **`failOnStatusCode: false`** when testing negative paths (so Cypress doesn't break when validating `400` or `401` errors).
- Use **`expect`** statements to run Assertions on status codes, response headers, and JSON keys.
