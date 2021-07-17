# Document-Based Databases

Schemaless databases, dynamic databases.

## Mongo DB

Easy to get it up and running. 

Key concepts:
- database - group of collections
- collection - group of documents
- document - data entry 

### Querying

- `find`
- `findOne`
- `insert` - "deprecated"
- `insertOne`
- `insertMany`
- `deleteOne`
- `deleteMany`
- `updateOne`
- `updateMany`
- `count`
- query operators
  - `$gt` - greater than
  - `$gte` - greater than or equal to
  - `$lt` - lesser than
  - `$lte` - lesser than or equal to
  - `$ne` - not equal
  - `$eq` - not equal
  - `$and`
  - `$or`
  - `$nor`
  - `$not`
- `sort` - asc 1, desc -1, can handle multiple sorts at once
- `toArray` converts iterator to array


### Geospatial Querying

IE points on a map and finding nearest point to current point.

### Projections

A way to take only what you need from a query. In Mongo it's done by passing second parameter to a query with an object of properties holding `boolean` or `1|0` value.

### Upsert

Update if it exists, insert if it does not.

### Text search

Mongo db supports language aware text search indexes, but does not sort them by default. To sort by score a `$meta: "textScore"` is required in `sort`.

### Aggregation

Allows to slice up data into buckets, allowing to drive insight from data - combine and unwind them, do addition, means etc. Useful for data science.

### Replica Sets

A set of MongodB servers that have the same set of data on them.
It's eventually consistent. 

Each of them has:

- primary server - a server that can be written to
- secondaries - servers that can be read from

### Elections

If primary server goes down holds an election, each server gets a vote and they vote on which server should be the new primary. Then reasigns the most voted server to primary. 

There can be priorities assigned to them.

### Artbiters

Only purpose of arbiters is to vote in elections.

### Sharding

Splitting data into replica sets. Queries are written to Mongos.

### Managed Cloud Version

Most ops can handled by cloud managers.