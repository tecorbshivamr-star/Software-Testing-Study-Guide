# Appium Setup Guide

## What is Appium?
**Appium** is an open-source, cross-platform test automation tool used to validate Native, Hybrid, and Mobile Web applications on iOS and Android.

> *"Appium lets you write tests against mobile platforms using the standard W3C WebDriver API—the same philosophy behind Selenium."*

---

## Key Architectural Pipeline

```
[ Appium Script (Java/Python) ] ──→ [ Appium Server ] ──→ [ UI Automator (Android) / XCUITest (iOS) ] ──→ [ Device ]
```

---

## Setting Up Appium for Android (Python)

### Step 1: Install Appium Server
```bash
npm install -g appium
```

### Step 2: Install Appium Python Client
```bash
pip install Appium-Python-Client
```

### Step 3: Configure Android Home Paths
Ensure your environment variables are configured in `.bashrc` or `.zshrc`:
```bash
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

### Step 4: Write Your First Appium Script
Create a file named `test_appium_android.py`:

```python
# test_appium_android.py
from appium import webdriver
from appium.options.android import UiAutomator2Options

def test_android_calc():
    # 1. Define target capabilities
    options = UiAutomator2Options()
    options.platform_name = "Android"
    options.device_name = "emulator-5554"
    options.app_package = "com.android.calculator2"
    options.app_activity = ".Calculator"

    # 2. Initialize driver session pointing to local Appium server
    driver = webdriver.Remote("http://localhost:4723", options=options)

    try:
        # 3. Perform clicks (Standard Selenium syntax!)
        driver.find_element(by="id", value="com.android.calculator2:id/digit_7").click()
        print("Successfully interacted with emulator!")
        
    finally:
        driver.quit()

if __name__ == "__main__":
    test_android_calc()
```

---

## Appium Inspector
A vital desktop companion GUI tool used to inspect elements, discover UI resource-ids, and record actions directly on the active mobile screen.

---

## 📌 Key Takeaways
- Appium utilizes **W3C WebDriver** selectors—making the syntax identical to Selenium.
- Always use `UiAutomator2Options` for Android and `XCUITestOptions` for iOS.
- **Appium Inspector** is crucial for identifying target locators.
