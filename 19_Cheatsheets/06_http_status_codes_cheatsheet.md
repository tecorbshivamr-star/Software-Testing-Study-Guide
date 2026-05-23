# HTTP Status Codes Cheatsheet

Quick reference for API and Web application testing.

---

## 🟢 2xx: Success
The client's request was successfully received, understood, and accepted.

- **200 OK:** Standard response for successful HTTP requests (GET, PUT, PATCH).
- **201 Created:** The request has been fulfilled, resulting in the creation of a new resource (Standard for successful POST requests).
- **202 Accepted:** The request has been accepted for processing, but the processing has not been completed.
- **204 No Content:** The server successfully processed the request and is not returning any content (Standard for successful DELETE requests).

---

## 🟡 3xx: Redirection
Further action needs to be taken by the user agent in order to fulfill the request.

- **301 Moved Permanently:** The URL of the requested resource has been changed permanently.
- **302 Found:** The URI of requested resource has been changed temporarily.
- **304 Not Modified:** Indicates that the resource has not been modified since the version specified by the request headers (Browser Cache).

---

## 🔴 4xx: Client Error
The error seems to have been caused by the client (invalid data, bad syntax, missing credentials).

- **400 Bad Request:** The server could not understand the request due to invalid syntax or missing required parameters.
- **401 Unauthorized:** The client must authenticate itself to get the requested response (Missing/Invalid Token).
- **403 Forbidden:** The client's identity is known, but they do not have access rights to the content (Permissions issue).
- **404 Not Found:** The server can not find the requested resource or endpoint.
- **405 Method Not Allowed:** The request method is known by the server but is not supported by the target resource (e.g., sending a POST to a read-only GET endpoint).
- **409 Conflict:** Request conflicts with current state of the server (e.g., trying to register an email that already exists).
- **415 Unsupported Media Type:** The payload format is not supported (e.g., sending XML when JSON is expected).
- **422 Unprocessable Entity:** The request was well-formed but was unable to be followed due to semantic errors (e.g., validation rules failed).
- **429 Too Many Requests:** The user has sent too many requests in a given amount of time (Rate Limiting).

---

## ⚡ 5xx: Server Error
The server failed to fulfill a valid request due to an issue on the backend. **(A 500 error should generally be logged as a critical defect).**

- **500 Internal Server Error:** Generic error message, given when an unexpected condition was encountered (Backend crash/exception).
- **502 Bad Gateway:** The server, while acting as a gateway or proxy, received an invalid response from the upstream server.
- **503 Service Unavailable:** The server is not ready to handle the request (Down for maintenance or overloaded).
- **504 Gateway Timeout:** The server is acting as a gateway and cannot get a response in time from the upstream server.
