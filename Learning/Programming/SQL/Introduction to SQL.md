---
aliases: SQL
tags: SQL
---
Link:

### Introduction to SQL
**Structured Query Language** (SQL — typically pronounced either as S-Q-L or as "sequel").

Clauses make up SQL programs, (we commonly call these programs **queries**).

It's actually not necessary to include the semicolon for the query to run. However, it improves the query's readability.

Use the AS statement directly after each query to rename results.

### Introduction to Databases
A database structures data just like a spreadsheet, by organizing data in different tables comprised of rows and columns. A database can store much more data more securely than a spreadsheet or a text file. However, unlike simply opening a spreadsheet, we actually have to "ask" for data from the database. This is what we do when we write queries.

The `SELECT` clause contains the column names.
The `FROM` clause indicate from which table we want to extract the selected columns.

**Metadata** is data about data.
A very common type of metadata when working with tables is the [data dictionary](https://en.wikipedia.org/wiki/Data_dictionary), which is an explanation of what the columns represent or mean, and other technicalities.

SQL has a way to easily select all columns:
SELECT *
FROM dt;

In SQL, instead of sentences, we use **statements**. Clauses build SQL statements.

### Exploring Tables
The identity column uniquely identifies rows.

`LIMIT` clause

The order of the clauses is **not** interchangeable.

The first thing SQL does when it runs a query is determine what data it will be looking at. Thus, it executes `FROM` first.
After determining the table we're getting data from, SQL will choose the selected columns.
Finally, SQL limits the results with `LIMIT`.

`SELECT DISTINCT`clause to remove duplicate values in a column

There are many different versions of SQL (also called SQL flavors or dialects)
SQLite (pronounced "_sequel light_").

### Coding with Style
The software we use to query databases is called a **database management system** (DBMS).

Typically, SQL flavors and database management systems are considered the same thing, but they're not.

To be precise, SQLite is actually a DBMS, and we're using its SQL version.

Most of the time, DBMS provide a graphical user interface for the interaction between users and the database.

One way to signal a comment is to introduce the intended message with a double dash (`--`)
We can also signal the start of a block comment with `/*` and its end with `*/`.

**Reserved words**, broadly speaking, are words in a programming language that have a special function and therefore shouldn't be used for anything else

Column and table names are **not** reserved words.

Even though it's not necessary for reserved words to be uppercase, it is recommended to capitalize all letters for consistency.

When writing code, we should and adhere to certain stylistic guidelines to be consistent so other readers can easily parse our meaning.

Indenting clause reserved words to be right-aligned, creating an empty column in the middle of the code is called a **river**.

https://www.sqlstyle.guide/


