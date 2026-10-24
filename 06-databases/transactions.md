# Database transactions

A transaction groups database operations into a unit of work. The goal is to ensure that related changes are handled consistently: either the transaction succeeds as a whole, or its changes are rolled back.

Consider moving money between two accounts. The operation should subtract from one account and add to the other. If only one update happened, the records would be inconsistent; a transaction can make both updates succeed or neither persist.

Transactions are often described using ACID: **Atomicity** (all or nothing), **Consistency** (rules remain valid), **Isolation** (concurrent work is managed), and **Durability** (committed changes persist). The exact guarantees depend on the database and its configuration.

## Related challenge question

- **63.** What happens when you click “Save”?

Read the [seven-lens answer](./challenge-answers.md#databases-seven-lens-answers).

The [rabbit-hole answer](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers) explains what can happen when two users modify the same record concurrently.

### Related rabbit-hole question

**What happens if two users try to modify the same database record at exactly the same time?**

Read the [seven-lens rabbit-hole answer](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers).
