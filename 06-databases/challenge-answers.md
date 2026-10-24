# Databases: seven-lens answers

Answers correspond to questions 61–70 in the [Programming Curiosity Challenge](../CHALLENGE.md). Database guarantees vary by product and configuration.

## 61. Why can't we simply store everything in Python variables?

- **WHY?** Variables are temporary and private to a running process.
- **WHAT?** They hold in-memory state, not durable shared records.
- **HOW?** A process loses ordinary memory on exit; databases persist and coordinate data.
- **WHERE?** Variables are in process memory; database data is in managed storage.
- **WHEN?** Use variables for active computation, databases for durable/shared data.
- **WHO?** Application and database services manage data at different lifetimes.
- **WHAT IF?** The process crashes; unsaved variable contents are lost.

## 62. Why do applications need databases?

- **WHY?** Applications need durable, searchable, shared data.
- **WHAT?** A database manages storage, queries, integrity, and concurrent access.
- **HOW?** It uses data structures, indexes, transactions, and persistent storage.
- **WHERE?** On local or networked storage, or in a managed database service.
- **WHEN?** When information must outlive a process or be accessed by multiple users/services.
- **WHO?** The application, database engine, and operators cooperate.
- **WHAT IF?** Database failure disrupts service; backups and recovery plans reduce impact.

## 63. What happens when you click “Save”?

- **WHY?** The user wants a change to persist.
- **WHAT?** The app validates input and requests a durable write.
- **HOW?** It may send an API request; the service writes in a transaction and returns a result.
- **WHERE?** From the UI to application logic and a database/storage system.
- **WHEN?** After the user submits the form, with success shown only after confirmation.
- **WHO?** User interface, API, database, and storage layers.
- **WHAT IF?** The response is lost after commit; the UI should avoid creating duplicate records on retry.

## 64. Where does the data physically go?

- **WHY?** Durable storage should survive process restarts and power cycles.
- **WHAT?** Database pages, logs, and metadata are stored on persistent devices, often with replicas.
- **HOW?** The DB engine writes through the OS and storage stack, sometimes flushing logs for durability.
- **WHERE?** SSDs/HDDs in a local machine or data center; managed services abstract the hardware.
- **WHEN?** On commits or according to configured write policies.
- **WHO?** Database engine, OS, storage hardware, and operators.
- **WHAT IF?** A device or region fails; replication and tested backups support recovery.

## 65. What is a table?

- **WHY?** Related records need an organized structure.
- **WHAT?** A relational table represents records using named columns.
- **HOW?** The database stores rows and applies schema constraints to columns.
- **WHERE?** In a relational database's logical schema and physical storage structures.
- **WHEN?** When modeling a set of similar entities or events.
- **WHO?** Designers define it; the database manages it.
- **WHAT IF?** The schema does not match evolving needs; migrations can change it carefully.

## 66. What is a row?

- **WHY?** Each individual record needs a representation.
- **WHAT?** A row is one record containing values for table columns.
- **HOW?** SQL operations insert, select, update, and delete rows.
- **WHERE?** In a table's logical data and database storage pages.
- **WHEN?** Whenever an entity or event is stored.
- **WHO?** Applications create/query rows; database engines enforce constraints.
- **WHAT IF?** Required values are absent or invalid; constraints can reject the write.

## 67. What is a column?

- **WHY?** Records need named attributes with defined meaning.
- **WHAT?** A column describes one field, often with a data type and constraints.
- **HOW?** The database validates and stores values according to the schema.
- **WHERE?** In the table definition and each row's logical structure.
- **WHEN?** When designing or querying data.
- **WHO?** Schema designers choose columns; DBMS enforces their rules.
- **WHAT IF?** A column's meaning changes; migration and compatibility planning are needed.

## 68. Why do we need primary keys?

- **WHY?** Each record needs a stable, unambiguous identity.
- **WHAT?** A primary key is a unique, non-null identifier for a row.
- **HOW?** The DB enforces uniqueness and other tables can reference the key.
- **WHERE?** In the table schema, indexes, and related foreign-key records.
- **WHEN?** When records must be individually referenced or updated reliably.
- **WHO?** Schema designers choose keys; the database enforces them.
- **WHAT IF?** A key changes or is reused; references can break or point to the wrong record.

## 69. Why do we need indexes?

- **WHY?** Scanning every row can be slow for common lookups.
- **WHAT?** An index is an auxiliary structure mapping key values to records.
- **HOW?** The database uses it to locate candidate rows, then checks query conditions.
- **WHERE?** In database-managed storage, separate from or associated with table data.
- **WHEN?** For measured query patterns that benefit from faster lookup or ordering.
- **WHO?** Designers/operators create indexes; the DB updates them on writes.
- **WHAT IF?** Too many indexes consume space and slow inserts/updates.

## 70. What is the difference between SQL and NoSQL?

- **WHY?** Data models should fit relationships, queries, scale, and consistency needs.
- **WHAT?** SQL is a query language and commonly refers to relational systems; NoSQL covers varied non-relational models.
- **HOW?** Relational databases use tables/relations; NoSQL systems may use documents, key-values, graphs, or wide columns.
- **WHERE?** Both are used in local, cloud, and distributed applications.
- **WHEN?** Choose based on access patterns, constraints, transactions, and operational needs.
- **WHO?** Developers and operators choose and maintain the database.
- **WHAT IF?** Requirements change; some systems support multiple models, or data migration may be needed.

Continue with [SQL](./sql.md), [NoSQL](./nosql.md), [Indexes](./indexes.md), and [Transactions](./transactions.md).
