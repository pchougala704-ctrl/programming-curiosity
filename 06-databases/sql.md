# SQL

Structured Query Language (SQL) is used to define, query, and change data in relational databases. A relational database organizes information into tables containing rows and columns, with relationships between tables.

For example, a `customers` table might hold customer details, while an `orders` table stores purchases and refers to the customer who made each one. A query can select only the information needed:

```sql
SELECT name
FROM customers
WHERE id = 42;
```

SQL databases are useful when data has clear relationships and needs reliable rules. Different database products support SQL with their own features and variations.

## Challenge questions

- **61.** Why can't we simply store everything in Python variables?
- **62.** Why do applications need databases?
- **63.** What happens when you click “Save”?
- **64.** Where does the data physically go?
- **65.** What is a table?
- **66.** What is a row?
- **67.** What is a column?
- **68.** Why do we need primary keys?

Read the [seven-lens answers](./challenge-answers.md#databases-seven-lens-answers).
