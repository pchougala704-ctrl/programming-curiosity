# Authentication

Authentication is the process of checking who or what is making a request. A website may authenticate a person with a password, a security key, a one-time code, or a combination of methods.

After a successful login, an application commonly creates a session or issues a token so the user does not have to prove their identity with every request. These credentials must be protected because anyone who obtains them may be able to act as that user.

Authentication answers "Who are you?" It is different from authorization, which determines what an authenticated identity is allowed to do. A secure login system also needs protections such as rate limits and safe password storage.

## Challenge questions

- **71.** How does a website know who you are after login?
- **72.** Where is your password stored?
- **73.** Why shouldn't passwords be stored as plain text?
- **79.** What is a token?

Read the [seven-lens answers](./challenge-answers.md#security-seven-lens-answers).

### Related rabbit-hole question

**When I click Login, how does my password travel from my phone to the server and come back as “Login successful”?**

Read the [seven-lens rabbit-hole answer](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers).
