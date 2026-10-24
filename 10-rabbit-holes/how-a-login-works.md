# How does a login work?

A login is a way for a service to authenticate an identity and then associate later requests with that identity. The details differ between websites, but a typical flow looks like this.

1. You submit credentials over an HTTPS connection.
2. The server checks the credentials. A well-designed service stores password hashes made with a dedicated password-hashing algorithm, not readable passwords.
3. If the check succeeds, the service creates a session or issues a token.
4. The browser sends the session identifier or token with later requests, often using a protected cookie.
5. The server verifies it and then checks authorization before allowing each protected action.
6. Logging out or expiring the session prevents the old credential from continuing to grant access.

Multi-factor authentication adds another proof, such as a security key or one-time code. A valid login proves an identity according to the service; it does not automatically give that identity permission to do everything.

## Related challenge

The [expanded seven-lens answers](./challenge-answers.md#rabbit-holes-seven-lens-answers) trace how login credentials travel from a device to a server and how sessions are established.
