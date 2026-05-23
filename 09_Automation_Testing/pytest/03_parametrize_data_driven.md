# Pytest Parameterization (Data-Driven)

Data-driven testing is extremely powerful when you need to run the exact same testing steps against hundreds of different input combinations.

---

## Parameterizing a Single Test Case

Use `@pytest.mark.parametrize` to inject lists of inputs and expected outcomes directly into a test.

```python
# test_login.py
import pytest

@pytest.mark.parametrize("email, password, expected_status", [
    ("valid@qa.com", "Pass123", "success"),
    ("invalid@qa.com", "Pass123", "fail"),
    ("valid@qa.com", "WrongPass", "fail"),
    ("", "Pass123", "validation_error"),
])
def test_login_scenarios(email, password, expected_status):
    # Test logic
    status = attempt_login(email, password)
    assert status == expected_status

def attempt_login(email, password):
    if email == "valid@qa.com" and password == "Pass123":
        return "success"
    elif not email:
        return "validation_error"
    return "fail"
```

---

## Benefits of Parameterization
- **Cleaner Code:** No need to write 4 separate test functions.
- **Detailed Reports:** Pytest treats each parameter row as an independent, distinct test execution. If row 3 fails, rows 1, 2, and 4 still pass.

---

## 📌 Key Takeaways
- Parameterization is the built-in way to perform **Data-Driven Testing** in Pytest.
- Extremely useful for validating login variations, form inputs, mathematical calculators, and API responses.
