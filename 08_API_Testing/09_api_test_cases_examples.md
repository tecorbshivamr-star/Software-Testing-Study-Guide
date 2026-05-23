# API Test Cases Examples

This guide details professional test cases for standard API endpoints using an E-Commerce system.

---

## Module 1: User Login (`POST /api/v1/auth/login`)

**System Specs:**
- Request body requires `email` (string, must exist, correct format) and `password` (string).
- Returns JWT token on success.

| Test Case ID | Test Scenario | Request Payload | Expected Status | Expected Body Assertions |
|---|---|---|---|---|
| **TC_API_LGN_01** | Login with valid credentials (Happy Path) | `{"email": "user@qa.com", "password": "Pass@1234"}` | **200 OK** | - `token` field exists & is not null.<br>- `user.email` equals `user@qa.com`. |
| **TC_API_LGN_02** | Login with incorrect password | `{"email": "user@qa.com", "password": "WrongPassword"}` | **401 Unauthorized** | - `error` field contains "Invalid credentials". |
| **TC_API_LGN_03** | Login with missing required email | `{"password": "Pass@1234"}` | **400 Bad Request** | - `error` mentions "email is required". |
| **TC_API_LGN_04** | Login with invalid email format | `{"email": "bademailformat.com", "password": "Pass"}` | **400 Bad Request** | - `error` mentions "invalid email format". |

---

## Module 2: Add to Cart (`POST /api/v1/cart/add`)

**System Specs:**
- Requires authentication (Bearer token).
- Payload requires `product_id` (integer) and `quantity` (integer, min 1).

| Test Case ID | Test Scenario | Headers & Payload | Expected Status | Expected Assertions |
|---|---|---|---|---|
| **TC_API_CRT_01** | Add product successfully (Auth) | - Headers: `Authorization: Bearer <valid_token>`<br>- Body: `{"product_id": 99, "quantity": 2}` | **200 OK** | - `cart.items[0].product_id` = 99.<br>- `cart.total_items` = 2. |
| **TC_API_CRT_02** | Attempt action without Auth token | - Headers: None<br>- Body: `{"product_id": 99, "quantity": 2}` | **401 Unauthorized** | - Request blocked.<br>- `error` mentions "Authentication token required". |
| **TC_API_CRT_03** | Add product with negative quantity | - Headers: `Bearer <valid_token>`<br>- Body: `{"product_id": 99, "quantity": -5}` | **400 Bad Request** | - Request blocked.<br>- `error` mentions "quantity must be greater than 0". |

---

## 📌 Key Takeaways
- Every test case must have a defined **Expected Status Code**.
- Assert both the top-level **JSON keys** and the specific nested **field values**.
- Check database changes (e.g., query DB to verify the product count is indeed 2).
