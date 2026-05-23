# Banking Application: Data Integrity Validation Queries

In a banking context, backend database testing is as important as UI testing. Below are automated SQL queries used to validate the integrity of the ledger.

---

### 1. Verify Atomicity (Double-Entry Accounting)
In double-entry accounting, every debit must have a corresponding credit. The total sum of all transactions in the ledger must always equal zero.

```sql
-- QA Validation Query: Verify the ledger is balanced.
-- Expected Result: 0.00
SELECT SUM(amount) AS net_balance
FROM ledger_transactions;
```

### 2. Verify Account Balance Integrity
The cached "current balance" on the `accounts` table must exactly match the sum of all historical transactions for that account in the `ledger`.

```sql
-- QA Validation Query: Find accounts where the cached balance does NOT match the transaction history.
-- Expected Result: 0 rows returned
SELECT a.account_id, a.current_balance, SUM(t.amount) AS calculated_balance
FROM accounts a
JOIN ledger_transactions t ON a.account_id = t.account_id
GROUP BY a.account_id, a.current_balance
HAVING a.current_balance != SUM(t.amount);
```

### 3. Verify Negative Balance Constraints
Retail checking accounts should not be allowed to drop below $0.00 unless an overdraft protection flag is explicitly enabled.

```sql
-- QA Validation Query: Find retail accounts with negative balances that do not have overdraft enabled.
-- Expected Result: 0 rows returned
SELECT account_id, current_balance
FROM accounts
WHERE account_type = 'Retail_Checking' 
  AND current_balance < 0 
  AND overdraft_enabled = FALSE;
```

### 4. Verify Orphaned Transactions (Referential Integrity)
A transaction cannot exist if the parent account has been deleted. (The application should soft-delete accounts, not hard-delete).

```sql
-- QA Validation Query: Find transactions pointing to non-existent accounts.
-- Expected Result: 0 rows returned
SELECT transaction_id, account_id
FROM ledger_transactions
WHERE account_id NOT IN (SELECT account_id FROM accounts);
```
