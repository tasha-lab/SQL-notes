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

---

# Table constraints

1.  What are constraints and examples of constrains

    - constraints are use to rules for data in a table

    1. `PRIMARY KEY`

       - **Purpose:** Uniquely identifies each record in a table.
       - **Usage:**

       ```SQL
       CREATE TABLE users (
       user_id INT PRIMARY KElY,
       username VARCHAR(50)
       );
       ```

    2. `UNIQUE`

       - **Purpose:** Ensures that all values in a column (or a group of column are different)
       - **Usage:**

       ```SQL
         DROP TABLE IF EXISTS users;

         CREATE TABLE users (
            kuser_id INT PRIMARY KEY,
            username VARCHAR(50) UNIQUE,
            email VARCHAR(100) UNIQUE
         );
       ```

    3. `NOT NULL`

       - **Purpose:** Ensures that a column cannot have a NULL value
       - **Usage:**

       ```SQL
        DROP TABLE IF EXISTS users;

        CREATE TABLE users (
          user_id INT PRIMARY KEY,
          username VARCHAR(50) UNIQUE NOT NULL, -- username cannot be NULL
          email VARCHAR(100) UNIQUE,
          first_name VARCHAR(50) NOT NULL -- first_name cannot be NULL
        );
       ```

    4. `DEFAULT`

       - **Purpose:** Assigns a default value if no value is provided during insertion.
       - **Usage:**

       ```SQL
        CREATE TABLE tasks (
           task_id INT PRIMARY KEY,
           description TEXT NOT NULL,
           status VARCHAR(20) DEFAULT 'pending' -- Default status is 'pending'
        );
       ```

    5. `CHECK`

       - **Purpose:** Enforces a specific condition that values in a column must meet.
       - **Usage:**

       ```SQL
        CREATE TABLE students (
          student_id INT PRIMARY KEY,
          name VARCHAR(100),
          age INT CHECK (age >= 5 AND age <= 18) -- Age must be between 5 and 18
        );
       ```

    6. `FOREIGN KEY`

       - **Purpose:** Links two tables together, ensuring referential integrity (values in this column must exist in the referenced primary key column of another table)
       - **Usage:**

       ```SQL
          -- Parent table
          CREATE TABLE categories (
              category_id INT PRIMARY KEY,
              category_name VARCHAR(50)
          );

          -- Child table referencing categories
          CREATE TABLE books (
              book_id INT PRIMARY KEY,
              title VARCHAR(255),
              category_id INT,
              CONSTRAINT fk_category -- Name for the foreign key constraint
              FOREIGN KEY (category_id)
              REFERENCES categories (category_id)
              ON DELETE CASCADE -- If a category is deleted, related books are also deleted
          );
       ```
