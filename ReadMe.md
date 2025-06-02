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

# Inserting Data Into tables

To insert data into a table, the command **INSERT INTO** statement. 

**Syntax**
```sql
INSERT INTO cars (brand, model, year)
VALUES ('Ford', 'Mustang', 1964);
```
We can also add multiple columns and values at once

```sql
INSERT INTO cars (brand, model, year)
VALUES
  ('Volvo', 'p1800', 1968),
  ('BMW', 'M1', 1978),
  ('Toyota', 'Celica', 1975);
```

# Altering Table

 The ```ALTER TABLE ``` statement is used to add, delete, or modifiy column in an existing table. This includes droping constraints on an existing table.

## ADD Column

To add a column in a table, use the following syntax;

```sql
    ALTER TABLE table_name
    ADD column_name datatype;
```
### ADD Multiple Columns

To add multiple columns into a table, use the following syntax.
```sql
    ALTER TABLE table_name
    ADD column_name datatype,
    Add column_name datatype;
```

## Drop Column

Deleting a column in a table we use <b>```DROP COLUMN ``` </b> KEYWORD.

```sql
    ALTER TABLE table_name
    DROP COLUMN column_name;
```

## Rename Column

Renaming a column in a table we use <b>``` RENAME  TO```</b> keyword.

```sql
    ALTER TABLE table_name
    RENAME COLUMN old_name to new_name;
```

## Alter/Modify Datatype

To change data type of a column in a table.

```sql
    ALTER TABLE table_name
    ALTER COLUMN column_name TYPE INTEGER USING column_name::INTEGER;
```

# Droping Table
The <b>``` DROP TABLE```</b> statement is used to drop an existing table in a database.

**Example**
Delete cars table:

```
    DROP TABLE cars;
```


 
