# Healthcare API: Postman Collection Structure

To ensure the team can manually explore and debug the API efficiently, we maintain a highly organized Postman Collection.

---

## Environment Variables
Instead of hardcoding URLs or tokens, the collection relies on an Environment file (`qa-env.json`):
- `{{baseUrl}}`: `https://qa.api.medconnect.com/v1`
- `{{clinicA_token}}`: `eyJhbG...` (Generated dynamically via Pre-request script)
- `{{clinicB_token}}`: `eyJhbG...`
- `{{test_patient_id}}`: `uuid-1234` (Extracted dynamically after POST)

---

## Collection Folder Structure

```
MedConnect FHIR API (Collection)
│
├── 1. Authentication
│   ├── POST /auth/token (Generates and saves token to {{clinicA_token}})
│
├── 2. Patient Management (CRUD)
│   ├── POST /patients (Creates patient, saves ID to {{test_patient_id}})
│   ├── GET /patients/{{test_patient_id}} (Retrieves patient, asserts 200 OK)
│   ├── PUT /patients/{{test_patient_id}} (Updates patient phone number)
│   └── DELETE /patients/{{test_patient_id}} (Soft deletes patient)
│
├── 3. Observations (Lab Results)
│   ├── GET /observations?patient={{test_patient_id}}
│   └── POST /observations
│
└── 4. Security & Negative Scenarios
    ├── GET /patients/{{test_patient_id}} (Without Auth Header -> Expect 401)
    ├── GET /patients/{{test_patient_id}} (Using {{clinicB_token}} -> Expect 403)
    └── POST /patients (With invalid JSON payload -> Expect 400)
```

---

## Example Tests Script (Postman)

On the `GET /patients/{{test_patient_id}}` request, the following JavaScript assertions are written in the "Tests" tab:

```javascript
// 1. Assert Status Code
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// 2. Assert Response Time
pm.test("Response time is less than 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
});

// 3. Schema Validation
var schema = {
    "type": "object",
    "properties": {
        "resourceType": { "type": "string", "enum": ["Patient"] },
        "id": { "type": "string" },
        "active": { "type": "boolean" },
        "name": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": { "family": { "type": "string" }, "given": { "type": "array" } }
            }
        }
    },
    "required": ["resourceType", "id", "name"]
};

pm.test("Response matches FHIR schema", function () {
    pm.response.to.have.jsonSchema(schema);
});
```
