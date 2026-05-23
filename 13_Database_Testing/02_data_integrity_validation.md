# Data Integrity Validation

Data Integrity is the assurance that digital data remains accurate, consistent, and reliable over its entire lifecycle.

---

## 4 Types of Data Integrity Constraints

### 1. Entity Integrity (Primary Keys)
Ensures that each table has a **Primary Key** that is unique and **not null**.
- **QA Check:** Attempt to insert two records with identical IDs. The database must reject the second transaction with a `Unique Constraint Violation`.

### 2. Referential Integrity (Foreign Keys)
Ensures that relationships between tables remain consistent. A foreign key in Table B must point to a valid primary key in Table A.
- **QA Check:** Attempt to insert an order record for a user ID that does not exist. The database must block the write with a `Foreign Key Constraint Violation`.
- **Delete Check:** Attempt to delete a user record who has active orders. Check if the database blocks the deletion or cascades the delete successfully based on the business strategy.

### 3. Domain Integrity (Data Types)
Ensures that columns accept values only within a defined structure or set.
- **QA Check:** Attempt to save alphabetic text inside a `price` (decimal) or `age` (integer) column.

### 4. User-Defined Integrity (Business Rules)
Custom constraints set by developer specifications.
- **Example:** Ensuring the `discount` column is never greater than the `price` column.
- **QA Check:** Run boundary testing on custom database constraints.

---

## Standard Integrity Verification Queries

```sql
-- Check for orphaned orders (broken referential integrity)
SELECT * FROM orders
WHERE user_id NOT IN (SELECT id FROM users);
-- Expected result: 0 rows returned

-- Check for null constraints on required fields
SELECT * FROM users
WHERE email IS NULL OR created_at IS NULL;
-- Expected result: 0 rows returned
```

---

## 📌 Key Takeaways
- Database constraint checks prevent dirty data from corrupting reports.
- Validate **Cascading Deletes** carefully to avoid orphaned records.
- Input validation on front-end controls helps, but backend database constraints are the ultimate gatekeeper.
