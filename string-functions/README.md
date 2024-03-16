# SQL String Functions Cheatsheet

## LEFT

Extracts a specified number of characters from the left side of a string.

```sql
LEFT(string, length)
```

_string_: The string from which column to be extracted.\
_length_: The number of characters to extract from the left side of the string.

```sql
LEFT(name, 1)
```

suppose the column `name` has `sql` value, then the sql query below will produce `s` only value

## RIGHT

Similiar to `Left`, but it extracts characters from right side of the string.

```sql
RIGHT(string, length)
```
