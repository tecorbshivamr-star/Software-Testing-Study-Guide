# Playwright Page Object Model (POM)

Just like Selenium, the Page Object Model (POM) is the design pattern standard for organizing Playwright automation suites.

---

## POM Code Implementation (Python)

### 1. The Page Object Class
```python
# login_page.py
from playwright.sync_api import Page

class LoginPage:
    def __init__(self, page: Page):
        self.page = page
        # Locators defined using Playwright's locator API
        self.email_input = page.locator("#email")
        self.pass_input  = page.locator("#password")
        self.submit_btn  = page.locator("#login-btn")
        self.error_msg   = page.locator(".alert-danger")

    def navigate(self, base_url: str):
        self.page.goto(f"{base_url}/login")
        return self

    def perform_login(self, email: str, password: str):
        self.email_input.fill(email)
        self.pass_input.fill(password)
        self.submit_btn.click()
```

### 2. The Pytest Test Case
```python
# test_login.py
import pytest
from playwright.sync_api import Page
from login_page import LoginPage

def test_invalid_login_error(page: Page):
    # Initialize Page Object (Page is a built-in Playwright pytest fixture!)
    login_page = LoginPage(page).navigate("https://qa.ecommerce.com")
    login_page.perform_login("fake@user.com", "WrongPassword")

    # Assert error banner text
    error_text = login_page.error_msg.text_content()
    assert "Invalid credentials" in error_text
```

---

## Selenium POM vs Playwright POM

| Feature | Selenium POM | Playwright POM |
|---|---|---|
| **Element Creation** | `driver.find_element()` | `page.locator()` |
| **Locators** | Static, immediate DOM check | Lazy-loaded (checked only during execution) |
| **Explicit Wait** | Required for all dynamic items | Built-in automatic assertions |

---

## 📌 Key Takeaways
- Playwright's `locator` API is **lazy-loaded**—it doesn't query the DOM until you perform an action (e.g., click, fill), reducing timing issues.
- Playwright automatically detects when page elements refresh.
- Pytest's built-in `page` fixture handles browser context setup and teardown automatically.
