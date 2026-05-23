# Healthcare API: Automation Framework Design

For robust, CI/CD-integrated testing, we bypass Postman and use a pure Python framework.

---

## 1. Technology Stack
- **Language:** Python 3.10
- **Test Runner:** Pytest
- **HTTP Client:** `requests`
- **Schema Validation:** `jsonschema` library
- **Reporting:** `pytest-html`

---

## 2. Directory Structure

```text
healthcare_api_automation/
│
├── endpoints/
│   ├── base_api.py       # Wrapper for requests, logging, and error handling
│   ├── auth_api.py       # Methods to hit /auth/token
│   └── patient_api.py    # Methods to hit /patients
│
├── tests/
│   ├── conftest.py       # Global fixtures (e.g., token generation)
│   ├── test_auth.py      # Tests for token expiry, invalid scopes
│   ├── test_patients.py  # CRUD flow tests
│   └── test_security.py  # Cross-tenant data leak tests
│
├── schemas/
│   └── fhir_patient.json # JSON schema definition files
│
├── data/
│   └── test_data.json    # Payloads for POST/PUT requests
│
├── pytest.ini            # Pytest config and markers
└── requirements.txt      # pip dependencies
```

---

## 3. Code Example: Pytest Fixture & Test

### `conftest.py`
```python
import pytest
from endpoints.auth_api import AuthAPI

@pytest.fixture(scope="session")
def valid_token():
    # Setup: Generate a token once for the entire test session
    response = AuthAPI().get_token("clinicA_client_id", "secret")
    yield response.json().get("access_token")
    # Teardown: Revoke token if necessary
```

### `test_patients.py`
```python
import pytest
from endpoints.patient_api import PatientAPI

def test_get_patient_returns_200(valid_token):
    # Arrange
    api = PatientAPI(token=valid_token)
    patient_id = "uuid-1234-5678"

    # Act
    response = api.get_patient(patient_id)

    # Assert
    assert response.status_code == 200, f"Expected 200, got {response.status_code}"
    
    data = response.json()
    assert data["resourceType"] == "Patient"
    assert data["id"] == patient_id
```

### `test_security.py`
```python
import pytest
from endpoints.patient_api import PatientAPI

def test_cross_tenant_access_blocked(clinicB_token):
    # Arrange
    api = PatientAPI(token=clinicB_token)
    patient_id_belonging_to_clinic_A = "uuid-1234-5678"

    # Act
    response = api.get_patient(patient_id_belonging_to_clinic_A)

    # Assert (Strict Security Check)
    assert response.status_code == 403, "CRITICAL: Data Leak! Cross-tenant access allowed!"
    assert "Forbidden" in response.json().get("error")
```
