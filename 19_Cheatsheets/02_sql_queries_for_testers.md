# SQL Queries for Testers

> QA engineers use SQL to verify data after UI actions. No dev skills needed — just the essentials.

---

## Why QA Engineers Need SQL

- Verify data was **saved correctly** after form submission
- Check that **deleted records** are actually removed
- Validate **calculations** (totals, discounts, balances)
- **Seed test data** before test runs
- Debug failures by checking the database directly

---

## Basic SELECT Queries

```sql
-- Get all records from a table
SELECT * FROM users;

-- Get specific columns
SELECT id, email, name FROM users;

-- Filter with WHERE
SELECT * FROM users WHERE email = 'testuser@qa.com';

-- Multiple conditions
SELECT * FROM users WHERE status = 'active' AND age >= 18;

-- OR condition
SELECT * FROM users WHERE email = 'a@test.com' OR email = 'b@test.com';

-- LIKE (partial match)
SELECT * FROM users WHERE email LIKE '%@gmail.com';
SELECT * FROM users WHERE name LIKE 'Shiv%';  -- starts with Shiv

-- NULL checks
SELECT * FROM users WHERE phone IS NULL;
SELECT * FROM users WHERE phone IS NOT NULL;

-- Sort results
SELECT * FROM orders ORDER BY created_at DESC;
SELECT * FROM products ORDER BY price ASC;

-- Limit results
SELECT * FROM orders ORDER BY created_at DESC LIMIT 10;
```

---

## Aggregate Functions

```sql
-- Count records
SELECT COUNT(*) FROM users;
SELECT COUNT(*) FROM users WHERE status = 'active';

-- Sum, Average, Min, Max
SELECT SUM(amount) FROM orders WHERE user_id = 123;
SELECT AVG(price) FROM products WHERE category = 'electronics';
SELECT MIN(price), MAX(price) FROM products;

-- Group By (count per category)
SELECT status, COUNT(*) as total
FROM users
GROUP BY status;

-- Group By with Having (filter groups)
SELECT user_id, COUNT(*) as order_count
FROM orders
GROUP BY user_id
HAVING COUNT(*) > 5;
```

---

## JOIN Queries (Most Useful for QA)

```sql
-- INNER JOIN: get matching records from both tables
SELECT u.name, u.email, o.id as order_id, o.total
FROM users u
INNER JOIN orders o ON u.id = o.user_id
WHERE u.email = 'testuser@qa.com';

-- LEFT JOIN: all users even if no orders
SELECT u.name, o.id as order_id
FROM users u
LEFT JOIN orders o ON u.id = o.user_id;
```

---

## Common QA Verification Queries

```sql
-- Verify user was created after registration
SELECT * FROM users
WHERE email = 'newuser@test.com'
AND created_at >= NOW() - INTERVAL '5 minutes';

-- Verify order total is correct
SELECT id, SUM(price * quantity) as calculated_total, total
FROM orders o
JOIN order_items oi ON o.id = oi.order_id
WHERE o.id = 12345
GROUP BY o.id, o.total;

-- Check if password is hashed (not plain text)
SELECT email, password FROM users WHERE email = 'test@qa.com';
-- Expected: password should be a bcrypt hash, NOT plain text

-- Verify deleted record is gone (soft delete check)
SELECT * FROM users WHERE email = 'deleted@test.com' AND deleted_at IS NULL;

-- Count failed login attempts
SELECT email, COUNT(*) as attempts
FROM login_attempts
WHERE email = 'test@qa.com'
AND created_at >= NOW() - INTERVAL '1 hour'
GROUP BY email;

-- Verify payment record
SELECT * FROM payments
WHERE order_id = 999
AND status = 'completed'
AND amount = 1500.00;
```

---

## INSERT / UPDATE for Test Data Setup

```sql
-- Create a test user
INSERT INTO users (email, name, password, status, created_at)
VALUES ('qatest@test.com', 'QA Test User', 'hashed_password', 'active', NOW());

-- Update user status for testing
UPDATE users SET status = 'locked' WHERE email = 'locktest@qa.com';

-- Reset failed attempts counter
UPDATE login_attempts SET count = 0 WHERE email = 'locktest@qa.com';
```

---

## DELETE for Test Data Cleanup

```sql
-- Clean up after tests
DELETE FROM users WHERE email LIKE '%@qatest.com';

-- Delete test orders
DELETE FROM orders WHERE user_id IN (
    SELECT id FROM users WHERE email LIKE '%@qatest.com'
);
```

---

## Useful Date Queries

```sql
-- Records created today
SELECT * FROM orders WHERE DATE(created_at) = CURDATE();

-- Records from last 7 days
SELECT * FROM orders WHERE created_at >= NOW() - INTERVAL 7 DAY;

-- Records between two dates
SELECT * FROM orders
WHERE created_at BETWEEN '2026-05-01' AND '2026-05-31';
```

---

## PostgreSQL vs MySQL Differences

| Feature | MySQL | PostgreSQL |
|---------|-------|-----------|
| Current timestamp | `NOW()` | `NOW()` |
| Date diff | `DATEDIFF(d1, d2)` | `d1 - d2` |
| String concat | `CONCAT(a, b)` | `a \|\| b` |
| Auto increment | `AUTO_INCREMENT` | `SERIAL` |
| Case sensitive | No (by default) | Yes |

---

## 📌 Key Takeaways

- SQL is **essential for QA** — use it to verify data, not just trust the UI
- Always use `WHERE` with `DELETE/UPDATE` — never run without a filter!
- Use `LIMIT 10` when exploring — avoid loading millions of rows
- Learn `JOIN` — most real-world verifications need data from multiple tables

---

*Shivam Rai | Software Testing MasterGuide*
