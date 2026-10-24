# Cloud and deployment: seven-lens answers

Answers correspond to questions 91–100 in the [Programming Curiosity Challenge](../CHALLENGE.md). Large services use evolving designs; these are general patterns.

## 91. Where does your application actually run after deployment?

- **WHY?** Deployment makes the application available to its users.
- **WHAT?** It runs as processes or managed workloads on devices, servers, or cloud infrastructure.
- **HOW?** A build is installed/configured, started, and connected to required services.
- **WHERE?** Data centers, cloud regions, edge locations, or user devices.
- **WHEN?** After a release or when a service instance starts.
- **WHO?** Developers, operators, platform providers, and deployment automation.
- **WHAT IF?** Configuration or environment differs; the deployed app may fail despite working locally.

## 92. What happens when one user uses your application?

- **WHY?** The system must respond to the user's input or request.
- **WHAT?** A client sends data; application logic validates, processes, and returns a result.
- **HOW?** Local code or network requests invoke services and possibly storage.
- **WHERE?** On the user's device and, for online apps, backend infrastructure.
- **WHEN?** At each interaction or background event.
- **WHO?** User, client, backend, and supporting services.
- **WHAT IF?** A dependency is slow or unavailable; the app should handle errors rather than claim false success.

## 93. What changes when one million users use it?

- **WHY?** Higher concurrency increases resource demand and failure impact.
- **WHAT?** CPU, memory, network, storage, and database load grow, often unevenly.
- **HOW?** Systems add instances, caching, queues, replicas, partitioning, and capacity planning.
- **WHERE?** Across application tiers, data stores, and regions.
- **WHEN?** As workload grows or traffic spikes.
- **WHO?** Architects, operators, platform systems, and developers manage capacity.
- **WHAT IF?** A bottleneck or hot spot remains; simply adding app servers may not solve it.

## 94. Why can't we simply buy one huge computer?

- **WHY?** A single machine has cost, performance, and fault limits.
- **WHAT?** Vertical scaling upgrades one system; horizontal scaling distributes work.
- **HOW?** More machines share traffic and provide redundancy, with coordination costs.
- **WHERE?** In data centers or cloud deployments.
- **WHEN?** Scale vertically while practical; distribute when requirements justify it.
- **WHO?** System designers and operators choose the trade-off.
- **WHAT IF?** The large machine fails; a single point of failure can take everything offline.

## 95. What is a server?

- **WHY?** Clients need services or data from another component.
- **WHAT?** A server is a program or machine that responds to client requests.
- **HOW?** It listens on an endpoint, processes requests, and returns responses.
- **WHERE?** On local networks, data centers, cloud platforms, or devices.
- **WHEN?** While providing a service to clients.
- **WHO?** A server process and its operators provide the service.
- **WHAT IF?** It is unavailable; clients need error handling and perhaps failover.

## 96. What is cloud computing?

- **WHY?** Organizations may need computing resources without owning every physical machine.
- **WHAT?** On-demand access to computing, storage, networks, and managed services.
- **HOW?** Providers operate infrastructure and expose it through consoles, APIs, and billing.
- **WHERE?** Provider data centers and regions.
- **WHEN?** When flexible capacity or managed infrastructure is useful.
- **WHO?** Cloud providers operate facilities; customers configure workloads and services.
- **WHAT IF?** A region or provider service fails; architecture and recovery plans determine impact.

## 97. What is AWS/Azure actually providing?

- **WHY?** Teams need infrastructure and managed capabilities for applications.
- **WHAT?** Providers offer virtual machines, networks, storage, databases, identity, and higher-level services.
- **HOW?** Customers provision resources through APIs/console; provider operates underlying facilities and some service layers.
- **WHERE?** Across provider data centers and regions.
- **WHEN?** As workloads are deployed and used.
- **WHO?** Provider and customer share responsibility, with the customer responsible for appropriate configuration.
- **WHAT IF?** Resources are misconfigured or left running; security exposure or unexpected costs can result.

## 98. What happens when a server crashes?

- **WHY?** The service must detect lost capacity and maintain availability.
- **WHAT?** In-flight work may fail; clients see errors or timeouts.
- **HOW?** Health checks detect it; supervisors restart it and load balancers route around it.
- **WHERE?** In the application process, host, or cloud infrastructure.
- **WHEN?** On failure or missed health signals.
- **WHO?** Monitoring, orchestrators, operators, and clients respond.
- **WHAT IF?** State existed only on that machine; it may be lost unless persisted or replicated.

## 99. How do Netflix, YouTube, or Instagram handle millions of users?

- **WHY?** Large demand exceeds what one machine or region can serve reliably.
- **WHAT?** They use distributed services, caching/CDNs, data systems, queues, and operational automation.
- **HOW?** Traffic is distributed; content is cached near users; data and work are partitioned or replicated where appropriate.
- **WHERE?** Across data centers, cloud/edge networks, and user devices.
- **WHEN?** Continuously, with capacity adjusted to demand.
- **WHO?** Service engineering and operations teams plus automated infrastructure.
- **WHAT IF?** A dependency or region fails; redundancy, graceful degradation, and incident response help limit impact.

## 100. If you had to build WhatsApp from scratch, what would you need?

- **WHY?** Messaging requires reliable, private exchange among users and devices.
- **WHAT?** Clients, identity, contact discovery, APIs, message delivery/storage, notifications, media handling, safety, and operations.
- **HOW?** Authenticate users, route and queue messages, protect content, sync devices, and operate resilient infrastructure.
- **WHERE?** Mobile devices, backend services, data stores, and media storage/CDNs.
- **WHEN?** Messages may deliver immediately or queue while recipients are offline.
- **WHO?** Users, clients, messaging services, operators, and abuse-response teams.
- **WHAT IF?** Devices go offline, keys are lost, messages duplicate, or services fail; queues, delivery acknowledgments, backups, and recovery behavior matter.

Continue with [Servers](./server.md), [Cloud computing](./cloud.md), and [Scaling](./scaling.md).
