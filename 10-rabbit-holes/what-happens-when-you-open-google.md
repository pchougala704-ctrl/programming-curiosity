# What happens when you open Google?

Opening a search site involves many components working together. This outline describes a typical web visit; the details can vary with browsers, networks, caching, and the services involved.

1. You enter a site address or choose a search result. The browser parses the address and may check cached data.
2. The browser uses DNS to find an IP address for the site's domain.
3. It connects to a server. For HTTPS, the browser and server negotiate a protected TLS connection and the browser checks the server's certificate.
4. The browser sends an HTTP request, and the server returns a response.
5. The browser processes returned HTML, styles, scripts, and other resources. It may make additional requests for them.
6. The browser lays out and displays the page. Scripts may respond to your actions and request more data.

This simplified journey connects DNS, IP, HTTPS, HTTP, servers, and code running in the browser. It does not mean every visit uses a single server: large services may use caches, load balancers, and many distributed systems.

## Related challenge

The [expanded seven-lens answers](./challenge-answers.md#rabbit-holes-seven-lens-answers) trace how a domain reaches a service and what can still work if the Internet becomes unavailable.
