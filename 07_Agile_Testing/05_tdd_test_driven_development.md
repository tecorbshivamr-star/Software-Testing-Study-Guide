# Test-Driven Development (TDD)

## What is TDD?
**Test-Driven Development (TDD)** is a software development process where you **write the test cases first**, before writing the actual production code.

> *"Tests dictate how code is written, rather than code dictates how tests are written."*

---

## The Red-Green-Refactor Loop

```
      ┌─────────────────────────┐
      │   Write a Failing Test  │ (RED)
      └────────────┬────────────┘
                   │
                   ▼
      ┌─────────────────────────┐
      │  Write Minimal Code to  │
      │       make it Pass      │ (GREEN)
      └────────────┬────────────┘
                   │
                   ▼
      ┌─────────────────────────┐
      │ Refactor / Clean Code  │ (REFACTOR)
      └────────────┬────────────┘
                   │
                   └────────────────── Loop back
```

1. **RED:** Write a test that fails (since the code does not exist yet).
2. **GREEN:** Write the absolute minimal production code to make the test pass.
3. **REFACTOR:** Clean up the code (remove duplication, improve naming) while ensuring the test stays green.

---

## Simple TDD Example in Python

### Step 1: Write a Failing Test (RED)
```python
# test_string_util.py
import pytest
from string_util import reverse_string

def test_reverse_string():
    assert reverse_string("hello") == "olleh"  # Fails! Module doesn't exist
```

### Step 2: Write Minimal Code to Pass (GREEN)
```python
# string_util.py
def reverse_string(text: str) -> str:
    return text[::-1]  # Simple implementation
```
*Run tests -> Passes! (GREEN)*

### Step 3: Refactor (REFACTOR)
Optimize imports, typing, or handle edge cases (e.g., empty string inputs) while keeping the test suite green.

---

## 📌 Key Takeaways
- TDD leads to **high code coverage** by default.
- Prevents bloat—you only write code that is verified by a test.
- TDD is predominantly done by **Developers** at the unit level.
