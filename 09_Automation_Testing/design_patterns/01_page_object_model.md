# Page Object Model (POM) — Complete Guide

## What Is POM?

**Page Object Model (POM)** is a design pattern where each web page has a corresponding class containing its locators and actions. Tests use these classes instead of raw Selenium commands.

> *"POM separates test logic from UI interaction — readable, maintainable, reusable."*

---

## POM Structure

```
project/
├── pages/
│   ├── base_page.py       ← Common methods
│   ├── login_page.py      ← Login locators + actions
│   └── dashboard_page.py  ← Dashboard locators + actions
├── tests/
│   ├── conftest.py        ← Fixtures
│   └── test_login.py      ← Test cases
└── utils/
    └── helpers.py
```

---

## Base Page

```python
# pages/base_page.py
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

class BasePage:
    def __init__(self, driver):
        self.driver = driver
        self.wait = WebDriverWait(driver, timeout=10)

    def find(self, locator):
        return self.wait.until(EC.visibility_of_element_located(locator))

    def click(self, locator):
        self.find(locator).click()

    def fill(self, locator, text):
        el = self.find(locator)
        el.clear()
        el.send_keys(text)

    def get_text(self, locator):
        return self.find(locator).text

    def is_visible(self, locator):
        try:
            return self.find(locator).is_displayed()
        except Exception:
            return False
```

---

## Login Page Object

```python
# pages/login_page.py
from selenium.webdriver.common.by import By
from pages.base_page import BasePage

class LoginPage(BasePage):
    EMAIL     = (By.ID, "email")
    PASSWORD  = (By.ID, "password")
    LOGIN_BTN = (By.ID, "login-submit")
    ERROR_MSG = (By.CSS_SELECTOR, ".alert-error")
    DASHBOARD = (By.ID, "dashboard-header")

    def open(self, base_url):
        self.driver.get(f"{base_url}/login")
        return self

    def login(self, email, password):
        self.fill(self.EMAIL, email)
        self.fill(self.PASSWORD, password)
        self.click(self.LOGIN_BTN)
        return self

    def get_error(self):
        return self.get_text(self.ERROR_MSG)

    def is_dashboard_loaded(self):
        return self.is_visible(self.DASHBOARD)
```

---

## Test File

```python
# tests/test_login.py
import pytest
from pages.login_page import LoginPage

@pytest.mark.smoke
def test_valid_login(driver, base_url):
    page = LoginPage(driver).open(base_url)
    page.login("testuser@qa.com", "Test@1234")
    assert page.is_dashboard_loaded()

@pytest.mark.regression
def test_wrong_password_shows_error(driver, base_url):
    page = LoginPage(driver).open(base_url)
    page.login("testuser@qa.com", "WrongPass")
    assert "Invalid" in page.get_error()
```

---

## conftest.py

```python
import pytest
from selenium import webdriver
from selenium.webdriver.chrome.options import Options

@pytest.fixture(scope="session")
def base_url():
    return "https://qa.yourapp.com"

@pytest.fixture(scope="function")
def driver():
    options = Options()
    options.add_argument("--headless")
    driver = webdriver.Chrome(options=options)
    yield driver
    driver.quit()
```

---

## POM Best Practices

| ✅ Do | ❌ Don't |
|------|--------|
| Return `self` for chaining | Put assertions in page objects |
| Locators as class constants | Raw `find_element` in tests |
| Explicit waits only | `time.sleep()` |
| One class per page | Mix test logic in page class |

---

## 📌 Key Takeaways

- Locator change → update **one file only**
- Tests read like **business scenarios**
- Combine with **pytest fixtures** for scalability
- Foundation of every professional automation framework
