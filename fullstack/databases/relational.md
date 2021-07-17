# Relational

Big table with many columns and rows. Each row is one entry, each column is a field.

It has defined, structured schema. 

They are very good at describing relations between data. 

## SQL

Structured Query Language. A way of forming questions and statements to a database to do CRUD operations.

### SQL databases

- PostgresSQL - open source database, very flexible, scalable
- MySQL - backed by Oracle, often used
- MariaDB - drop in replacement for MySQL, open source
- SQLite - small, performant, not scalable, useful in embedded
- Microsoft SQL Server
- Oracle
- DB2

### Syntax cheatsheet

Just use docs.

```sql
CREATE DATABASE <name>;
CREATE TABLE <table> (
    <field> <type> <attributes>,
    ...,
    <field> <type> <attributes>
);
INSERT INTO <table> (<fields>). VALUES (<values>);
SELECT <projection> FROM <table>;
<SELECT> LIMIT <limit>
<SELECT> WHERE <clause>
<SELECT> WHERE <clause> AND <clause>
<SELECT> ORDER BY <type=asc>
SELECT COUNT(<projection>) FROM users;
SELECT DISTINCT <projection> FROM <table>
UPDATE <table> SET <field>=<value> WHERE <clause> RETURNING <projection>;
DELETE FROM <table> WHERE <clause>;
```

### Types

Some of the types:

- INTEGER
- VARCHAR (max_length)
- TEXT
- TIMESTAMP

### Attributes

Some of the attributes:

```
- PRIMARY KEY - unique, database will primarly index on it
- REFERENCES <table(<foreign_key>)> - refers to PK of other table
- GENERATED ALWAYS AS IDENTITY - generates on insertion
- UNIQUE
- NOT NULL - required
- ON DELETE CASCADE - if FK is deleted do the same
- ON DELETE SET NULL
- ON DELETE NO ACTION - throw an error if you try to delete, default behaviour
```

### JOINS
![](https://btholt.github.io/complete-intro-to-databases/static/a729907d372a71692cc11a04cf37a85b/5a190/SQL_Joins.png)

```sql
SELECT <projection>
FROM <table1>
INNER JOIN <table2>
ON <table1.field> = <table2.field>
WHERE <clause>; 
```

- `INNER JOIN` - include stuff that matches
- `LEFT JOIN` - if A has a FK that does not exist, include it anyway
- `RIGHT JOIN` - if B has a FK that does not exist, include it anyway
- `OUTER JOIN` - inlude things that doesn't match
- `FULL OUTER JOIN` - include everything
- `CROSS JOIN` - make every possible combinations
- `NATURAL JOIN` - looks for FK with the same name and checks if they match

### Subqueries

```sql
SELECT <projection>
FROM <table1>
WHERE
SELECT <field> = (SELECT <projection>
                  FROM <table>
                  WHERE <clause>); 
```

### GROUP BY

Groups rows with same values into summary rows. Helpful with aggregate functions like COUNT, MAX, MIN, SUM, AVG.

## PostgreSQL

### JSONB data type

Allows for unschemed values inside of a schemaful database. Allows to insert jsons into values. 

```sql
CREATE TABLE <table> (
    <name> <type> <attributes>,
    ...
    <name> JSONB <attributes>
)
```

```sql
SELECT <<projection> -> <json_attriute> AS <name>> FROM <table>;
```

Takes an attribute out of json.

```sql
SELECT <<projection> ->> <json_attriute> AS <name>> FROM <table>;
```

Same, but it casts automatically as TEXT.

### Monitoring

`EXPLAIN` allows to see cost.

### Indexes

```sql
CREATE INDEX ON <table> (<fields>);
```

```sql
CREATE UNIQUE INDEX <name> ON <table> (<fields>);
```
Ensures unique values in the index.

There's more types of indexes in Postgres.


### Hasura

Turns Postgres database that turns database into GraphQL endpoint.


### Ops

Primary and Secondary, replication strategy that allows to write to primary server and read from secondaries.

### User Accounts

Making multiple accounts is a good practice. Least privilege principle applies here as well.