# Rabbit holes: seven-lens answers

These answers expand the ten investigations in the [Programming Curiosity Challenge](../CHALLENGE.md). They describe common designs, not the proprietary internals of a particular service.

## 1. When I type `x = 10`, where exactly does `10` go?

- **WHY?** A program needs a representation of the value to use it.
- **WHAT?** In Python, `10` is an integer object and `x` is a name bound to it.
- **HOW?** The interpreter evaluates the expression, stores a binding in a namespace, and manages an object reference.
- **WHERE?** The namespace and object are in the process's virtual address space; the OS maps pages to physical RAM as needed.
- **WHEN?** The binding happens when execution reaches the assignment; the object lives while it is retained.
- **WHO?** Python runtime and allocator manage objects; the OS manages process memory and physical pages.
- **WHAT IF?** `x` is rebound; the old object can be reclaimed when no references remain, though the exact timing and address are implementation-dependent.

## 2. When I type `python app.py`, what happens between pressing Enter and seeing the output?

- **WHY?** The command starts the interpreter to execute the script.
- **WHAT?** The shell launches a Python process, which reads and executes the file.
- **HOW?** The shell resolves the executable; the OS loads it; Python parses source, commonly compiles bytecode, and runs it.
- **WHERE?** The shell and interpreter run as OS processes; the file is read from storage; output goes to a terminal or redirected stream.
- **WHEN?** After Enter, through process startup, script execution, and output flushing.
- **WHO?** Shell, OS, Python runtime, application code, and terminal.
- **WHAT IF?** Syntax errors stop execution early; exceptions, buffering, missing files, or process termination affect the output.

## 3. When I enter `google.com`, how does my computer find another computer somewhere in the world?

- **WHY?** A human-readable domain must be resolved into a network destination.
- **WHAT?** DNS supplies records; IP and routing deliver packets; TLS and HTTP exchange protected web data.
- **HOW?** The browser checks caches, asks a resolver, connects to an IP, and routers forward packets toward the service.
- **WHERE?** Across the device, local network, providers, internet routers, and potentially edge/data-center infrastructure.
- **WHEN?** Name resolution occurs before connecting unless cached; subsequent requests may reuse connections and cached content.
- **WHO?** Browser, resolver, DNS operators, routers, network providers, and service endpoints.
- **WHAT IF?** DNS, routing, TLS validation, or the server fails; the browser reports an error or incomplete response.

## 4. When I click Login, how does my password travel from my phone to the server and come back as “Login successful”?

- **WHY?** The service must verify identity before granting a session.
- **WHAT?** The app sends credentials over HTTPS; the server checks them and returns a session or token if valid.
- **HOW?** TLS protects the connection; the server compares a password-derived value with a salted password hash and applies login protections.
- **WHERE?** Credentials move from the device to the authentication service; the stored password hash is in protected account storage.
- **WHEN?** At login; the returned session credential is presented on later requests.
- **WHO?** User, app, network/TLS stack, identity service, database, and authorization logic.
- **WHAT IF?** The login fails, is intercepted on an insecure connection, or a session is stolen; secure transport, rate limits, MFA, short-lived/revocable sessions, and user feedback help.

## 5. When I upload a photo to Instagram, where does that photo actually go?

- **WHY?** The service needs to store, process, and deliver the media.
- **WHAT?** The app uploads file bytes plus metadata; backend systems validate, transform, and store them.
- **HOW?** An authenticated upload request reaches a service; object storage holds media, databases hold references/metadata, and jobs generate variants.
- **WHERE?** On the device during upload, then in data-center object storage; CDNs may cache delivery copies.
- **WHEN?** Upload occurs after selection; processing and replication may continue asynchronously.
- **WHO?** Client app, upload API, storage, processing workers, database, CDN, and service operators.
- **WHAT IF?** The connection drops midway, the format is rejected, or a service fails; resumable uploads, validation, retry, and clear status can help.

## 6. How can millions of people use the same application at the same time?

- **WHY?** A single process or machine cannot meet every level of demand or availability.
- **WHAT?** The service is a distributed system with multiple application instances and supporting components.
- **HOW?** Load balancing, horizontal scaling, caches/CDNs, queues, database replicas/partitioning, and monitoring share work.
- **WHERE?** Across machines, data stores, regions, and edge networks.
- **WHEN?** Capacity changes with ongoing demand, peaks, and failures.
- **WHO?** Engineering and operations teams plus schedulers and autoscaling systems.
- **WHAT IF?** A bottleneck or dependency fails; graceful degradation, redundancy, and traffic controls protect core functions.

## 7. What happens if two users try to modify the same database record at exactly the same time?

- **WHY?** Concurrent changes must not silently corrupt or unexpectedly overwrite data.
- **WHAT?** The DB applies its concurrency and transaction rules; one update may wait, conflict, or overwrite according to policy.
- **HOW?** Locks, MVCC, isolation levels, optimistic version checks, or serializable transactions coordinate writes.
- **WHERE?** In the database engine and, sometimes, application-level conflict handling.
- **WHEN?** When transactions overlap on the same row or related data.
- **WHO?** Database engine enforces guarantees; application designers define retries, merges, or conflict messages.
- **WHAT IF?** A stale update wins; use version checks or explicit merge/rejection logic to prevent lost updates.

## 8. How does a program know that another program has crashed?

- **WHY?** Dependent software needs to detect failures and recover.
- **WHAT?** It observes evidence such as process exit, health-check failure, timeout, or missed heartbeat.
- **HOW?** The OS can report local process termination; remote systems use timeouts and health probes.
- **WHERE?** In supervisors, orchestrators, clients, load balancers, or service registries.
- **WHEN?** After a process exits or fails to respond within a configured interval.
- **WHO?** OS, supervisor, monitoring service, and dependent application.
- **WHAT IF?** A slow process looks like a crashed one; detection is uncertain in distributed systems, so use cautious timeouts and idempotent recovery.

## 9. If Python, JavaScript, and Java are completely different languages, how can they communicate with each other?

- **WHY?** A system can combine components built with different languages.
- **WHAT?** They share a protocol or interface contract instead of sharing source-code syntax.
- **HOW?** Serialize data through HTTP/JSON, queues, files, subprocess streams, FFI, or a shared runtime.
- **WHERE?** Across process/machine boundaries or inside one process through native bindings.
- **WHEN?** When each component has different ecosystem needs or an existing implementation.
- **WHO?** Developers on both sides define compatible formats, errors, and versioning.
- **WHAT IF?** Schemas drift or one side is unavailable; compatibility checks, timeouts, retries, and versioning help.

## 10. If the Internet disappeared tomorrow, which parts of your application would still work?

- **WHY?** Understanding dependencies reveals which features can operate offline.
- **WHAT?** Local code and locally stored data may work; remote APIs, identity, storage, and content may not.
- **HOW?** Offline-first apps use local storage and queue changes for later synchronization.
- **WHERE?** On the device or local network, without internet-hosted services.
- **WHEN?** During disconnection, and until remote dependencies are needed.
- **WHO?** The client, local services, user, and later synchronization service.
- **WHAT IF?** Queued edits conflict with remote changes; the app needs a conflict-resolution and data-freshness policy.

For further reading, see [What happens when you run code?](./what-happens-when-you-run-code.md), [What happens when you open Google?](./what-happens-when-you-open-google.md), and [How does a login work?](./how-a-login-works.md).
