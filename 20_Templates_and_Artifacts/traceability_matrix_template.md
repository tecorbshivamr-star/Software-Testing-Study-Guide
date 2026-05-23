# Requirements Traceability Matrix (RTM) Template

*The RTM is a critical document used to map business requirements to test cases. It proves to stakeholders that 100% of the requested features have been tested.*

---

## Traceability Matrix Table

| Req ID | Requirement Description | Module | Test Case ID | Test Execution Status | Defect ID (If Failed) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **REQ-001** | User must be able to log in with an email and password. | Auth | `TC_LGN_01`<br>`TC_LGN_02` | ✅ Passed<br>✅ Passed | N/A |
| **REQ-002** | User account locks after 5 failed login attempts. | Auth | `TC_LGN_05` | ❌ Failed | `BUG-104` |
| **REQ-003** | User can add a physical product to the shopping cart. | Cart | `TC_CRT_01` | ✅ Passed | N/A |
| **REQ-004** | Cart must calculate a 10% discount if code 'SUMMER' is applied. | Cart | `TC_CRT_05`<br>`TC_CRT_06` | ❌ Failed<br>✅ Passed | `BUG-210` |
| **REQ-005** | Checkout page must accept Visa and Mastercard payments. | Checkout| `TC_CHK_01`<br>`TC_CHK_02` | ⏳ Pending | N/A |

---

## 📌 RTM Analysis Metrics

At the end of a sprint, use the RTM to calculate your coverage:

- **Total Requirements:** 5
- **Requirements with Test Cases (Coverage):** 5 (100% coverage)
- **Total Test Cases Executed:** 6
- **Test Cases Passed:** 4
- **Test Cases Failed:** 2
- **Pass Rate:** 66%

*Conclusion: Requirements REQ-002 and REQ-004 are currently broken and blocking release.*
