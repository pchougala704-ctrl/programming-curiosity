# Authorization

Authorization decides which actions an identity is allowed to perform. After an application authenticates a user, it can check whether that user may view a record, edit a project, or administer an account.

Permissions can be based on roles, ownership, or specific policy rules. A role-based system might let editors change articles while readers can only view them. The server should check authorization for each protected action rather than trusting a button being hidden in the interface.

A useful rule is to grant only the access needed for a task and deny access by default. This is called the principle of least privilege.

## Challenge questions

- **76.** What happens if someone changes an API request?
- **78.** How does a server know whether you are authorized?
- **80.** How can one careless line of code expose millions of users?

Read the [seven-lens answers](./challenge-answers.md#security-seven-lens-answers).
