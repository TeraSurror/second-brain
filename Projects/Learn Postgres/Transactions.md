syntax:
```postgresql
BEGIN;
-- SQL queries for the transaction --
COMMIT;
```

Transactions follow the ACID properties

Example of a transaction:
Transfer $1000 from John's account to Amy's account.

```postgresql
-- Begin transaction
BEGIN;
-- 1st query
UPDATE accounts
SET balance = balance - 1000
WHERE name = 'John';
-- 2nd Query
UPDATE accounts
SET balance = balance + 1000
WHERE name = 'Amy';

-- Save the transaction
COMMIT;
```