# SQL Window Functions Cheatsheet

## ROW_NUMBER

This funtion will generates a unique row for each row based on within its partition

```sql
SELECT
  id,
  person_name,
  ROW_NUMBER() AS row_number
FROM Person
```

In that case ROW_NUMBER() will assign `row_number` **(1, 2, 3)** to each row in the result set.

## OVER

This is a clause used in conjunction with window function to define the partitioning and ordering of the rows for the window function to operate on. It specifies the window over which the function should be computed. `OVER()` clause can include `PARTITION BY` to partition the rows data into groups and `ORDER BY` to specify the order within each partition.

Let's enchance our previous `ROW_NUMBER` query with `OVER`

```sql
SELECT
  id,
  person_name,
  ROW_NUMBER() OVER (PARTITION BY person_name ORDER BY id) AS row_number
FROM Person
```

In the example query above:

- `ROW_NUMBER()`: This function will generate unique number for each rows within its partition.
- `OVER (PARTITION BY person_name ORDER BY id)`: This clause will specifies that each rows should be partitioned by _person_name_ column, meaning the row number will restart for each unique person_name. Within each partition, the rows ordered by the _id_ column. With that said the rows number will be ordered by their ID.
