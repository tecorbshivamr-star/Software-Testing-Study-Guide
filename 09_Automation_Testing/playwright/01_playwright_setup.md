# Playwright Setup Guide

## What is Playwright?
**Playwright** is a modern, fast, open-source testing framework developed by Microsoft. It is designed to enable resilient, cross-browser web testing for modern single-page apps (SPAs) built on React, Angular, and Vue.

---

## Why Playwright?
- **Resilient:** Built-in auto-waiting mechanism (no flaky tests!).
- **Fast:** Runs tests in parallel using modern browser context isolation.
- **Developer-friendly:** Excellent tooling (Codegen, Inspector, Trace Viewer).
- **Multi-language:** Supports JavaScript/TypeScript, Python, Java, and C#.

---

## Playwright Setup (Python)

### Step 1: Install Playwright Library
```bash
pip install playwright
```

### Step 2: Install System Browsers
Playwright downloads chromium, firefox, and webkit custom binaries during installation:
```bash
playwright install
```

### Step 3: Write Your First Playwright Test
Create a file named `test_playwright_basic.py`:

```python
# test_playwright_basic.py
from playwright.sync_api import sync_playwright

def test_google_title():
    # 1. Start browser session
    with sync_playwright() as p:
        browser = p.chromium.launch(headless=False)
        context = browser.new_context()
        page = context.new_page()

        # 2. Navigate to page
        page.goto("https://www.google.com")

        # 3. Assert title (No explicit waits required!)
        assert "Google" in page.title()
        print("Page title verified successfully!")

        # 4. Clean up
        browser.close()

if __name__ == "__main__":
    test_google_title()
```

---

## 📌 Key Takeaways
- Always run `playwright install` to pull browser binaries.
- Auto-waiting is standard—Playwright automatically checks that elements are visible and actionable before clicking.
- Excellent for modern headless pipeline environments.
