# Selenium Setup Guide (Python)

## What is Selenium?
**Selenium WebDriver** is the most popular open-source automated testing suite used to validate web applications across different browsers and platforms.

---

## 3 Steps to Setup Selenium with Python

### Step 1: Install Python & Selenium Client
Open your terminal and run:
```bash
pip install selenium
```

### Step 2: Install WebDriver Manager (Recommended)
Historically, testers had to manually download `chromedriver` or `geckodriver` binary files and place them in the environment path.

Using **Webdriver Manager** automates this entirely:
```bash
pip install webdriver-manager
```

### Step 3: Write Your First Selenium Script
Create a file named `test_selenium_basic.py`:

```python
# test_selenium_basic.py
from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from webdriver_manager.chrome import ChromeDriverManager
import time

def test_google_search():
    # 1. Initialize Chrome Driver automatically
    service = Service(ChromeDriverManager().install())
    driver = webdriver.Chrome(service=service)

    try:
        # 2. Navigate to a webpage
        driver.get("https://www.google.com")
        driver.maximize_window()

        # 3. Assert correct page title
        assert "Google" in driver.title
        print("Page title verified successfully!")
        
    finally:
        # 4. Terminate browser session cleanly
        driver.quit()

if __name__ == "__main__":
    test_google_search()
```

---

## 📌 Key Takeaways
- Always use `webdriver-manager` to avoid manual driver binary mismatches.
- Always wrap your test code inside `try-finally` blocks and call `driver.quit()` to prevent orphaned browser background processes from eating server RAM.
- Use `driver.quit()` (closes all windows) rather than `driver.close()` (only closes the active window).
