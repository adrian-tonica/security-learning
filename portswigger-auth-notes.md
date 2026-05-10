# SQL Injection – Hidden Data Retrieval

## Objective
Exploit SQL injection in a WHERE clause to retrieve hidden data.

## Vulnerability
User input was inserted directly into a SQL query without sanitization.

Original query concept:

```sql
SELECT * FROM products
WHERE category='Gifts'
AND released=1
```

## Payload Used

```sql
' OR 1=1--
```

## Why it worked
- `OR 1=1` evaluates to true
- `--` comments out the remainder
- query returns all rows, including hidden items

## Mitigation
- parameterized queries
- prepared statements
- input sanitization
