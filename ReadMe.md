# SQL

## Constraints

- Constraints are rules enforced on data data columns on tables. They are used to limit the type of data that can go into a table

## Examples of Constraints

### 1. Primary Key

- Uniquely identifies each record in a table.

- Record (rows), is each individual entry that exists in a table

- field (column), is a column in a table that is designed to maintain specific information about every record in the table
  <code>

  CREATE TABLE Persons (

  ID int NOT NULL,

  LastName varchar(255) NOT NULL,

  FirstName varchar(255),

  Age int,

  PRIMARY KEY (ID)

  );

  </code>

### 2. Foreign Key

A foreign key in one table points to a primary key in another table.

The table with the foreign key is called the child table, and the table with the primary key is called the referenced or parent table.

Persons Table
|PersonID | LastName| FirstName |Age|
|---------|---------|--------------|---|
|1| Hansen| Ola |30|
|2| Svendson| Tova |23|
|3| Pettersen| Kari |20|

Orders Table
|OrderID |OrderNumber|PersonID|
|------------|------------|---------|
|1 | 77895 |3|
|2 | 44678 |3|
|3 | 22456 |2|
|4 | 24562 |1|

### 3. Not null

- Ensures a column cannot have a null value. It enforces a field to always have a value
  <code>
  CREATE TABLE Persons (

      ID int NOT NULL,

      LastName varchar(255) NOT NULL,

      FirstName varchar(255) NOT NULL,

      Age int
        );

</code>

### 4. Unique Constraint

Unique constraint ensures all values in a column are different

A <code> PRIMARY KEY</code> constraint automatically has a UNIQUE constraint.

However, you can have many <code> UNIQUE</code> constraints per table, but only one <code>PRIMARY KEY</code> constraint per table.

<code>

CREATE TABLE Persons (
ID int NOT NULL,

    LastName varchar(255) NOT NULL,

    FirstName varchar(255),

    Age int,

    UNIQUE (ID)

);

</code>

### 5. Check Contraints

Ensures all values in a column satisfy certain conditions

The following SQL creates a CHECK constraint on the "Age" column when the "Persons" table is created. the check ensures the age is above or equal to 18.

<code>

    CREATE TABLE Persons (

    ID int NOT NULL,

    LastName varchar(255) NOT NULL,

    FirstName varchar(255),

    Age int CHECK (Age>=18)

);

</code>

### 6. Default Constraint

Used to insert a default value in a column if not specified

The following SQL sets a DEFAULT value for the "City" column when the "Persons" table is created:
<code>

    CREATE TABLE Persons (

    ID int NOT NULL,

    LastName varchar(255) NOT NULL,

    FirstName varchar(255),

    Age int,

    City varchar(255) DEFAULT 'Sandnes'

);

</code>

### 7. Index Constraint

Makes creating and retrieving data to be fast

Creates an index on a table. Duplicate values are allowed:
<code>

CREATE INDEX index_name

ON table_name (column1, column2, ...);
