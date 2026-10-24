# Internet: seven-lens answers

Answers correspond to questions 41–50 in the [Programming Curiosity Challenge](../CHALLENGE.md). A real visit may involve caches, proxies, and many servers.

## 41. What happens when you type `google.com` into a browser?

- **WHY?** The browser needs to locate a service and request its content.
- **WHAT?** It parses the address, resolves a destination, connects, requests resources, and renders responses.
- **HOW?** DNS, transport connections, TLS, HTTP, and browser rendering work together.
- **WHERE?** Across the device, network, and service infrastructure.
- **WHEN?** After entering the address and submitting it.
- **WHO?** Browser, resolver, network routers, service, and rendering engine.
- **WHAT IF?** DNS, connectivity, TLS, or the server fails; the browser shows an error or incomplete page.

## 42. How does your computer find Google's server?

- **WHY?** Network packets need destination addresses.
- **WHAT?** DNS provides an IP address for a domain; the address can point to an edge or load-balanced service.
- **HOW?** The resolver checks caches or queries DNS; routers forward packets toward the IP.
- **WHERE?** Name resolution occurs through local and distributed resolvers; routing occurs across networks.
- **WHEN?** Before connecting, unless a suitable answer is cached.
- **WHO?** Browser/OS resolver, DNS operators, and network routers.
- **WHAT IF?** The answer is stale or unreachable; connection attempts may fail or be redirected after another lookup.

## 43. What is DNS?

- **WHY?** Names are easier to use than numeric network addresses.
- **WHAT?** DNS is a distributed, hierarchical system that stores and returns domain records.
- **HOW?** Resolvers query authoritative data and cache answers for their time-to-live.
- **WHERE?** Across resolvers and authoritative DNS servers around the world.
- **WHEN?** When a client needs records and does not have a valid cached answer.
- **WHO?** Domain owners, registries, DNS operators, and resolvers maintain the system.
- **WHAT IF?** DNS is unavailable or misconfigured; a service may be unreachable by name.

## 44. What is an IP address?

- **WHY?** Routers need addressing information to forward packets.
- **WHAT?** An IP address identifies a network interface in an IP network; IPv4 and IPv6 are common versions.
- **HOW?** Routers compare destination prefixes with routing tables and forward packets.
- **WHERE?** On network interfaces and in packet headers.
- **WHEN?** During network communication.
- **WHO?** Networks assign addresses; routers and hosts use them.
- **WHAT IF?** The address changes, conflicts, or has no route; communication may fail.

## 45. Why do we need ports?

- **WHY?** A machine may run many network services at the same time.
- **WHAT?** A transport port identifies an application endpoint on a host.
- **HOW?** TCP or UDP uses port numbers to deliver traffic to the appropriate socket.
- **WHERE?** In transport-layer packet headers and operating-system socket tables.
- **WHEN?** When establishing or using a network connection.
- **WHO?** Applications bind/listen; OS networking delivers received traffic.
- **WHAT IF?** The port is blocked or no service listens; the connection is refused or times out.

## 46. What is HTTP?

- **WHY?** Web clients and servers need a common way to request and return resources.
- **WHAT?** HTTP is an application-layer request-response protocol.
- **HOW?** Requests carry methods, targets, headers, and optional bodies; responses carry status, headers, and content.
- **WHERE?** Between clients and servers, usually over a transport connection.
- **WHEN?** When a browser or API client requests web resources.
- **WHO?** Clients and HTTP servers implement the protocol.
- **WHAT IF?** The server returns an error or malformed response; the client must handle it.

## 47. Why was HTTPS created?

- **WHY?** Plain HTTP does not protect data from network observation or modification.
- **WHAT?** HTTPS is HTTP protected by TLS.
- **HOW?** TLS authenticates the server and negotiates encryption and integrity protection.
- **WHERE?** Between the client and the TLS endpoint, which may be a proxy or edge server.
- **WHEN?** During a secure connection setup and throughout protected communication.
- **WHO?** Browser, server, certificate authorities, and TLS implementations participate.
- **WHAT IF?** Certificate validation fails; the browser warns or blocks the connection.

## 48. What happens when you click a button on a website?

- **WHY?** A user action may request a change or additional information.
- **WHAT?** Browser code can update the page, validate input, and possibly send a request.
- **HOW?** An event handler runs; it may call an API and update the UI with the result.
- **WHERE?** The event starts in the browser; network work reaches a server if needed.
- **WHEN?** When the browser dispatches the click event.
- **WHO?** User, browser, page code, and possibly a backend service.
- **WHAT IF?** The request fails or is slow; the UI should communicate status and allow appropriate recovery.

## 49. How does your request travel thousands of kilometres?

- **WHY?** The destination may be outside the local network.
- **WHAT?** Data is packetized and forwarded hop-by-hop through interconnected networks.
- **HOW?** Routers use routing tables; physical links carry signals over fiber, radio, copper, or cables.
- **WHERE?** Across local networks, providers, exchange points, and data centers.
- **WHEN?** During each network transmission.
- **WHO?** Routers and network operators forward traffic.
- **WHAT IF?** A link or route fails; protocols may reroute, retry, or report failure.

## 50. How does the server know where to send the response?

- **WHY?** The client needs to receive the answer to its request.
- **WHAT?** Connection state records the endpoints, including addresses and transport ports.
- **HOW?** The server sends data through the established socket; network routing carries packets back.
- **WHERE?** In transport connection state, OS socket tables, and router forwarding.
- **WHEN?** As the server writes the response.
- **WHO?** Server process, OS networking stack, and routers.
- **WHAT IF?** The client disconnects or its route changes; the write may fail or the response may be lost.

Continue with [DNS](./dns.md), [IP addresses](./ip.md), [HTTP](./http.md), and [HTTPS](./https.md).
