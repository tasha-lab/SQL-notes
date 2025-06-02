# Data Types in PostgreSQL

## Numeric

Used to store numbers, whether whole or decimal. Examples:

- `integer` -a whole number
- `smallint` – Small range integer
- `bigint` – Big range integer
- `decimal(p,s)` – Exact numeric with precision and scale
- `real` – Approximate floating-point number
- `serial` – Auto-increment integer

## Character Types (String)

Used to store text data. Examples:

- `char(n)` – Fixed-length string, stores exactly n characters
- `varchar(n)` – Variable-length string with limit n
- `text` – No size limit

## Date & Time

Store dates, times, or both. Examples:

- `date` – Stores date
- `time` – Stores time
- `timestamp` – Stores both date and time
- `interval` – Stores a span of time

## Boolean

Stores logic true or false.

- `boolean` – true or false

## Monetary

Store money values.

- `money` – Currency type with locale formatting
- `numeric(p,s)` – eg, `(10, 2)` for 10 total digits with 2 decimal places

---

# Creating Tables without Constraints

To create a new table, use `CREATE TABLE`.

**Syntax:**

```sql
CREATE TABLE table_name (
    column_name datatype,
    column_name datatype
);
```
