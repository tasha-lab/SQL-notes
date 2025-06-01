# SQL

## Constraints

- Constraints are rules enforced on data data columns on tables. They are used to limit the type of data that can go into a table

## Examples of Constraints

### 1. Primary Key

- Uniquely identifies each record in a table.

- Record (rows), is each individual entry that exists in a table

- field (column), is a column in a table that is designed to maintain specific information about every record in the table
  <code>CREATE TABLE Persons (
  ID int NOT NULL,
  LastName varchar(255) NOT NULL,
  FirstName varchar(255),
  Age int,
  PRIMARY KEY (ID)
  );</code>

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
