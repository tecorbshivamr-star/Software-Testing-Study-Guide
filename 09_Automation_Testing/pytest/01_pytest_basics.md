# Pytest Basics

## What is Pytest?
**Pytest** is a robust, open-source testing framework for Python. It allows you to write simple, readable unit, integration, and functional test scripts with minimal boilerplate.

---

## 4 Core Rules of Pytest
To ensure Pytest automatically discovers and runs your test scripts:
1. **File Names:** Must start with `test_` or end with `_test.py` (e.g., `test_login.py`).
2. **Class Names:** Must start with `Test` (e.g., `Class TestLogin:`). No `__init__` constructor allowed.
3. **Function Names:** Must start with `test_` (e.g., `def test_valid_user():`).
4. **Assertions:** Uses standard Python `assert` statements rather than complex API calls (e.g., `self.assertEqual`).

---

## Writing a Simple Pytest Test

```python
# test_math.py
def add(a, b):
    return a + b

def test_add_positive():
    assert add(2, 3) == 5

def test_add_negative():
    assert add(-1, -1) == -2
```

To run the tests:
```bash
pytest test_math.py
```

---

## 📌 Key Takeaways
- Simple, readable tests with raw Python `assert` statements.
- Auto-discovery of files and folders saves management time.
- Highly extensible via a massive plugin ecosystem (e.g., `pytest-html`, `pytest-xdist`).
