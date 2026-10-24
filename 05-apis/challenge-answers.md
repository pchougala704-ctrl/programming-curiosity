# APIs: seven-lens answers

Answers correspond to questions 51–60 in the [Programming Curiosity Challenge](../CHALLENGE.md).

## 51. What exactly is an API?

- **WHY?** It lets software use another component without depending on its internals.
- **WHAT?** An API is a defined interface of operations, inputs, outputs, and errors.
- **HOW?** A client follows the interface contract to request a capability or data.
- **WHERE?** Inside one program, between libraries, or across a network.
- **WHEN?** When one component needs another component's functionality.
- **WHO?** Providers define it; consumers use it.
- **WHAT IF?** The API changes incompatibly; clients may fail unless changes are versioned or coordinated.

## 52. Why can't two applications simply access each other's variables?

- **WHY?** Separate apps need isolation and may run on different machines.
- **WHAT?** A variable belongs to one process's memory and is not a shared cross-process contract.
- **HOW?** Apps communicate through APIs, IPC, files, or network protocols.
- **WHERE?** Across process or machine boundaries.
- **WHEN?** Whenever independently running components need to exchange data.
- **WHO?** Both applications and the OS/network mechanisms participate.
- **WHAT IF?** Shared memory is used without coordination; races, corruption, or security leaks can result.

## 53. What happens when a React application calls a Node/Python API?

- **WHY?** The UI needs data or an operation provided by the backend.
- **WHAT?** Browser JavaScript sends a network request and receives a response.
- **HOW?** It serializes input, uses HTTP(S), and handles the response asynchronously; the server validates and processes it.
- **WHERE?** React runs in the browser; Node/Python usually runs in a server process.
- **WHEN?** Often after a page load or user action.
- **WHO?** Browser code, network, API server, and data services.
- **WHAT IF?** The request is slow, blocked, or fails; the UI should show loading/error state and avoid false success.

## 54. What is a request?

- **WHY?** A client needs to specify what service operation it wants.
- **WHAT?** A request is a message identifying a target and operation, with optional metadata and data.
- **HOW?** It carries a URL/path, method, headers, and sometimes a body.
- **WHERE?** It travels from client to server or is passed locally to a component.
- **WHEN?** When an app invokes an API operation.
- **WHO?** The client constructs it; a server or component receives it.
- **WHAT IF?** Required fields are missing or malformed; the server should reject it clearly.

## 55. What is a response?

- **WHY?** The caller needs the outcome of its request.
- **WHAT?** A response reports status and may contain result data or an error.
- **HOW?** The server returns a status code, headers, and optional body.
- **WHERE?** It travels back over the connection or local interface.
- **WHEN?** After the operation succeeds, fails, or reaches a timeout.
- **WHO?** The service creates it; the client interprets it.
- **WHAT IF?** The response is lost or malformed; the client should handle uncertainty safely.

## 56. Why do APIs commonly use JSON?

- **WHY?** It is convenient for exchanging common data structures across languages.
- **WHAT?** JSON is a text data format for objects, arrays, strings, numbers, booleans, and null.
- **HOW?** Each side serializes data to JSON and parses it back.
- **WHERE?** In HTTP bodies, files, and messaging systems.
- **WHEN?** When human-readable interoperable data is more useful than a specialized binary format.
- **WHO?** API designers choose it; libraries implement encoding and decoding.
- **WHAT IF?** Payloads become huge or performance-sensitive; binary formats may be more suitable.

## 57. What are HTTP methods?

- **WHY?** Requests need a standard way to express intended operations.
- **WHAT?** Methods such as GET, POST, PUT, PATCH, and DELETE describe request semantics.
- **HOW?** Clients select a method; servers implement its defined behavior for a resource.
- **WHERE?** In the HTTP request line or protocol representation.
- **WHEN?** For every HTTP request.
- **WHO?** HTTP defines semantics; API designers and server implementers apply them.
- **WHAT IF?** A method is used inconsistently; clients may make unsafe assumptions about caching or retries.

## 58. Why do we have GET, POST, PUT, PATCH, and DELETE?

- **WHY?** Common operations benefit from shared, predictable meanings.
- **WHAT?** GET retrieves; POST commonly creates or triggers processing; PUT replaces/creates at a known URI; PATCH partially modifies; DELETE requests removal.
- **HOW?** Client and server agree on method semantics and resource behavior.
- **WHERE?** In HTTP APIs.
- **WHEN?** Use the method matching the intended operation and API contract.
- **WHO?** API designers document behavior; clients and servers follow it.
- **WHAT IF?** A retry repeats a non-idempotent POST; duplicate side effects may occur unless guarded.

## 59. What happens if an API takes 10 seconds to respond?

- **WHY?** The client is waiting for remote work or a network operation.
- **WHAT?** The request remains pending until completion, timeout, or cancellation.
- **HOW?** Client deadlines, loading states, and bounded retries can manage waiting.
- **WHERE?** Delay may occur in the network, application, database, or external dependency.
- **WHEN?** Whenever processing exceeds normal latency.
- **WHO?** Client and service operators should monitor latency and communicate status.
- **WHAT IF?** A retry duplicates a write; use idempotency keys or another safe retry strategy.

## 60. What happens if the API server is completely down?

- **WHY?** No service process is available to handle the request.
- **WHAT?** Connections fail or time out; the operation's outcome may be unknown.
- **HOW?** Clients report failure, use bounded retries/backoff, or use a safe fallback.
- **WHERE?** At connection establishment or while waiting for a response.
- **WHEN?** During an outage, deployment, overload, or network partition.
- **WHO?** Client users, service operators, and monitoring systems are affected.
- **WHAT IF?** The request reached the server before failure; verify operation state before retrying non-idempotent work.

Continue with [What is an API?](./what-is-api.md), [Request and response](./request-response.md), and [REST APIs](./rest-api.md).
