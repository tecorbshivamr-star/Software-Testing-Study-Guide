# Cypress Best Practices

To build scalable and non-flaky test suites in Cypress, follow these industry-standard best practices.

---

## 5 Cypress Commandments

### 1. Use Custom `data-*` Attributes
Do not locate elements using CSS classes (which devs change often for styling) or fragile dynamic IDs. Use custom test attributes:
- ❌ *Bad (Fragile class):* `cy.get('.btn-primary')`
- ✅ *Good (Stable test attribute):* `cy.get('[data-cy=submit-btn]')`

---

### 2. Never Use `cy.wait(Number)`
Hardcoded pauses (`time.sleep` equivalents) are an anti-pattern. Always wait for specific UI selectors or API network routes instead.
- ❌ *Bad (Hardcoded sleep):* `cy.wait(5000)`
- ✅ *Good (Wait for API response):*
  ```javascript
  cy.intercept('POST', '/api/v1/checkout').as('checkoutCall')
  cy.get('[data-cy=pay]').click()
  cy.wait('@checkoutCall')  // Wait for the exact network response!
  ```

---

### 3. Keep Tests Isolated (No Dependencies)
Do not make test B dependent on test A passing. Every test should be runnable in isolation.
- **Tip:** Reset the application database or clear cookies before each run inside the `beforeEach` hook.

---

### 4. Create Custom Commands for Reusable Tasks
For actions executed repeatedly (like user login), define custom helper commands in `cypress/support/commands.js`.

```javascript
// cypress/support/commands.js
Cypress.Commands.add('performLogin', (email, password) => {
  cy.visit('/login')
  cy.get('[data-cy=email]').type(email)
  cy.get('[data-cy=password]').type(password)
  cy.get('[data-cy=submit]').click()
})
```
*Usage in script:* `cy.performLogin('user@qa.com', 'Pass123')`

---

### 5. Verify Database/API Direct States
Don't just trust the UI. If a test updates a profile, use `cy.request()` to query the backend database directly and verify the changes occurred.

---

## 📌 Key Takeaways
- Use **`data-cy` attributes** for stable locators.
- Leverage **network interception (`cy.intercept`)** to handle API latency safely.
- Never use blind timing sleeps.
