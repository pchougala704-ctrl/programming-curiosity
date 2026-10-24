# Database indexes

An index is an additional data structure that helps a database find rows more quickly, much like an index in a book helps you find a topic without reading every page. For example, an index on an email column can speed up searches for a particular email address.

Indexes require storage and must be updated when the underlying data changes. Too many indexes can therefore slow down inserts and updates, while too few can make common queries inefficient.

Database designers choose indexes based on actual query patterns. Database query plans and performance measurements can help determine whether an index is useful.

## Challenge question

- **69.** Why do we need indexes?

Read the [seven-lens answer](./challenge-answers.md#databases-seven-lens-answers).
