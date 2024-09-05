<!-- Create ToC and content on learning postgres. Progressive from basics -> intermediate -> advanced -->

## ![postgres](https://github.com/user-attachments/assets/caadeb56-16f6-4062-a208-50aaf2c86e06)

## Table of Contents

### 1\. [Introduction to PostgreSQL](#1-introduction-to-postgresql)

1.1. [What is PostgreSQL?](#11-what-is-postgresql)\
1.2. [Installing PostgreSQL (Windows, Mac, Linux)](#12-installing-postgresql-windows-mac-linux)\
1.3. [PostgreSQL vs Other Databases](#13-postgresql-vs-other-databases)\
1.4. [First Steps: Connecting to PostgreSQL](#14-first-steps-connecting-to-postgresql)\
   1.4.1. [Using `psql` (PostgreSQL Command-Line Tool)](#141-using-psql-postgresql-command-line-tool)\
   1.4.2. [Connecting via GUI (pgAdmin, DBeaver)](#142-connecting-via-gui-pgadmin-dbeaver)

### 2\. [Basic PostgreSQL Commands](#2-basic-postgresql-commands)

2.1. [Creating a Database](#21-creating-a-database)\
2.2. [Creating and Dropping Tables](#22-creating-and-dropping-tables)\
2.3. [Data Types in PostgreSQL](#23-data-types-in-postgresql)\
2.4. [Inserting, Updating, and Deleting Data](#24-inserting-updating-and-deleting-data)\
2.5. [Basic Queries: `SELECT`, `WHERE`, `ORDER BY`](#25-basic-queries-select-where-order-by)\
2.6. [Filtering Results: `LIMIT`, `OFFSET`](#26-filtering-results-limit-offset)\
2.7. [Basic Joins: `INNER JOIN`, `LEFT JOIN`](#27-basic-joins-inner-join-left-join)\
2.8. [Aliases for Columns and Tables](#28-aliases-for-columns-and-tables)\
2.9. [Exporting and Importing Data (`COPY`, `pg_dump`)](#29-exporting-and-importing-data-copy-pg_dump)

### 3\. [Intermediate PostgreSQL Concepts](#3-intermediate-postgresql-concepts)

3.1. [Constraints](#31-constraints)\
   3.1.1. [Primary Key, Foreign Key, Unique Constraints](#311-primary-key-foreign-key-unique-constraints)\
   3.1.2. [Check Constraints](#312-check-constraints)\
3.2. [Indexes](#32-indexes)\
   3.2.1. [Creating Indexes](#321-creating-indexes)\
   3.2.2. [B-tree vs GIN vs GiST Indexes](#322-b-tree-vs-gin-vs-gist-indexes)\
   3.2.3. [Partial Indexes](#323-partial-indexes)\
3.3. [Views](#33-views)\
   3.3.1. [Creating and Using Views](#331-creating-and-using-views)\
   3.3.2. [Materialized Views](#332-materialized-views)\
3.4. [Transactions](#34-transactions)\
   3.4.1. [ACID Properties](#341-acid-properties)\
   3.4.2. [Using `BEGIN`, `COMMIT`, `ROLLBACK`](#342-using-begin-commit-rollback)\
3.5. [Functions and Stored Procedures](#35-functions-and-stored-procedures)\
   3.5.1. [Built-in Functions (Math, String, Date)](#351-built-in-functions-math-string-date)\
   3.5.2. [Writing Custom Functions (PL/pgSQL)](#352-writing-custom-functions-plpgsql)\
   3.5.3. [Working with Stored Procedures](#353-working-with-stored-procedures)\
3.6. [Triggers](#36-triggers)\
   3.6.1. [Creating Triggers](#361-creating-triggers)\
   3.6.2. [Common Use Cases](#362-common-use-cases)

### 4\. [Advanced PostgreSQL Topics](#4-advanced-postgresql-topics)

4.1. [Advanced Queries](#41-advanced-queries)\
   4.1.1. [Subqueries](#411-subqueries)\
   4.1.2. [Common Table Expressions (CTEs)](#412-common-table-expressions-ctes)\
   4.1.3. [Window Functions](#413-window-functions)\
   4.1.4. [Recursive Queries](#414-recursive-queries)\
4.2. [Performance Tuning](#42-performance-tuning)\
   4.2.1. [Query Optimization](#421-query-optimization)\
   4.2.2. [Analyzing Queries (`EXPLAIN`, `ANALYZE`)](#422-analyzing-queries-explain-analyze)\
   4.2.3. [Vacuuming and Autovacuum](#423-vacuuming-and-autovacuum)\
4.3. [Partitioning](#43-partitioning)\
   4.3.1. [Table Partitioning Strategies](#431-table-partitioning-strategies)\
   4.3.2. [Managing Partitions](#432-managing-partitions)\
4.4. [Advanced Indexing](#44-advanced-indexing)\
   4.4.1. [Indexing for Full-text Search](#441-indexing-for-full-text-search)\
   4.4.2. [Multi-column Indexes](#442-multi-column-indexes)\
   4.4.3. [Index-only Scans](#443-index-only-scans)\
4.5. [Security and Authentication](#45-security-and-authentication)\
   4.5.1. [Roles and Privileges](#451-roles-and-privileges)\
   4.5.2. [Managing Users and Permissions](#452-managing-users-and-permissions)\
   4.5.3. [SSL and Encryption](#453-ssl-and-encryption)\
4.6. [Replication and High Availability](#46-replication-and-high-availability)\
   4.6.1. [Master-Slave Replication](#461-master-slave-replication)\
   4.6.2. [Hot Standby](#462-hot-standby)\
   4.6.3. [Streaming Replication](#463-streaming-replication)\
   4.6.4. [Logical Replication](#464-logical-replication)\
4.7. [Working with JSON Data](#47-working-with-json-data)\
   4.7.1. [JSON and JSONB Data Types](#471-json-and-jsonb-data-types)\
   4.7.2. [Querying JSON Data](#472-querying-json-data)\
   4.7.3. [Indexing JSON Data](#473-indexing-json-data)\
4.8. [Full-text Search in PostgreSQL](#48-full-text-search-in-postgresql)\
   4.8.1. [`tsvector` and `tsquery`](#481-tsvector-and-tsquery)\
   4.8.2. [Implementing Full-text Search](#482-implementing-full-text-search)

### 5\. [PostgreSQL Extensions and Ecosystem](#5-postgresql-extensions-and-ecosystem)

5.1. [Installing and Using Extensions](#51-installing-and-using-extensions)\
5.2. [Popular Extensions](#52-popular-extensions)\
   5.2.1. [PostGIS (Geospatial Data)](#521-postgis-geospatial-data)\
   5.2.2. [pg_stat_statements (Query Performance Monitoring)](#522-pg_stat_statements-query-performance-monitoring)\
   5.2.3. [pgcrypto (Cryptographic Functions)](#523-pgcrypto-cryptographic-functions)\
5.3. [Integrating PostgreSQL with Other Technologies](#53-integrating-postgresql-with-other-technologies)\
   5.3.1. [Using PostgreSQL with Python, Node.js, etc.](#531-using-postgresql-with-python-nodejs-etc)\
   5.3.2. [PostgreSQL in Docker](#532-postgresql-in-docker)

### 6\. [Best Practices and Real-world Use Cases](#6-best-practices-and-real-world-use-cases)

- [Database Design Best Practices](#database-design-best-practices)
- [Schema Management and Versioning (with tools like Flyway or Liquibase)](#schema-management-and-versioning-with-tools-like-flyway-or-liquibase)
- [Backups and Restores](#backups-and-restores)
- [Handling Migrations](#handling-migrations)
- [Common Mistakes to Avoid](#common-mistakes-to-avoid)
- [Case Studies: Real-world PostgreSQL Use Cases](#case-studies-real-world-postgresql-use-cases)
