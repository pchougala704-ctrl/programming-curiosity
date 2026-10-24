# Language comparisons: seven-lens answers

Answers correspond to questions 81–90 in the [Programming Curiosity Challenge](../CHALLENGE.md). Performance depends on workload, implementation, libraries, and configuration.

## 81. Why is Python popular for AI?

- **WHY?** AI development benefits from rapid experimentation and strong numerical tools.
- **WHAT?** Python is a readable language with a mature AI and scientific ecosystem.
- **HOW?** Libraries expose high-level APIs and often run heavy computation in optimized native code or accelerators.
- **WHERE?** Research, data pipelines, notebooks, and production services.
- **WHEN?** When ecosystem and iteration speed matter; performance-sensitive paths can use native libraries.
- **WHO?** Researchers, engineers, educators, and companies use it.
- **WHAT IF?** Pure Python becomes a bottleneck; profile and use optimized libraries or native implementations.

## 82. Why is JavaScript used in browsers?

- **WHY?** Web pages need to react to events and update dynamically.
- **WHAT?** JavaScript is the standard widely supported scripting language built into browsers.
- **HOW?** A browser engine runs scripts and exposes controlled web APIs.
- **WHERE?** In browser contexts such as pages and workers.
- **WHEN?** On page load and in response to events or asynchronous work.
- **WHO?** Browser vendors implement engines; web developers write scripts.
- **WHAT IF?** A script is slow or unsafe; browser isolation and resource limits help, but bugs still affect users.

## 83. Why is Node.js able to run JavaScript on servers?

- **WHY?** JavaScript can be useful outside browser interfaces.
- **WHAT?** Node.js combines a JavaScript engine with server-side APIs and libraries.
- **HOW?** The engine executes JavaScript; Node provides networking, filesystem, and process capabilities.
- **WHERE?** On servers, desktops, and development machines.
- **WHEN?** For backend services, tooling, and scripts.
- **WHO?** Node maintainers and package authors provide the runtime ecosystem.
- **WHAT IF?** Blocking work stalls the event loop; isolate or offload CPU-heavy tasks.

## 84. Why is Java still heavily used in enterprise applications?

- **WHY?** Large systems need stable tooling, libraries, and maintainable runtime behavior.
- **WHAT?** Java is statically typed and commonly runs on the JVM.
- **HOW?** Source compiles to bytecode; JVMs execute and optimize it.
- **WHERE?** Enterprise backends, financial systems, and many other environments.
- **WHEN?** When ecosystem, team experience, JVM portability, or long-term support fit.
- **WHO?** Organizations, developers, and platform vendors sustain its ecosystem.
- **WHAT IF?** Legacy constraints dominate; modernization should weigh risk and value rather than language fashion.

## 85. Why is C still important?

- **WHY?** Some software needs low-level control, compact runtimes, and broad platform support.
- **WHAT?** C is a compiled language with direct access to memory and system interfaces.
- **HOW?** Compilers translate C into native machine code.
- **WHERE?** Operating systems, embedded devices, libraries, and language runtimes.
- **WHEN?** When low-level control or platform compatibility is required.
- **WHO?** Systems programmers and maintainers of foundational software use it.
- **WHAT IF?** Manual memory errors occur; careful design, tools, and safer interfaces help reduce risk.

## 86. Why is Rust becoming popular?

- **WHY?** Developers want systems-level performance with stronger memory-safety guarantees.
- **WHAT?** Rust is a compiled systems language with ownership and borrowing rules.
- **HOW?** The compiler checks many lifetime and aliasing constraints before execution.
- **WHERE?** Systems software, services, tools, and embedded work.
- **WHEN?** When control and safety are important and the team can handle its learning curve.
- **WHO?** Systems developers and organizations adopt it for new or rewritten components.
- **WHAT IF?** The constraints slow development or a library is missing; evaluate whether the safety/performance benefits justify the cost.

## 87. Is Python actually slower than Java?

- **WHY?** Speed matters for latency, throughput, energy, and cost.
- **WHAT?** Python can be slower on CPU-heavy loops than optimized Java, but this is not universal.
- **HOW?** Java JITs optimize hot code; Python workloads often delegate computation to native libraries.
- **WHERE?** Differences appear in the specific runtime and workload, not the language name alone.
- **WHEN?** Benchmark after profiling representative production-like cases.
- **WHO?** Developers and performance engineers measure and optimize the actual system.
- **WHAT IF?** The bottleneck is I/O or database access; changing languages may not help.

## 88. Does “faster language” always mean “better language”?

- **WHY?** Software quality includes more than execution speed.
- **WHAT?** Better means meeting project requirements with acceptable cost and risk.
- **HOW?** Balance performance, safety, readability, ecosystem, delivery speed, and maintenance.
- **WHERE?** Evaluate in the project's actual deployment and team context.
- **WHEN?** During technology selection and when measured bottlenecks appear.
- **WHO?** The team and stakeholders define what “better” means.
- **WHAT IF?** Maximum speed harms maintainability or delivery; a balanced choice can be better overall.

## 89. Can Python call code written in C?

- **WHY?** Native libraries can provide performance or reuse existing functionality.
- **WHAT?** Python can call C through extension modules or foreign-function interfaces.
- **HOW?** Bindings marshal arguments and results across the language boundary.
- **WHERE?** In the same process, subject to ABI and platform constraints.
- **WHEN?** When an appropriate C library exists or profiling identifies a suitable hotspot.
- **WHO?** Extension authors and library maintainers implement the bindings.
- **WHAT IF?** Types, ownership, or ABI are handled incorrectly; memory corruption or crashes can occur.

## 90. Can different programming languages communicate with each other?

- **WHY?** Systems often combine components built with different tools.
- **WHAT?** They exchange data through a shared protocol or interface.
- **HOW?** Use HTTP/JSON, queues, files, subprocess streams, shared runtimes, or foreign-function interfaces.
- **WHERE?** Across process or machine boundaries, or inside one process.
- **WHEN?** When components have different requirements or already exist in different languages.
- **WHO?** Both sides' developers define and maintain the contract.
- **WHAT IF?** Schemas or versions drift; compatibility tests and versioning help.

Continue with [Python](./python.md), [JavaScript](./javascript.md), [Java](./java.md), and [Python vs JavaScript vs Java](./python-vs-javascript-vs-java.md).
