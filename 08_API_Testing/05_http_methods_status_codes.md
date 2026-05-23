# HTTP Methods and Status Codes

Understanding HTTP specifications is the foundation of testing any web application or API.

---

## HTTP Methods

| Method | CRUD Mapping | Idempotent? | Safe? |
|---|---|---|---|
| **GET** | Read | ✅ Yes | ✅ Yes (Does not alter state) |
| **POST** | Create | ❌ No (Multiple posts create multiple records) | ❌ No |
| **PUT** | Update (Full replace) | ✅ Yes (Repeating PUT returns same state) | ❌ No |
| **PATCH** | Update (Partial) | ❌ No (Depends on implementation) | ❌ No |
| **DELETE** | Delete | ✅ Yes (Deleting already deleted item yields same state) | ❌ No |

---

## HTTP Status Codes

### 🟢 2xx: Success
- **200 OK:** Request succeeded.
- **201 Created:** Successful POST request; resource created.
- **204 No Content:** Request processed successfully, but returns no body (common in DELETE).

### 🟡 3xx: Redirection
- **301 Moved Permanently:** Resource is now at a different URI permanently.
- **302 Found (Temporary):** Temporary redirect.

### 🔴 4xx: Client Error
- **400 Bad Request:** Request body or parameters are malformed.
- **401 Unauthorized:** Authentication missing or token invalid.
- **403 Forbidden:** Authenticated, but lacking permission/scopes.
- **404 Not Found:** URI path or resource does not exist.
- **422 Unprocessable Entity:** Validation errors (e.g., missing fields in payload).
- **429 Too Many Requests:** Rate limits exceeded.

### ⚡ 5xx: Server Error
- **500 Internal Server Error:** Generic error indicating a crash in back-end code.
- **502 Bad Gateway:** Gateway/proxy server received invalid upstream response.
- **503 Service Unavailable:** Server overloaded or down for maintenance.

---

## 📌 Key Takeaways
- **Idempotency** means running the exact same request multiple times leaves the system state identical.
- Never let API validation issues return `500 Server Error`—they should always be safely caught and return `400` or `422`.
