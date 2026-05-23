# SQL Injection Testing (SQLi)

## What is SQL Injection?
**SQL Injection (SQLi)** occurs when untrusted user input is concatenated directly inside a database query string instead of using parameterized inputs. This allows an attacker to inject raw database commands that manipulate your SQL engine.

---

## The Mechanics of SQLi

Suppose the login check query looks like this in the backend:
```sql
-- Vulnerable raw SQL string concatenation
SELECT * FROM users WHERE email = 'USER_INPUT' AND password = 'USER_INPUT';
```

If the attacker inputs `' OR '1'='1` in the email field, the query becomes:
```sql
SELECT * FROM users WHERE email = '' OR '1'='1' AND password = '';
```
Since `'1'='1'` is always true, the SQL engine bypasses all password validations completely and logs the user in as the first user in the database (usually the Admin).

---

## Standard SQLi Payload Testing Checklist

Try injecting these standard strings into form input fields and check if a database error appears:

| Payload | Expected Behavior on Vulnerable App |
|---|---|
| `'` or `"` | Triggers standard database syntax error (highly vulnerable). |
| `' OR '1'='1` | Bypasses standard check limits. |
| `' UNION SELECT null, username, password FROM users --` | Leaks complete database contents. |
| `; DROP TABLE products; --` | Destroys tables (Do not run on real databases!). |

---

## How to Prevent SQLi (The Remediation)
Never concatenate SQL inputs directly! Always use **Parameterized Queries (Prepared Statements)**:

```python
# ❌ Bad (Vulnerable to SQLi)
cursor.execute(f"SELECT * FROM users WHERE email = '{user_email}'")

# ✅ Good (Secure Prepared Statement)
cursor.execute("SELECT * FROM users WHERE email = %s", (user_email,))
```

---

## 📌 Key Takeaways
- SQLi allows attackers to steal, delete, or modify your entire corporate database.
- Always use **Prepared Statements** in backend code.
- Input validation (front-end length/character checks) is good, but backend parameterization is the only absolute security fix.
