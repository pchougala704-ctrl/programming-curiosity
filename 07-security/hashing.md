# Hashing

A cryptographic hash function turns input data into a fixed-size value called a hash or digest. The same input produces the same digest, but a secure hash is designed to make it impractical to recover the input or find a different input with the same digest.

Hashes are useful for checking whether data changed and for storing passwords more safely than plain text. Passwords need special treatment: systems should use a password-hashing algorithm such as Argon2id, scrypt, or bcrypt, with a unique salt and suitable work settings. Fast general-purpose hashes such as SHA-256 alone are not appropriate for password storage.

Hashing is not encryption. Encryption is designed to be reversed with a key; a hash is intended to be one-way.

## Challenge question

- **75.** What is hashing?

Read the [seven-lens answer](./challenge-answers.md#security-seven-lens-answers).
