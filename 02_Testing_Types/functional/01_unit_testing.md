# Unit Testing

## What is Unit Testing?
**Unit Testing** is the first level of dynamic testing. It involves testing the smallest testable part (unit) of an application—typically a single function, method, class, or module—in isolation from the rest of the system.

> *"Test the pieces in absolute isolation to make sure the building blocks are strong."*

---

## Key Characteristics
- **Done By:** Developers.
- **When:** During the coding phase (Implementation).
- **Isolation:** Uses mocks, stubs, and fakes to isolate the unit from databases, network APIs, or other modules.
- **Execution Speed:** Extremely fast (runs in milliseconds).
- **Coverage Type:** White-box testing (requires code visibility).

---

## Unit Testing Frameworks

| Language | Frameworks |
|---|---|
| **Python** | `unittest`, `pytest` |
| **Java** | `JUnit`, `TestNG` |
| **JavaScript** | `Jest`, `Mocha`, `Jasmine` |
| **C#** | `NUnit`, `xUnit` |

---

## Simple Python Unit Test Example

```python
# calculator.py
def add(a, b):
    return a + b

# test_calculator.py
import unittest
from calculator import add

class TestCalculator(unittest.TestCase):
    def test_add_positive_numbers(self):
        self.assertEqual(add(2, 3), 5)

    def test_add_negative_numbers(self):
        self.assertEqual(add(-1, -1), -2)

if __name__ == '__main__':
    unittest.main()
```

---

## 📌 Key Takeaways
- Catches bugs early when they are easiest and cheapest to fix.
- Simplifies debugging because failures pinpoint exact code lines.
- Acts as living documentation for developers.
