# Data Types in PostgreSQL

## Numeric

Used to store numbers, whether whole or decimal. Examples:

- `integer` -a whole number. Range: `–2,147,483,648 to 2,147,483,647`
- `smallint` – Small range integer. Range: `–32,768 to 32,767`
- `bigint` – Big range integer. Range: `–9,223,372,036,854,775,808 to 9,223,372,036,854,775,807`
- `decimal(p,s)` – Exact numeric with precision and scale
- `real` – Approximate floating-point type. Upto 6 decimal precisons meaning, takes 6 digits before and after a decimal. eg `12.3456`
- `Double precision` - Also a floating point number. has upto 15 decimal precision.
- `serial` – Auto-increment integer

## Character Types (String)

Used to store text data. Examples:

- `char(n)` – Fixed-length string, stores exactly n characters. If the string doesn't take up (n), the remaining is filled with space characters.
- `varchar(n)` – Variable-length string with limit (n). It does not add any spaces.
- `text` – No size limit. It is meant for data upto 1 gigabyte.

## Date & Time

Store dates, times, or both. Examples:

- `date` – Stores date
- `time` – Stores time
- `timestamp` – Stores both date and time
- `interval` – Stores a span of time eg 2 or 4 hours

## Boolean

Stores logic true or false.

- `boolean` – true (true,1,on,yes), false(false,0,off,no) and null

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
