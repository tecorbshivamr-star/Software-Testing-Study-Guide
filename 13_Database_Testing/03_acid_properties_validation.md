# ACID Properties Validation

Any relational database (RDBMS) processing transactions must adhere to **ACID** properties to guarantee absolute data reliability.

---

## The ACID Definition

```
    A ──→ Atomicity (All or nothing)
    C ──→ Consistency (Valid state transition)
    I ──→ Isolation (Concurrent transactions don't interfere)
    D ──→ Durability (Once saved, it is safe from crashes)
```

---

## Testing ACID Properties

### 1. Atomicity (All or Nothing)
A transaction is considered a single, indivisible unit. If *one* step of a transaction fails, the entire transaction is cancelled, and the database rolls back to its initial state.
- **Example:** transferring ₹1,000 from Account A to Account B.
  - Step 1: Deduct ₹1,000 from A. (Succeeds)
  - Step 2: Add ₹1,000 to B. (Fails due to network drop)
- **QA Check:** Force a failure during Step 2. Verify that Account A’s balance **rolls back** (₹1,000 is restored).

---

### 2. Consistency
A transaction must move the database from one valid state to another, preserving all schema rules and constraints.
- **QA Check:** Verify that invalid transactions (e.g., trying to set balance to negative when constraint is `balance >= 0`) are rejected, keeping the database consistent.

---

### 3. Isolation
Concurrently executed transactions should not interfere with one another. The execution state should look as if they ran sequentially.
- **QA Check:** Simulating race conditions. If two users click to purchase the **last remaining stock** at the exact same millisecond, verify that only one transaction succeeds, and the second transaction receives a "Sold Out" validation block.

---

### 4. Durability
Once a transaction is committed, it remains saved in database logs even if the server crashes immediately afterward.
- **QA Check:** Force a hard shutdown or server restart immediately after a massive batch transaction is committed. Upon reboot, verify that all committed records are present in the tables.

---

## 📌 Key Takeaways
- **Atomicity** is tested by injecting failures mid-transaction.
- **Isolation** is tested using concurrent load generators to check for race conditions.
- Relational databases (PostgreSQL, Oracle) offer strict ACID compliance out of the box, but business code configurations (e.g., transactional annotations) can still break them.
