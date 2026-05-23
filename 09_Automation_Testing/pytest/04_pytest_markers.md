# Pytest Markers

## What are Markers?
**Pytest Markers** are custom labels used to group, filter, and control the execution of test cases.

---

## Built-in Markers

### 1. Skip
Skips a test unconditionally.
```python
@pytest.mark.skip(reason="Legacy feature, no longer supported")
def test_legacy_payments():
    assert False
```

### 2. SkipIf
Skips a test based on a condition (e.g., OS check).
```python
import sys
@pytest.mark.skipif(sys.platform == "win32", reason="Not applicable on Windows")
def test_mac_specific_flow():
    assert True
```

### 3. XFail
Expects the test to fail. Useful if a bug is known but not yet fixed.
```python
@pytest.mark.xfail(reason="BUG-102: Checkout integration latency")
def test_payment_timeout():
    assert False
```

---

## Custom Markers

You can define your own markers (e.g., `smoke`, `regression`) to categorize test suites.

```python
# test_login.py
import pytest

@pytest.mark.smoke
def test_login_happy_path():
    assert True

@pytest.mark.regression
def test_login_edge_cases():
    assert True
```

### Running Specific Markers
To run *only* smoke tests:
```bash
pytest -m smoke
```

To run everything *except* regression tests:
```bash
pytest -m "not regression"
```

---

## 📌 Key Takeaways
- Use markers to quickly build **Smoke** or **Regression** execution groups.
- Define custom markers in your `pytest.ini` file to prevent warning flags.
- **XFail** is perfect for keeping test suites green even with unresolved bug backlogs.
