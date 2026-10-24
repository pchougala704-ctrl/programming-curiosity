# Security: seven-lens answers

Answers correspond to questions 71–80 in the [Programming Curiosity Challenge](../CHALLENGE.md). Use reviewed security libraries and verify behavior for your application.

## 71. How does a website know who you are after login?

- **WHY?** It needs to associate later actions with an authenticated identity.
- **WHAT?** A login verifies credentials and establishes a session or token.
- **HOW?** The server checks proof, issues a credential, and validates it on later requests.
- **WHERE?** Authentication occurs at the service; a session credential is held by client and server mechanisms.
- **WHEN?** At login and on each protected request.
- **WHO?** User, client, identity system, and application server.
- **WHAT IF?** The session credential is stolen; an attacker may impersonate the user until it expires or is revoked.

## 72. Where is your password stored?

- **WHY?** The service needs to verify future login attempts without keeping readable passwords.
- **WHAT?** A well-designed service stores a salted password hash, not plaintext.
- **HOW?** A dedicated password-hashing algorithm derives a value for comparison.
- **WHERE?** In protected account records in a database or identity provider.
- **WHEN?** The hash is created at registration/password change and checked at login.
- **WHO?** The service/identity provider manages it; users choose credentials.
- **WHAT IF?** The database leaks; strong unique passwords and slow salted hashes make offline guessing harder.

## 73. Why shouldn't passwords be stored as plain text?

- **WHY?** A data breach would immediately expose users' secrets.
- **WHAT?** Plaintext is the original readable password.
- **HOW?** Instead, store a unique salt and slow password hash such as Argon2id, scrypt, or bcrypt.
- **WHERE?** The password is submitted over a protected connection; only its hash should be stored.
- **WHEN?** Hash during enrollment/change and verify during login.
- **WHO?** Developers and identity providers must implement safe handling.
- **WHAT IF?** Users reuse passwords; exposure at one service can compromise accounts elsewhere.

## 74. What is encryption?

- **WHY?** To keep data confidential and detect unauthorized changes in transit or storage.
- **WHAT?** Encryption transforms plaintext into ciphertext using cryptographic keys.
- **HOW?** Symmetric or public-key cryptography, often combined by protocols such as TLS.
- **WHERE?** On devices, in storage, or across network links.
- **WHEN?** Whenever data needs confidentiality against unauthorized observers.
- **WHO?** Applications and protocol libraries encrypt; authorized parties manage keys.
- **WHAT IF?** Keys are stolen or mishandled; encrypted data may become readable.

## 75. What is hashing?

- **WHY?** To produce a digest useful for integrity checks and secure password verification.
- **WHAT?** A hash function maps input to a fixed-size digest and is designed to be one-way.
- **HOW?** The function deterministically processes input; password storage uses a salted, slow password hash.
- **WHERE?** In software or hardware implementations and stored digests.
- **WHEN?** For integrity checking, fingerprints, and password verification.
- **WHO?** Applications use vetted hash algorithms and libraries.
- **WHAT IF?** A weak or fast hash is used for passwords; attackers can guess at high speed.

## 76. What happens if someone changes an API request?

- **WHY?** Clients cannot be assumed trustworthy; requests can be edited or fabricated.
- **WHAT?** The server receives modified fields or actions.
- **HOW?** It must validate input, authenticate identity, and authorize the specific resource/action.
- **WHERE?** Validation and permission checks belong on the server, even if the UI also checks.
- **WHEN?** For every request, including apparently harmless reads.
- **WHO?** API developers enforce controls; clients and users submit requests.
- **WHAT IF?** A check is missing; unauthorized changes or data access may occur.

## 77. What is CORS?

- **WHY?** Browsers need a policy governing whether one origin can read responses from another.
- **WHAT?** CORS is a browser-enforced cross-origin response-sharing mechanism using HTTP headers.
- **HOW?** The server advertises allowed origins/methods/headers; browsers enforce the policy, sometimes after preflight.
- **WHERE?** In browser networking between web origins and servers.
- **WHEN?** When browser code makes cross-origin requests subject to CORS.
- **WHO?** Server owners configure headers; browsers enforce them.
- **WHAT IF?** CORS is mistaken for authentication; non-browser clients are not blocked by browser CORS policy.

## 78. How does a server know whether you are authorized?

- **WHY?** Authentication alone does not decide what actions are allowed.
- **WHAT?** Authorization evaluates identity, permissions, resource, and requested action.
- **HOW?** Server-side policy checks roles, ownership, scopes, or attributes on every protected operation.
- **WHERE?** In trusted server or service logic.
- **WHEN?** Before returning protected data or changing state.
- **WHO?** Service owners define policies; the server enforces them.
- **WHAT IF?** The check relies only on a hidden button or client claim; it can be bypassed.

## 79. What is a token?

- **WHY?** It lets a client present proof or authority without resending primary credentials.
- **WHAT?** A token is data representing a session, claim, or scoped permission.
- **HOW?** The server validates it, or verifies a signature and checks claims such as expiry.
- **WHERE?** Stored and sent by a client, validated by a service.
- **WHEN?** On requests after authentication or authorization grant.
- **WHO?** Identity provider issues it; client protects it; service validates it.
- **WHAT IF?** A bearer token is stolen; an attacker may use it, so scope, expiry, storage, and revocation matter.

## 80. How can one careless line of code expose millions of users?

- **WHY?** A small flaw can affect a shared route or data boundary at large scale.
- **WHAT?** Examples include a missing authorization check, unsafe query, or public storage setting.
- **HOW?** Attackers or accidental callers reach data or actions the system failed to restrict.
- **WHERE?** APIs, database access, cloud configuration, logs, and deployment boundaries.
- **WHEN?** As soon as vulnerable code/configuration is deployed and reachable.
- **WHO?** Developers, reviewers, operators, and service owners share prevention and response.
- **WHAT IF?** Assume controls can fail; limit privileges, monitor access, revoke credentials, and respond to incidents.

Continue with [Authentication](./authentication.md), [Authorization](./authorization.md), [Hashing](./hashing.md), and [Encryption](./encryption.md).
