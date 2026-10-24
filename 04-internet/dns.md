# DNS

The Domain Name System (DNS) helps computers find network addresses associated with names. People can remember a name such as `example.com` more easily than a numeric IP address.

When an application needs to contact a domain, it can ask a DNS resolver for the domain's records. The resolver may already have a cached answer, or it may query other DNS servers. The returned records can include IP addresses and other information.

DNS is often compared to a phone book, but it is a distributed system with caching and multiple record types. Because answers may be cached for a period of time, a DNS change may not appear everywhere immediately.

## Challenge questions

- **41.** What happens when you type `google.com` into a browser?
- **42.** How does your computer find Google's server?
- **43.** What is DNS?

Read the [seven-lens answers](./challenge-answers.md#internet-seven-lens-answers).

### Related rabbit-hole question

**When I enter `google.com`, how does my computer find another computer somewhere in the world?**

Read the [seven-lens rabbit-hole answer](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers).
