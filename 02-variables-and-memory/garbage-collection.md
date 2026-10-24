# Garbage collection

Garbage collection is automatic memory management used by some programming languages and runtimes. A garbage collector looks for objects that a program can no longer reach and reclaims the memory they used, so it can be reused.

For example, if a function creates a temporary object and nothing keeps a reference to it after the function finishes, a collector may eventually identify that object as unused. This reduces the need for programmers to manually free every object.

Garbage collection does not mean memory is unlimited. Objects that are still reachable remain in use, even if the program no longer needs them logically. Some collectors can also pause or slow a program while they work. Other languages use ownership rules or explicit resource management instead.

Memory is only one kind of resource. Files and network connections often need to be closed explicitly, even in languages with garbage collection.

## Curiosity questions

These answers cover questions 20, 28, and 29 in the [Programming Curiosity Challenge](../CHALLENGE.md). For the other questions in this section, see the [complete variables and memory answers](./challenge-answers.md).

### 20. Who cleans unused memory?

- **WHY?** Reclaiming memory makes it available for future allocations.
- **WHAT?** Memory management tracks allocations and decides when their storage can be reused.
- **HOW?** CPython primarily uses reference counting and also has a cyclic garbage collector; other languages use tracing collectors, ownership rules, or explicit deallocation.
- **WHERE?** The language runtime and allocator manage process memory; the operating system manages memory assigned to the process.
- **WHEN?** When an object is no longer reachable or a program explicitly releases memory, depending on the language.
- **WHO?** The runtime, programmer, and operating system have different responsibilities.
- **WHAT IF?** A reference is accidentally retained; the object remains in use even if the program no longer needs it logically.

### 28. What is garbage collection?

- **WHY?** Automatic reclamation reduces the need for programmers to manually free every object.
- **WHAT?** Garbage collection is a runtime process that identifies objects no longer reachable by the program and reclaims their memory.
- **HOW?** Collectors may count references, trace reachable objects, or combine strategies; reclaimed memory can be reused.
- **WHERE?** In a language runtime or managed execution environment.
- **WHEN?** The runtime runs collection according to its implementation and memory needs; exact timing is not generally guaranteed.
- **WHO?** The runtime performs collection, while programmers still need to avoid unnecessary references and manage other resources.
- **WHAT IF?** An object remains reachable through an accidental reference; the collector cannot reclaim it.

### 29. Why doesn't unused memory remain forever?

- **WHY?** Reusing memory helps prevent a program's allocations from growing without limit.
- **WHAT?** Memory for objects that are no longer needed can be reclaimed, although the process may keep it cached for later reuse.
- **HOW?** The runtime frees or recycles allocations, and may return some memory pages to the operating system.
- **WHERE?** Reclamation happens in the process allocator and operating-system memory manager.
- **WHEN?** When the language's memory-management rules determine that storage is no longer needed.
- **WHO?** The runtime and operating system handle different levels of memory reclamation.
- **WHAT IF?** Memory usage still looks high after collection; the allocator may be retaining freed blocks for future allocations, or some objects may still be referenced.

## More related questions

The full [variables and memory answer guide](./challenge-answers.md#variables-and-memory-seven-lens-answers) also answers:

- **19.** What happens to variables when a function finishes?
- **26.** What is a stack?
- **27.** What is a heap?
