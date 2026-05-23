# Selenium Waits: Implicit, Explicit, and Fluent

Web applications rely heavily on AJAX, React, and network calls—meaning page elements load asynchronously. If a script tries to click an element before it renders, Selenium throws a `NoSuchElementException`. 

Waits are how we prevent flaky tests.

---

## 3 Types of Selenium Waits

### 1. Implicit Wait (Global / Dumb Wait)
Tells Selenium to poll the DOM for a set duration (e.g., 10 seconds) before throwing an error.
- **Scope:** Applies globally to all element search calls during the entire driver session.
- **Drawback:** Dumb. If an element is in the DOM but hidden, implicit wait won't wait for it to become clickable.
```python
driver.implicitly_wait(10)  # Wait up to 10s for all elements globally
```

---

### 2. Explicit Wait (Local / Smart Wait)
Tells Selenium to wait for a **specific condition** on a **specific element** before proceeding.
- **Scope:** Local to the target locator call.
- **Pros:** Smart. Checks states (e.g., visibility, clickability, text contents).
```python
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.common.by import By

# Wait up to 10s until the submit button is fully clickable
wait = WebDriverWait(driver, timeout=10)
button = wait.until(EC.element_to_be_clickable((By.ID, "submit")))
button.click()
```

---

### 3. Fluent Wait (Highly Custom Smart Wait)
A specialized flavor of Explicit Wait where you define:
- The maximum timeout duration.
- The polling frequency (how often to check).
- What exceptions to ignore (e.g., ignore `NoSuchElementException` while polling).

```python
# Custom explicit wait with custom polling interval (Fluent wait behavior)
wait = WebDriverWait(driver, timeout=10, poll_frequency=1.0, ignored_exceptions=[NoSuchElementException])
element = wait.until(EC.visibility_of_element_located((By.ID, "status-message")))
```

---

## Why You Should NEVER Mix Implicit and Explicit Waits!
Mixing them can cause unexpected session freezes or double timeouts. For instance, if implicit wait is 10s and explicit is 10s, a failure can freeze the thread for up to **20 seconds** before raising an exception.

---

## 📌 Key Takeaways
- **Never** use `time.sleep()` in test scripts—it freezes execution blindly, slowing down runs.
- **Explicit Waits** are the modern QA industry standard.
- Use explicit waits inside **Base Page** wrappers to ensure clean, readable script logic.
