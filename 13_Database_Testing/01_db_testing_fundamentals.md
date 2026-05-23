# Database Testing Fundamentals

## What is Database Testing?
**Database Testing** is a back-end testing type that validates the **schema, tables, triggers, indexes, stored procedures, and data integrity** of the database. It ensures that the application layer records data accurately without corruption.

---

## Front-End (UI) vs. Back-End (DB) Testing

| Parameter | UI Testing | Database Testing |
|---|---|---|
| **Interface** | Direct graphical interface (browser, mobile screen) | Query interfaces (SQL prompt, backend drivers) |
| **Focus** | Buttons, form fills, styling layout, workflow | Schema constraints, table structures, ACID compliance |
| **Speed** | Slower (requires rendering) | ⚡ Extremely Fast |
| **Key Threat Caught** | UI validation misses, broken buttons | Duplicate primary keys, orphaned foreign keys |

---

## 3 Layers of Database Testing

### 1. Structural Layer
Validating the structural elements of the database:
- Schema updates, Table relationships (1:many, many:many).
- Primary and Foreign key constraints.
- Trigger behavior (automatic update scripts).

### 2. Functional Layer
Verifying the data transactions:
- CRUD operations (Create, Read, Update, Delete) are saved accurately.
- Transactions rollback if an intermediate step fails.
- Stored Procedures evaluate mathematically correct logic.

### 3. Non-Functional Layer
- **Load Testing:** Running complex SQL query checks under heavy database read/write volume.
- **Security:** Verifying user access permissions and database privilege levels.

---

## 📌 Key Takeaways
- UI testing is never enough—always verify backend databases to ensure data mapping is correct.
- Stored procedures should have isolated unit checks.
- Keep test data generation isolated from real databases.
