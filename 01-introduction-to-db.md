# Introduction to Databases

## What is a Database (DB)?

- A database is an organized collection of related data stored so it can be efficiently retrieved, updated, and managed.

## Why use a Database?

- **Reliability & durability**: data persists safely (backup/recovery support).
- **Efficient querying**: fast search/filter/sort using query engines + indexes.
- **Concurrency**: multiple users/apps can access and update data safely.
- **Integrity**: constraints help prevent invalid data (e.g., UNIQUE, NOT NULL, FK).
- **Security**: roles and permissions control access.
- **Transactions**: support for safe multi-step operations (common in RDBMS).

## What is a DBMS?

- A DBMS (Database Management System) is the software that manages a database:
  - storage, querying, indexing
  - transactions, concurrency control
  - constraints, security
  - backup/recovery
- Examples: MySQL, PostgreSQL, SQL Server, Oracle, SQLite.
- Note: tools like Workbench/DBeaver are clients, not the DBMS.

## Types of Databases

### Relational (RDBMS)

- Data is stored in tables (rows/columns) with a defined schema.
- Supports relationships between tables and joins.
- Examples: MySQL, PostgreSQL, Microsoft SQL Server.

### Non-Relational (NoSQL)

- Uses non-tabular data models (varies by database).
- Common models:
  - **Key–Value**: Redis
  - **Document**: MongoDB
  - **Wide-Column**: Cassandra
  - **Graph**: Neo4j

## Relational vs NoSQL (Key Differences)

### Relational DB (RDBMS)

- Schema-first (strict structure)
- Strong integrity constraints and joins
- Typically strong ACID transactions
- Best for: structured data + correctness (e.g., finance, orders, user accounts)

### NoSQL

- Often flexible schema (schema-on-read)
- Data model depends on type (document/key-value/graph/etc.)
- Often designed for horizontal scaling and high throughput
- Best for: large-scale, fast-changing, or high-volume data (depends on DB)

## What is SQL?

- SQL is a standardized language for working with relational databases.
- Each RDBMS supports its own SQL dialect (mostly similar, with differences).
