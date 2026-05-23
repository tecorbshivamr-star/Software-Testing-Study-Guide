# GraphQL Testing

## What is GraphQL?
**GraphQL** is a query language and server-side runtime for APIs created by Facebook. Unlike REST, which has separate endpoints for each resource, GraphQL exposes a **single endpoint** (usually `/graphql`) where clients can request the exact data they need.

---

## REST vs GraphQL

```
REST (Multiple requests to get data):
GET /api/users/123  ──→ returns user details
GET /api/users/123/orders  ──→ returns orders list

GraphQL (One request to get exactly what you want):
POST /graphql  ──→ with query payload specifying user name & order IDs
```

---

## Core Concepts

### 1. Queries (Read)
Used to retrieve data from the server.
```graphql
query {
  user(id: "123") {
    name
    email
  }
}
```

### 2. Mutations (Write)
Used to create, update, or delete data.
```graphql
mutation {
  createUser(email: "qa@test.com", name: "QA User") {
    id
    name
  }
}
```

---

## How to Test GraphQL APIs
1. **Send POST requests:** GraphQL queries are sent inside the body of an HTTP POST request.
2. **Schema Verification:** Use **Introspection** to query the server for its schema and verify types.
3. **Over-fetching & Under-fetching:** Validate that the server returns *only* the requested fields, and nothing more.

---

## 📌 Key Takeaways
- Exposes a single endpoint (`POST /graphql`).
- Extremely efficient for mobile clients since it eliminates over-fetching of data.
- Testing focus is on verifying correct query resolution and schema compliance.
