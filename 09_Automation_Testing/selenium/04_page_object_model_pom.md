# Selenium Page Object Model (POM)

The **Page Object Model (POM)** is a design pattern that structures UI automation frameworks cleanly by separating page locators and actions from the actual test cases.

---

## The POM Architectural Layer

```
                        [ Test Cases Layer ]
                  (e.g., test_valid_login_redirects())
                                 │
                                 ▼
                     [ Page Objects Classes ]
                (e.g., LoginPage class actions)
                                 │
                                 ▼
                     [ Locators & UI Engine ]
                   (e.g., By.ID, By.CSS selectors)
```

---

## POM Code Implementation (Python)

### 1. The Base Page (Parent Page class)
Contains common actions and waits for all pages.
```python
# base_page.py
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

class BasePage:
    def __init__(self, driver):
        self.driver = driver
        self.wait = WebDriverWait(driver, 10)

    def find(self, locator):
        return self.wait.until(EC.visibility_of_element_located(locator))

    def click(self, locator):
        self.find(locator).click()

    def type(self, locator, text):
        element = self.find(locator)
        element.clear()
        element.send_keys(text)
```

### 2. The Login Page Object (Child Page class)
Defines locators as class constants, and custom business flows as methods.
```python
# login_page.py
from selenium.webdriver.common.by import By
from base_page import BasePage

class LoginPage(BasePage):
    # Locators
    EMAIL_INPUT = (By.ID, "email")
    PASS_INPUT  = (By.ID, "password")
    SUBMIT_BTN  = (By.ID, "login-btn")
    ERROR_BANNER = (By.CLASS_NAME, "alert-danger")

    def __init__(self, driver):
        super().__init__(driver)

    def navigate(self, base_url):
        self.driver.get(f"{base_url}/login")
        return self

    def perform_login(self, email, password):
        self.type(self.EMAIL_INPUT, email)
        self.type(self.PASS_INPUT, password)
        self.click(self.SUBMIT_BTN)
```

### 3. The Clean Test Script
```python
# test_login.py
import pytest
from login_page import LoginPage

def test_invalid_login_error_message(driver):
    login_page = LoginPage(driver).navigate("https://qa.ecommerce.com")
    login_page.perform_login("fakeuser@test.com", "WrongPassword")
    
    # Assert error banner text
    error_text = login_page.find(LoginPage.ERROR_BANNER).text
    assert "Invalid credentials" in error_text
```

---

## 📌 Key Takeaways
- Easy to maintain—if a developer changes the `login-btn` ID to `submit-btn`, you only update **one line** in the `LoginPage` class, rather than 50 different test scripts.
- Aligns tests with actual product requirements.
- Eliminates code duplication across workflows.
