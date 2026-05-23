# Cypress Setup Guide

## What is Cypress?
**Cypress** is a next-generation, JavaScript-based front-end testing tool built for the modern web. It runs directly inside the browser, enabling extremely fast and reliable testing of anything that runs in a browser.

---

## Why Cypress?
- **Fast:** Runs inside the actual browser execution loop.
- **Time Travel:** Hover over command logs to see exactly what happened during each test step.
- **Auto-Waiting:** Built-in assertions wait for elements to appear automatically.
- **Screenshots & Videos:** Captures media automatically on test failures.

---

## Cypress Setup (JavaScript)

### Step 1: Initialize Project
Create a new directory and run:
```bash
npm init -y
```

### Step 2: Install Cypress
Install Cypress as a dev dependency:
```bash
npm install cypress --save-dev
```

### Step 3: Open Cypress Runner
Launch the interactive Cypress Test Runner:
```bash
npx cypress open
```

---

## Writing Your First Cypress Test

Create a file named `cypress/e2e/first_test.cy.js`:

```javascript
// first_test.cy.js
describe('Google Search Test Suite', () => {
  it('Verify Google search landing page title', () => {
    // 1. Navigate to URL
    cy.visit('https://www.google.com')

    // 2. Assert title (Auto-waiting built-in!)
    cy.title().should('include', 'Google')
  })
})
```

To run tests in headless mode:
```bash
npx cypress run
```

---

## 📌 Key Takeaways
- Cypress runs directly **inside the browser** alongside the application code.
- Uses JavaScript/TypeScript as its primary programming language.
- Exclude node_modules from your Git repository configurations (`.gitignore`).
