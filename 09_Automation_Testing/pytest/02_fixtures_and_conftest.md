# Pytest Fixtures and conftest.py

## What is a Pytest Fixture?
A **Pytest Fixture** is a function designed to perform **setup and tear-down** tasks before and after test execution. Common use cases include initializing web drivers, connecting to databases, or seeding test data.

---

## How to Write a Fixture

Use `@pytest.fixture` to declare a fixture and the `yield` statement to split setup and teardown steps.

```python
# test_db.py
import pytest

@pytest.fixture
def db_connection():
    # SETUP: Establish connection
    print("\n[Setup] Connecting to database...")
    db = {"status": "connected", "user": "QA"}
    yield db
    # TEARDOWN: Close connection
    print("\n[Teardown] Closing connection...")
    db["status"] = "disconnected"

def test_db_read(db_connection):
    # The fixture value is injected directly as a parameter!
    assert db_connection["status"] == "connected"
    print("Executing query...")
```

---

## Fixture Scopes

| Scope | Execution Frequency | Best Used For |
|---|---|---|
| **function** | Runs before and after every single test method. | Web driver refreshes, UI cleanup. |
| **class** | Runs once per test class. | Shared page allocations. |
| **module** | Runs once per Python test file. | Shared file reading. |
| **session** | Runs once per entire test run. | Global API connections, database setups. |

---

## Understanding conftest.py
Instead of copying fixtures across every test file, place them in a special file named `conftest.py` in the root of your test directory. **Pytest will automatically detect and share these fixtures across all files without importing them.**

```python
# conftest.py
import pytest
from selenium import webdriver

@pytest.fixture(scope="function")
def driver():
    driver = webdriver.Chrome()
    yield driver
    driver.quit()
```

---

## 📌 Key Takeaways
- Use **Fixtures** to prevent code duplication in setup/teardown tasks.
- Keep `conftest.py` in the root folder for global fixture sharing.
- Use `yield` to ensure database connections or web sessions are safely terminated during teardown.
