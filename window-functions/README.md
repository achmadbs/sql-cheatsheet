# SQL Window Functions Cheatsheet

## ROW_NUMBER

This funtion will generates a unique row for each row based on within its partition

```sql
SELECT
  id,
  name,
  ROW_NUMBER() AS row_number
FROM Person
```

In that case ROW_NUMBER() will assign `row_number` **(1, 2, 3)** to each row in the result set.
