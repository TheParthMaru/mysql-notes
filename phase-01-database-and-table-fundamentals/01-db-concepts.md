# 01 - Database Concepts

## What is data?

Data is any kind of information that can be stored, processed, or analysed.

Data can be:

- raw
- structured
- semi-structured
- unstructured

Examples:

- customer name
- order date
- product price
- payment amount
- image file
- log file
- JSON response from an API

---

## What is a database?

A database is an organised collection of data that is stored in a way that makes it easier to access, manage, update, and retrieve.

Example:

A spreadsheet containing student names, grades, subjects, and attendance can be treated as a simple database.

A proper database system, however, provides more powerful features such as:

- querying data
- updating data
- enforcing rules
- controlling access
- managing relationships
- handling large amounts of data safely

---

## What is a DBMS?

DBMS stands for Database Management System.

A DBMS is software used to create, store, manage, retrieve, and update databases.

Examples:

- MySQL
- PostgreSQL
- Oracle Database
- Microsoft SQL Server
- MongoDB

A DBMS allows users or applications to interact with the database using commands, queries, or APIs.

---

## What is an RDBMS?

RDBMS stands for Relational Database Management System.

An RDBMS stores data in tables. These tables contain rows and columns. Tables can be related to each other using keys.

Examples:

- MySQL
- PostgreSQL
- Oracle Database
- Microsoft SQL Server

In an RDBMS:

- data is stored in tables
- each row represents a record
- each column represents an attribute/field
- primary keys uniquely identify rows
- foreign keys connect related tables

---

## SQL vs MySQL

SQL stands for Structured Query Language.

SQL is the language used to interact with relational databases.

It is used to:

- create databases and tables
- insert data
- read data
- update data
- delete data
- filter data
- join tables
- aggregate data
- manage permissions and constraints

MySQL is an RDBMS that uses SQL.

SQL is the language.
MySQL is the database management system.

Different databases may use slightly different versions or dialects of SQL.

Examples:

- MySQL SQL
- PostgreSQL SQL
- T-SQL for Microsoft SQL Server
- PL/SQL for Oracle

---

## Table, row, and column

A table stores data about one type of entity or concept.

Examples of tables:

- customers
- products
- orders
- employees
- payments

A column represents a field or property of the table.

Example columns in an employees table:

- employeeNumber
- firstName
- lastName
- email
- jobTitle

A row represents one record in the table.

Example:

In a customers table, one row represents one customer.

---

## Schema/database meaning in MySQL

In MySQL, the terms database and schema are often used almost interchangeably.

A database/schema is a collection of related database objects such as:

- tables
- views
- indexes
- stored procedures
- functions
- triggers

Example:

The `classicmodels` database contains tables such as:

- customers
- orders
- orderdetails
- products
- payments
- employees
- offices
- productlines

The word schema can also mean the structure or design of the database, including tables, columns, data types, keys, and relationships.

---

## Relational model

The relational model is the theory behind relational databases.

In the relational model:

- data is represented in tables
- tables contain rows and columns
- each row represents one record
- relationships between tables are created using keys

Example:

A customer can place many orders.

This relationship can be represented using:

- `customers.customerNumber`
- `orders.customerNumber`

Here, `orders.customerNumber` refers to the customer who placed the order.

---

## ER model

ER model stands for Entity Relationship model.

It is used to design a database before creating the actual tables.

An ER diagram usually shows:

- entities
- attributes
- relationships
- primary keys
- foreign keys

Example entities:

- Customer
- Order
- Product
- Employee

Example relationship:

- One customer can place many orders.
- One order can contain many products.
- One employee can manage many customers.

---

## Entity vs relationship

An entity is a real-world object, person, place, event, or concept that we want to store data about.

Examples:

- customer
- employee
- order
- product
- payment
- office

In database design, an entity usually becomes a table.

A relationship describes how two entities are connected.

Examples:

- A customer places orders.
- An order contains products.
- An employee manages customers.
- An office has employees.

In backend development, entity classes often represent database tables, especially when using ORM tools like JPA/Hibernate.

---

## Candidate key, primary key, and foreign key

A candidate key is any column or combination of columns that can uniquely identify a row in a table.

Example:

In a users table, both of these might be candidate keys:

- userId
- email

Both can uniquely identify a user.

A primary key is the candidate key chosen as the main unique identifier for a table.

Rules of a primary key:

- must be unique
- cannot be null
- should not change frequently

Example:

```sql
customerNumber
```

in the `customers` table.

A foreign key is a column in one table that refers to a primary key or unique key in another table.

Example:

```sql
orders.customerNumber
```

refers to:

```sql
customers.customerNumber
```

This connects each order to the customer who placed it.

---

## Nullability

A `NULL` value represents missing, unknown, or unavailable data.

Example:

If a product price is `NULL`, it means the price is not currently known or has not been provided.

`NULL` is not the same as:

- zero
- empty string
- false

A column can be made mandatory using the `NOT NULL` constraint.

---

## Constraints

Constraints are rules applied to database tables or columns to protect data quality and consistency.

Common constraints:

- `NOT NULL`
- `UNIQUE`
- `PRIMARY KEY`
- `FOREIGN KEY`
- `DEFAULT`
- `CHECK`

Examples:

`NOT NULL` means a column must have a value.

`UNIQUE` means duplicate values are not allowed.

`PRIMARY KEY` uniquely identifies each row.

`FOREIGN KEY` links one table to another table.

`DEFAULT` provides a value automatically if no value is given.

`CHECK` ensures that values follow a condition.

Example:

```sql
creditLimit DECIMAL(10,2) CHECK (creditLimit >= 0)
```

This means the credit limit cannot be negative.
