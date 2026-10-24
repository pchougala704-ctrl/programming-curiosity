# HTTPS

HTTPS is HTTP communication protected by Transport Layer Security (TLS). TLS helps encrypt data in transit, detect changes to that data, and authenticate the server using a certificate.

When a browser connects to a secure site, the browser and server perform a TLS handshake. They agree on cryptographic settings and establish keys for the connection. The browser also checks that the certificate is valid for the site it intended to visit.

HTTPS protects the connection, but it does not guarantee that a website is honest, that a device is free of malware, or that information stored by the site is safe. It is an essential layer of security, not a complete security solution.

## Challenge question

- **47.** Why was HTTPS created?

Read the [seven-lens answer](./challenge-answers.md#internet-seven-lens-answers).

The [rabbit-hole answer](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers) describes what parts of an application may still work without Internet connectivity.

### Related rabbit-hole question

**If the Internet disappeared tomorrow, which parts of your application would still work?**

Read the [seven-lens rabbit-hole answer](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers).
