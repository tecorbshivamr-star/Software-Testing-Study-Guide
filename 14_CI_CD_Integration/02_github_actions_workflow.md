# GitHub Actions Workflow for QA

## What is GitHub Actions?
**GitHub Actions** is a native CI/CD orchestration engine built directly inside GitHub. It allows you to build, test, and deploy code directly from repository event triggers (e.g., Pull Requests, Push).

---

## Complete Pytest Workflow Config

Create a file named `.github/workflows/pytest_runner.yml`:

```yaml
# .github/workflows/pytest_runner.yml
name: QA Test Execution Suite

# 1. Define events that trigger the pipeline
on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]
  workflow_dispatch: # Allows manual trigger from GitHub UI

# 2. Define execution jobs
jobs:
  run-tests:
    runs-on: ubuntu-latest

    steps:
    # Step 1: Clone repository code
    - name: Checkout Code
      uses: actions/checkout@v4

    # Step 2: Configure Python
    - name: Set up Python
      uses: actions/setup-python@v5
      with:
        python-version: '3.10'

    # Step 3: Cache Pip Dependencies to speed up runs
    - name: Cache Pip Dependencies
      uses: actions/cache@v4
      with:
        path: ~/.cache/pip
        key: ${{ runner.os }}-pip-${{ hashFiles('**/requirements.txt') }}

    # Step 4: Install Dependencies
    - name: Install Dependencies
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt

    # Step 5: Run Tests using Pytest
    - name: Execute Pytest Suite
      run: |
        pytest -m smoke --html=reports/smoke_report.html --self-contained-html

    # Step 6: Publish HTML Report as Build Artifact
    - name: Upload Test Report
      if: always() # Always run this step even if tests fail!
      uses: actions/upload-artifact@v4
      with:
        name: execution-report
        path: reports/smoke_report.html
```

---

## 📌 Key Takeaways
- Use **`actions/cache`** to speed up build durations.
- Set **`if: always()`** on report upload steps to ensure test logs are preserved even when test assertions fail.
- Secrets (like API keys or passwords) must be stored in **GitHub Repository Secrets** and injected as environment variables.
