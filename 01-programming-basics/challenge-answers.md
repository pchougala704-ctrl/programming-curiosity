# Programming basics: seven-lens answers

Answers correspond to questions 1–10 in the [Programming Curiosity Challenge](../CHALLENGE.md). Details vary across languages and platforms.

## 1. What exactly is programming?

- **WHY?** To automate tasks, solve problems, and make ideas repeatable.
- **WHAT?** The design, writing, testing, and maintenance of computer instructions and data.
- **HOW?** People express steps and rules in a language that tools can process.
- **WHERE?** Programs run on computers, phones, servers, browsers, and embedded devices.
- **WHEN?** When a task can be described precisely enough to compute or automate.
- **WHO?** Programmers create programs; runtimes, operating systems, and hardware execute them.
- **WHAT IF?** Incorrect logic can fail, produce wrong results, or affect other systems.

## 2. Why was programming invented?

- **WHY?** To reduce repetitive human work and perform calculations consistently.
- **WHAT?** A way to give programmable machines a sequence of operations to perform.
- **HOW?** Instructions encode calculations, decisions, and actions for a machine.
- **WHERE?** It applies wherever programmable machines and computers are used.
- **WHEN?** It developed as machines needed to carry out increasingly complex, repeatable work.
- **WHO?** Mathematicians, engineers, researchers, and software developers advanced it.
- **WHAT IF?** Without programming, many modern tasks would require slow, error-prone manual work.

## 3. Why can't humans directly communicate with a computer?

- **WHY?** A processor needs precise operations; ordinary language can be ambiguous.
- **WHAT?** Hardware executes machine instructions, while people use higher-level languages.
- **HOW?** Compilers, interpreters, and runtimes translate or execute source-code meaning.
- **WHERE?** The translation occurs in language tools and runtimes.
- **WHEN?** Before execution or as the program runs, depending on the implementation.
- **WHO?** Hardware and language designers define interfaces; tool authors implement them.
- **WHAT IF?** Ambiguous or invalid instructions can cause errors or unintended behavior.

## 4. How does a computer understand `if`, `for`, `while`, and `function`?

- **WHY?** These constructs make decisions, repetition, and reusable work easier to express.
- **WHAT?** They are syntax with defined semantics in a programming language.
- **HOW?** A parser recognizes them; tools implement them with branches, jumps, and calls.
- **WHERE?** Their rules are defined in language specifications and implementations.
- **WHEN?** Their effects occur when execution reaches the corresponding code.
- **WHO?** Language designers define semantics; compiler and runtime authors implement them.
- **WHAT IF?** Incorrect conditions or loops can take the wrong path or repeat indefinitely.

## 5. Who decides what a programming language can do?

- **WHY?** Shared rules let programs and tools work consistently.
- **WHAT?** A language consists of syntax, semantics, and often libraries and runtime behavior.
- **HOW?** Proposals are specified, implemented, reviewed, and tested for compatibility.
- **WHERE?** Rules are recorded in specifications and embodied in compilers and runtimes.
- **WHEN?** Rules evolve through language releases and standards processes.
- **WHO?** Standards bodies, language teams, implementers, and communities shape them.
- **WHAT IF?** Implementations differ; some programs may behave inconsistently across platforms.

## 6. Why are there hundreds of programming languages?

- **WHY?** No single language is ideal for every task and constraint.
- **WHAT?** Each language makes different trade-offs in safety, speed, clarity, and control.
- **HOW?** Designers build new languages around needs, research, or existing limitations.
- **WHERE?** New languages emerge in industry, research, and open-source communities.
- **WHEN?** A new design is useful when existing tools make important work difficult.
- **WHO?** Companies, researchers, standards groups, and open-source teams create them.
- **WHAT IF?** Too many choices fragment expertise and tooling, so ecosystems and standards matter.

## 7. Why do we need Python, Java, JavaScript, C, C++, Go, Rust, and others?

- **WHY?** Projects differ in performance, safety, portability, ecosystem, and team needs.
- **WHAT?** They are languages with distinct designs and tool ecosystems, though capabilities overlap.
- **HOW?** Developers select a fit or connect languages through libraries and interfaces.
- **WHERE?** Python is common in data work, JavaScript in browsers, and C/Rust in systems work, among other uses.
- **WHEN?** Choose after considering requirements, skills, deployment, and maintenance.
- **WHO?** Developers and organizations choose; language communities maintain tools and libraries.
- **WHAT IF?** A language lacks a needed capability; use another language or a clear integration boundary.

## 8. What makes one programming language different from another?

- **WHY?** Language choices affect how safely and effectively people express solutions.
- **WHAT?** Languages vary in syntax, types, memory, concurrency, libraries, and runtime.
- **HOW?** Compilers, interpreters, runtimes, and ecosystems give language rules practical behavior.
- **WHERE?** Differences appear in code, execution, tooling, and deployment.
- **WHEN?** They matter when choosing a language or moving code between ecosystems.
- **WHO?** Designers define the model; implementers and communities shape its use.
- **WHAT IF?** A language's trade-offs conflict with the project; evaluate alternatives on real tasks.

## 9. Why does a programming language need a compiler or interpreter?

- **WHY?** Most source code is not a processor's native instruction format.
- **WHAT?** Compilers translate code; interpreters and runtimes execute it; systems may combine both.
- **HOW?** Tools parse code, check rules, and produce or execute machine code or an intermediate form.
- **WHERE?** Processing may happen during development, deployment, or program execution.
- **WHEN?** Ahead-of-time compilation is before execution; interpretation and JIT work may happen at runtime.
- **WHO?** Tool authors build compilers and runtimes; developers or build systems invoke them.
- **WHAT IF?** Required tools are missing or incompatible, preventing the program from running.

## 10. What actually happens when you run a program?

- **WHY?** Execution turns stored instructions into actions and results.
- **WHAT?** A running program is an active process with state and allocated resources.
- **HOW?** The OS starts it; executable code or a runtime loads instructions; the processor executes them.
- **WHERE?** On a physical or virtual computer, sometimes across multiple services.
- **WHEN?** A user, scheduler, event, or another program starts it.
- **WHO?** The shell, OS, runtime, application, and processor each participate.
- **WHAT IF?** An error, resource limit, or external failure interrupts execution.

Continue with [Why programming?](./why-programming.md), [Programming languages](./programming-languages.md), and [How code runs](./how-code-runs.md).
