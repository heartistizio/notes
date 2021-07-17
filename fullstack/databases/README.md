# Databases

- [Fullstack](../README.md)
- [Document-based Databases](./headers.md)
- [Relational](./relational.md)

A repository of data, place to store it on a big scale. Allows to persist application state. Allows to make servers stateless - database stores all of the information. Usually most expensive part of application. One source of truth.

## Query

Command sent to database, could be action or request.

## Schema

Shape of a data. Some databases need strict schemas, other are dynamic.

## Types of databases

Some of the types:

- Relational databses
- Document-based databases
- Graph databses
- Key value store
- Search engines - like Solr or Sphinx
- Wide Column Databases - Google Bigtable, Apache Cassandra, two dimensional key-value store. Resillient and able to scale massively.
- Message brokers - Apache Kafka,, RabbitMQ, Celery, allow apps and services to publish events/messages on a system, broker publishes subscriber about the event happening. 
- Multi model databases - Azure Cosmos DB, ArangoDB, databases that can operate indifferent ways

## ACID

- Atomicity - does the query happen all at once, transactions
- Consistency - running databases on a different server needs ensured consistency
- Isolation - query runned in parallel or sequentially needs to work to same
- Durability - crashed server can be restored to a state that it was in previously, running in memory is fast, but not durable

ACID is safe, but slow. It's a trade off, some databases allow to be flexible per query on ACID level.

## Transaction

Envelope containing multiple queries, either all happens or none of it happens. No other queries will happen between them. 

## Indexes

Databases use trees for indexing. Making reading data significantly faster. 

### Unique indexes

Unique indexes make reading even faster.

### Full text indexes

Allow for a text search of records.

### Aggregation

### ORM

Object-Relation Manager, allows to use a library to construct queries.