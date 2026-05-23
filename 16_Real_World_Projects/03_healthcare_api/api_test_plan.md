# Healthcare API Portal: Test Plan

## 1. Introduction
This Test Plan defines the approach for validating the "MedConnect FHIR API," a backend integration portal used by hospitals to securely fetch and update Electronic Health Records (EHR).

## 2. Testing Scope
- **In Scope:** All RESTful endpoints related to `/patients`, `/observations` (lab results), and `/medications`.
- **Out of Scope:** The front-end React application used by doctors (handled by a separate UI automation team).

## 3. Core Quality Requirements
Because this application handles sensitive Protected Health Information (PHI), the priorities are:
1. **HIPAA Compliance:** Data must be encrypted in transit (TLS 1.3) and at rest.
2. **Schema Validation:** Responses must strictly adhere to the HL7 FHIR (Fast Healthcare Interoperability Resources) JSON standard.
3. **Authorization:** A hospital administrator from Clinic A must be mathematically blocked from querying patient data from Clinic B.

## 4. API Testing Strategy

### A. Endpoint Functional Testing
- Verify all CRUD operations (Create, Read, Update, Delete) against the patient database.
- Assert HTTP Status Codes (200, 201, 400, 401, 403, 404).

### B. Security & Authentication Testing (OAuth 2.0)
- Verify Bearer tokens expire exactly after 15 minutes.
- Verify attempting to use an expired token returns `401 Unauthorized`.
- Verify Cross-Tenant Data Access restrictions (`403 Forbidden`).

### C. JSON Schema Validation
- Verify the API response payload strictly matches the complex FHIR schema (e.g., ensuring `patient.id` is a UUID, `patient.birthDate` is ISO-8601 formatted).

## 5. Tools & Frameworks
- **Manual Exploration:** Postman (Collections and Environments).
- **Automated Regression:** Python, Pytest, and the `requests` library.
- **CI/CD:** GitHub Actions (Running tests on every Pull Request).

## 6. Deliverables
1. Complete Postman Collection export (with environment variables).
2. Automated Pytest repository.
3. Final API Execution Report.
