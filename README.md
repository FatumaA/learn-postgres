![PostgreSQL-Logo 1](https://github.com/user-attachments/assets/6e1cf5b4-e6f2-47ff-9c3f-621aac45a11b)

## Table of Contents

### 1. [Introduction to PostgreSQL](#1-introduction-to-postgresql)

1.1. [What is PostgreSQL?](#11-what-is-postgresql)  
1.2. [Installing PostgreSQL (Windows, Mac, Linux)](#12-installing-postgresql-windows-mac-linux)  
1.3. [PostgreSQL vs Other Databases](#13-postgresql-vs-other-databases)  
1.4. [First Steps: Connecting to PostgreSQL](#14-how-to-connect-to-postgresql)  
 1.4.1. [Using `psql` (PostgreSQL Command-Line Tool)](#141-using-psql-postgresql-command-line-tool)  
 1.4.2. [Connecting via GUI (pgAdmin, DBeaver)](#142-connecting-via-gui-pgadmin-dbeaver)

### 2. [Basic PostgreSQL Commands](#2-basic-postgresql-commands)

2.1. [Creating a Database](#21-creating-a-database)  
2.2. [Creating and Dropping Tables](#22-creating-and-dropping-tables)  
2.3. [Data Types in PostgreSQL](#23-data-types-in-postgresql)  
2.4. [Inserting, Updating, and Deleting Data](#24-inserting-updating-and-deleting-data)  
2.5. [Basic Queries: `SELECT`, `WHERE`, `ORDER BY`](#25-basic-queries-select-where-order-by)  
2.6. [Filtering Results: `LIMIT`, `OFFSET`](#26-filtering-results-limit-offset)  
2.7. [Basic Joins: `INNER JOIN`, `LEFT JOIN`](#27-basic-joins-inner-join-left-join)  
2.8. [Aliases for Columns and Tables](#28-aliases-for-columns-and-tables)  
2.9. [Exporting and Importing Data (`COPY`, `pg_dump`)](#29-exporting-and-importing-data-copy-pg_dump)

### 3. [Intermediate PostgreSQL Concepts](#3-intermediate-postgresql-concepts)

3.1. [Constraints](#31-constraints)  
 3.1.1. [Primary Key, Foreign Key, Unique Constraints](#311-primary-key-foreign-key-unique-constraints)  
 3.1.2. [Check Constraints](#312-check-constraints)  
3.2. [Indexes](#32-indexes)  
 3.2.1. [Creating Indexes](#321-creating-indexes)  
 3.2.2. [B-tree vs GIN vs GiST Indexes](#322-b-tree-vs-gin-vs-gist-indexes)  
 3.2.3. [Partial Indexes](#323-partial-indexes)  
3.3. [Views](#33-views)  
 3.3.1. [Creating and Using Views](#331-creating-and-using-views)  
 3.3.2. [Materialized Views](#332-materialized-views)  
3.4. [Transactions](#34-transactions)  
 3.4.1. [ACID Properties](#341-acid-properties)  
 3.4.2. [Using `BEGIN`, `COMMIT`, `ROLLBACK`](#342-using-begin-commit-rollback)  
3.5. [Functions and Stored Procedures](#35-functions-and-stored-procedures)  
 3.5.1. [Built-in Functions (Math, String, Date)](#351-built-in-functions-math-string-date)  
 3.5.2. [Writing Custom Functions (PL/pgSQL)](#352-writing-custom-functions-plpgsql)  
 3.5.3. [Working with Stored Procedures](#353-working-with-stored-procedures)  
3.6. [Triggers](#36-triggers)  
 3.6.1. [Creating Triggers](#361-creating-triggers)  
 3.6.2. [Common Use Cases](#362-common-use-cases)

### 4. [Advanced PostgreSQL Topics](#4-advanced-postgresql-topics)

4.1. [Advanced Queries](#41-advanced-queries)  
 4.1.1. [Subqueries](#411-subqueries)  
 4.1.2. [Common Table Expressions (CTEs)](#412-common-table-expressions-ctes)  
 4.1.3. [Window Functions](#413-window-functions)  
 4.1.4. [Recursive Queries](#414-recursive-queries)  
4.2. [Performance Tuning](#42-performance-tuning)  
 4.2.1. [Query Optimization](#421-query-optimization)  
 4.2.2. [Analyzing Queries (`EXPLAIN`, `ANALYZE`)](#422-analyzing-queries-explain-analyze)  
 4.2.3. [Vacuuming and Autovacuum](#423-vacuuming-and-autovacuum)  
4.3. [Partitioning](#43-partitioning)  
 4.3.1. [Table Partitioning Strategies](#431-table-partitioning-strategies)  
 4.3.2. [Managing Partitions](#432-managing-partitions)  
4.4. [Advanced Indexing](#44-advanced-indexing)  
 4.4.1. [Indexing for Full-text Search](#441-indexing-for-full-text-search)  
 4.4.2. [Multi-column Indexes](#442-multi-column-indexes)  
 4.4.3. [Index-only Scans](#443-index-only-scans)  
4.5. [Security and Authentication](#45-security-and-authentication)  
 4.5.1. [Roles and Privileges](#451-roles-and-privileges)  
 4.5.2. [Managing Users and Permissions](#452-managing-users-and-permissions)  
 4.5.3. [SSL and Encryption](#453-ssl-and-encryption)  
4.6. [Replication and High Availability](#46-replication-and-high-availability)  
 4.6.1. [Master-Slave Replication](#461-master-slave-replication)  
 4.6.2. [Hot Standby](#462-hot-standby)  
 4.6.3. [Streaming Replication](#463-streaming-replication)  
 4.6.4. [Logical Replication](#464-logical-replication)  
4.7. [Working with JSON Data](#47-working-with-json-data)  
 4.7.1. [JSON and JSONB Data Types](#471-json-and-jsonb-data-types)  
 4.7.2. [Querying JSON Data](#472-querying-json-data)  
 4.7.3. [Indexing JSON Data](#473-indexing-json-data)  
4.8. [Full-text Search in PostgreSQL](#48-full-text-search-in-postgresql)  
 4.8.1. [`tsvector` and `tsquery`](#481-tsvector-and-tsquery)  
 4.8.2. [Implementing Full-text Search](#482-implementing-full-text-search)

### 5. [PostgreSQL Extensions and Ecosystem](#5-postgresql-extensions-and-ecosystem)

5.1. [Installing and Using Extensions](#51-installing-and-using-extensions)  
5.2. [Popular Extensions](#52-popular-extensions)  
 5.2.1. [PostGIS (Geospatial Data)](#521-postgis-geospatial-data)  
 5.2.2. [pg_stat_statements (Query Performance Monitoring)](#522-pg_stat_statements-query-performance-monitoring)  
 5.2.3. [pgcrypto (Cryptographic Functions)](#523-pgcrypto-cryptographic-functions)  
5.3. [Integrating PostgreSQL with Other Technologies](#53-integrating-postgresql-with-other-technologies)  
 5.3.1. [Using PostgreSQL with Python, Node.js, etc.](#531-using-postgresql-with-python-nodejs-etc)  
 5.3.2. [PostgreSQL in Docker](#532-postgresql-in-docker)

### 6. [Best Practices and Real-world Use Cases](#6-best-practices-and-real-world-use-cases)

6.1. [Database Design Best Practices](#61-database-design-best-practices)  
6.2. [Schema Management and Versioning (with tools like Flyway or Liquibase)](#62-schema-management-and-versioning-with-tools-like-flyway-or-liquibase)  
6.3. [Backups and Restores](#63-backups-and-restores)  
6.4. [Handling Migrations](#64-handling-migrations)  
6.5. [Common Mistakes to Avoid](#65-common-mistakes-to-avoid)  
6.6. [Case Studies: Real-world PostgreSQL Use Cases](#66-case-studies-real-world-postgresql-use-cases)

---

## 1. Introduction to PostgreSQL

### 1.1. What is PostgreSQL?

PostgreSQL, commonly known as Postgres, is an open-source [relational database management system (RDBMS)](https://cloud.google.com/learn/what-is-a-relational-database?hl=en). It is a reliable database that has been actively developed and used for almost 30 years.

### 1.2. Installing PostgreSQL (Windows, Mac, Linux)

To install Postgres on your system, follow the [official documentation](https://www.postgresql.org/) for your operating system. This guide will focus on MacOs.

There are several ways to install Postgres in Mac including using Homebrew, Docker, or downloading the installer from the official website. For this case, we will download using [Postgres.app](https://postgresapp.com/).

Postgres.app is a Postgres installer that comes as a minimal app. It downloads Postgres and other common utilities and tools, and installs them to your system. It can handle multiple flavors of Postgres and can run multiple Postgres instances at the same time. It also comes with a simplified Graphical User Interface (GUI) for managing databases.

To install Postgres.app:

- Visit the official website.
- Click the "Download" button to get the latest version.
- Open the downloaded .dmg file.
- Drag the Postgres.app icon to your Applications folder.

To use Postgres.app, launch it from your Applications folder. It will start a Postgres server and you can see it running in the top menu bar.

Next, add Postgres.app to your PATH environment variable. This will allow you to run Postgres commands from anywhere in your terminal. To do this, open your terminal and run the following command:

```bash
nano ~/.zshrc
```

Then, add the following line to the end of the file:

```bash
export PATH="$PATH:/Applications/Postgres.app/Contents/Versions/latest/bin"
```

Press `control + x` then type Y to save the file. After that, restart your terminal.

### 1.3. PostgreSQL vs Other Databases

Databases are of various types, each storing and managing data in their own way. Databases can be broadly categorized into these two categories:

- **Relational Databases (RDBMS) or SQL Databases**: Postgres is a relational database. This means it stores data in tables and those tables can be related to each other. Postgres is mostly used for structured data.
- **NoSQL Databases**: These are non-relational databases that don't use tables. They are suited for unstructured or semi-structured data. Common types of NoSQL databases are:
  - Key-Value Stores: Stores data as key-value pairs. [Redis](https://redis.io/) is a popular example.
  - Document Databases: Stores data as documents. [MongoDB](https://www.mongodb.com/) is a popular example.
  - Graph Databases: Stores data as nodes and edges. [Neo4j](https://neo4j.com/) is a popular example.

### 1.4. How to Connect to PostgreSQL

Open the postgres.app application and run the default instance it has. You will notice that it has three active databases - postgres, template1 and one named after the system user.

- The postgres one is the default database that is created when you install Postgres. It is used to store system-level information.
- The template1 one contains database templates that are used to create new databases.
- The one named after the system user is an extra database that you can start using immediately.

Once it is running, open a terminal window and type `psql` to connect to the default database. If all is well, you will see the Postgres version that postgres.app is using and be dropped into an interactive terminal. You can also connect to a specific database by typing `psql -d database_name`.

#### 1.4.1. Using `psql` (PostgreSQL Command-Line Tool)

[PSQL](https://www.postgresql.org/docs/current/app-psql.html) is a command line tool that allows you to interact with a Postgres database. You can then interact with the connected database directly in the terminal. You can run `sql` commands, create tables, and perform other database operations.

Common `psql` commands include:

- `\l`: List all databases.
- `\c database_name`: Connect to a specific database.
- `\dt`: List all tables in the current database.
- `\d table_name`: Describe a specific table.
- `\q`: Quit the `psql` session.

#### 1.4.2. Connecting via GUI (pgAdmin, DBeaver)

[Content to be added]

## 2. Basic PostgreSQL Commands

### 2.1. Creating a Database

[Content to be added]

### 2.2. Creating and Dropping Tables

[Content to be added]

### 2.3. Data Types in PostgreSQL

[Content to be added]

### 2.4. Inserting, Updating, and Deleting Data

[Content to be added]

### 2.5. Basic Queries: `SELECT`, `WHERE`, `ORDER BY`

[Content to be added]

### 2.6. Filtering Results: `LIMIT`, `OFFSET`

[Content to be added]

### 2.7. Basic Joins: `INNER JOIN`, `LEFT JOIN`

[Content to be added]

### 2.8. Aliases for Columns and Tables

[Content to be added]

### 2.9. Exporting and Importing Data (`COPY`, `pg_dump`)

[Content to be added]

## 3. Intermediate PostgreSQL Concepts

### 3.1. Constraints

#### 3.1.1. Primary Key, Foreign Key, Unique Constraints

[Content to be added]

#### 3.1.2. Check Constraints

[Content to be added]

### 3.2. Indexes

#### 3.2.1. Creating Indexes

[Content to be added]

#### 3.2.2. B-tree vs GIN vs GiST Indexes

[Content to be added]

#### 3.2.3. Partial Indexes

[Content to be added]

### 3.3. Views

#### 3.3.1. Creating and Using Views

[Content to be added]

#### 3.3.2. Materialized Views

[Content to be added]

### 3.4. Transactions

#### 3.4.1. ACID Properties

[Content to be added]

#### 3.4.2. Using `BEGIN`, `COMMIT`, `ROLLBACK`

[Content to be added]

### 3.5. Functions and Stored Procedures

#### 3.5.1. Built-in Functions (Math, String, Date)

[Content to be added]

#### 3.5.2. Writing Custom Functions (PL/pgSQL)

[Content to be added]

#### 3.5.3. Working with Stored Procedures

[Content to be added]

### 3.6. Triggers

#### 3.6.1. Creating Triggers

[Content to be added]

#### 3.6.2. Common Use Cases

[Content to be added]

## 4. Advanced PostgreSQL Topics

### 4.1. Advanced Queries

#### 4.1.1. Subqueries

[Content to be added]

#### 4.1.2. Common Table Expressions (CTEs)

[Content to be added]

#### 4.1.3. Window Functions

[Content to be added]

#### 4.1.4. Recursive Queries

[Content to be added]

### 4.2. Performance Tuning

#### 4.2.1. Query Optimization

[Content to be added]

#### 4.2.2. Analyzing Queries (`EXPLAIN`, `ANALYZE`)

[Content to be added]

#### 4.2.3. Vacuuming and Autovacuum

[Content to be added]

### 4.3. Partitioning

#### 4.3.1. Table Partitioning Strategies

[Content to be added]

#### 4.3.2. Managing Partitions

[Content to be added]

### 4.4. Advanced Indexing

#### 4.4.1. Indexing for Full-text Search

[Content to be added]

#### 4.4.2. Multi-column Indexes

[Content to be added]

#### 4.4.3. Index-only Scans

[Content to be added]

### 4.5. Security and Authentication

#### 4.5.1. Roles and Privileges

[Content to be added]

#### 4.5.2. Managing Users and Permissions

[Content to be added]

#### 4.5.3. SSL and Encryption

[Content to be added]

### 4.6. Replication and High Availability

#### 4.6.1. Master-Slave Replication

[Content to be added]

#### 4.6.2. Hot Standby

[Content to be added]

#### 4.6.3. Streaming Replication

[Content to be added]

#### 4.6.4. Logical Replication

[Content to be added]

### 4.7. Working with JSON Data

#### 4.7.1. JSON and JSONB Data Types

[Content to be added]

#### 4.7.2. Querying JSON Data

[Content to be added]

#### 4.7.3. Indexing JSON Data

[Content to be added]

### 4.8. Full-text Search in PostgreSQL

#### 4.8.1. `tsvector` and `tsquery`

[Content to be added]

#### 4.8.2. Implementing Full-text Search

[Content to be added]

## 5. PostgreSQL Extensions and Ecosystem

### 5.1. Installing and Using Extensions

[Content to be added]

### 5.2. Popular Extensions

#### 5.2.1. PostGIS (Geospatial Data)

[Content to be added]

#### 5.2.2. pg_stat_statements (Query Performance Monitoring)

[Content to be added]

#### 5.2.3. pgcrypto (Cryptographic Functions)

[Content to be added]

### 5.3. Integrating PostgreSQL with Other Technologies

#### 5.3.1. Using PostgreSQL with Python, Node.js, etc.

[Content to be added]

#### 5.3.2. PostgreSQL in Docker

[Content to be added]

## 6. Best Practices and Real-world Use Cases

### 6.1. Database Design Best Practices

[Content to be added]

### 6.2. Schema Management and Versioning (with tools like Flyway or Liquibase)

[Content

### 6.2. Schema Management and Versioning (with tools like Flyway or Liquibase)

[Content to be added]

### 6.3. Backups and Restores

[Content to be added]

### 6.4. Handling Migrations

[Content to be added]

### 6.5. Common Mistakes to Avoid

[Content to be added]

### 6.6. Case Studies: Real-world PostgreSQL Use Cases

[Content to be added]
