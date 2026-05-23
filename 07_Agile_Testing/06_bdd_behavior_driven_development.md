# BDD — Behavior Driven Development

## What Is BDD?

**Behavior Driven Development (BDD)** is an Agile testing approach where tests are written in **plain English** (using Gherkin syntax) that both technical and non-technical stakeholders can understand. It bridges the gap between business requirements and automated tests.

> *"BDD makes tests readable by everyone — business, developers, and QA — creating a shared understanding of what the software should do."*

---

## BDD vs TDD

| Aspect | TDD | BDD |
|--------|-----|-----|
| **Written by** | Developers | QA + Dev + Business (3 Amigos) |
| **Language** | Code | Plain English (Gherkin) |
| **Focus** | Code correctness | Business behavior |
| **Tests describe** | Methods/functions | User scenarios |
| **Framework** | JUnit, pytest | Cucumber, Behave, SpecFlow |

---

## Gherkin Syntax — Given / When / Then

BDD scenarios are written in **Gherkin** format:

```gherkin
Feature: User Login

  Scenario: Successful login with valid credentials
    Given the user is on the login page
    When the user enters email "testuser@qa.com"
    And the user enters password "Test@1234"
    And the user clicks the "Login" button
    Then the user should be redirected to the dashboard
    And the welcome message "Hello, Test User" should be displayed

  Scenario: Login fails with incorrect password
    Given the user is on the login page
    When the user enters email "testuser@qa.com"
    And the user enters password "WrongPassword"
    And the user clicks the "Login" button
    Then the error message "Invalid email or password." should be displayed
    And the user should remain on the login page
```

---

## Gherkin Keywords

| Keyword | Purpose | Example |
|---------|---------|---------|
| `Feature` | Describes the feature being tested | `Feature: Shopping Cart` |
| `Scenario` | One test scenario | `Scenario: Add item to cart` |
| `Given` | Precondition/context | `Given user is logged in` |
| `When` | Action performed | `When user clicks Add to Cart` |
| `Then` | Expected outcome | `Then cart count shows 1` |
| `And` | Additional Given/When/Then | `And the item is in stock` |
| `But` | Negative And | `But the discount is not applied` |
| `Background` | Shared Given for all scenarios | Login before each scenario |
| `Scenario Outline` | Data-driven scenarios | Multiple emails/passwords |
| `Examples` | Data table for Scenario Outline | Test data rows |

---

## Scenario Outline (Data-Driven BDD)

```gherkin
Scenario Outline: Login with multiple user types
  Given the user is on the login page
  When the user enters email "<email>"
  And the user enters password "<password>"
  And the user clicks Login
  Then the user should see "<expected_result>"

  Examples:
    | email              | password    | expected_result   |
    | admin@test.com     | Admin@123   | Admin Dashboard   |
    | user@test.com      | User@123    | User Dashboard    |
    | wrong@test.com     | BadPass     | Error message     |
```

---

## BDD Implementation — Python (Behave)

```python
# features/login.feature → Gherkin file (above)

# features/steps/login_steps.py
from behave import given, when, then

@given('the user is on the login page')
def step_open_login(context):
    context.browser.get("https://qa.app.com/login")

@when('the user enters email "{email}"')
def step_enter_email(context, email):
    context.browser.find_element("id", "email").send_keys(email)

@when('the user enters password "{password}"')
def step_enter_password(context, password):
    context.browser.find_element("id", "password").send_keys(password)

@when('the user clicks the "{button}" button')
def step_click_button(context, button):
    context.browser.find_element("xpath", f"//button[text()='{button}']").click()

@then('the user should be redirected to the dashboard')
def step_verify_dashboard(context):
    assert "/dashboard" in context.browser.current_url
```

---

## BDD Tools by Language

| Tool | Language | Notes |
|------|----------|-------|
| **Cucumber** | Java, JS, Ruby | Most popular |
| **Behave** | Python | Pythonic BDD |
| **SpecFlow** | C# / .NET | Enterprise BDD |
| **Pytest-BDD** | Python | BDD with pytest |
| **Cypress + Cucumber** | JavaScript | UI + BDD |

---

## Three Amigos Meeting

BDD scenarios are best written in a **Three Amigos** meeting:
- 👔 **Product Owner** — defines acceptance criteria
- 👨‍💻 **Developer** — flags technical constraints
- 🧪 **QA Engineer** — identifies edge cases and negative scenarios

This creates **shared understanding** before any code is written.

---

## 📌 Key Takeaways

- BDD = tests written in **plain English** using Given/When/Then
- Living documentation — scenarios serve as **both tests AND specs**
- **Three Amigos** ensures everyone agrees before coding starts
- BDD works best for **integration and E2E tests** (not unit tests)
- `Scenario Outline` + `Examples` enables **data-driven BDD**

---

*Related: [TDD](./05_tdd_test_driven_development.md) | [ATDD](./07_atdd_acceptance_tdd.md)*
