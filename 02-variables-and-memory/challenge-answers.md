# Variables and memory: seven-lens answers

Answers correspond to questions 11–30 in the [Programming Curiosity Challenge](../CHALLENGE.md). Python implementation details below are not guarantees for every Python runtime.

## Variables (11–20)

## 11. What happens internally when you write `x = 10`?

- **WHY?** A name makes a value easy to refer to in later code.
- **WHAT?** Python evaluates `10` and binds `x` to the resulting integer object.
- **HOW?** The runtime updates the current namespace with the name-to-object binding.
- **WHERE?** The binding is in a namespace; the object is in process memory.
- **WHEN?** As execution reaches the assignment.
- **WHO?** The Python runtime manages the binding and object.
- **WHAT IF?** If `x` had an earlier binding, it is replaced; the old object may remain if referenced elsewhere.

## 12. Where is `10` stored?

- **WHY?** The runtime needs a representation to perform integer operations.
- **WHAT?** It is an integer object; in CPython it is represented in process memory.
- **HOW?** The runtime allocates or reuses an object representation.
- **WHERE?** In the process's virtual address space, backed by physical memory as needed.
- **WHEN?** While the value is needed or retained by the runtime.
- **WHO?** The interpreter and allocator manage the representation.
- **WHAT IF?** Small integers may be cached, so code must not rely on a particular address or identity.

## 13. Where is `x` stored?

- **WHY?** Names provide access to values without requiring direct address manipulation.
- **WHAT?** `x` is a namespace entry that refers to an object.
- **HOW?** Name lookup resolves the identifier to its current binding.
- **WHERE?** A module or local namespace in the process's virtual address space.
- **WHEN?** While the binding remains in scope and has not been changed or removed.
- **WHO?** Python's runtime manages namespaces and references.
- **WHAT IF?** Another scope also has an `x`; it can refer to a different object.

## 14. Is `x` actually the value `10`?

- **WHY?** Separating names from objects explains assignment and shared references.
- **WHAT?** `x` is a name bound to an integer object whose value is 10.
- **HOW?** Evaluating `x` looks up the binding and obtains the referenced object.
- **WHERE?** The name is in a namespace; the object is in process memory.
- **WHEN?** Until the binding changes or its scope ends.
- **WHO?** The language runtime defines lookup and assignment behavior.
- **WHAT IF?** Multiple names refer to one mutable object; mutation through one is visible through the others.

## 15. What happens when you write `x = 10` and then `x = 20`?

- **WHY?** A program can update which value a name represents.
- **WHAT?** The second statement rebinds `x`; it does not change integer 10.
- **HOW?** The namespace entry for `x` is updated to refer to 20.
- **WHERE?** In the current namespace.
- **WHEN?** When the second assignment executes.
- **WHO?** The Python interpreter performs the rebinding.
- **WHAT IF?** Another name still refers to the old object; that reference remains valid.

## 16. What happens to `10`?

- **WHY?** Unneeded memory can be reused.
- **WHAT?** The old integer object may become eligible for reclamation if no reference remains.
- **HOW?** The runtime tracks references and may also collect cycles.
- **WHERE?** In memory managed by the process's allocator.
- **WHEN?** Reclamation timing is implementation-dependent.
- **WHO?** The runtime's memory manager handles it.
- **WHAT IF?** An alias still refers to the object; it stays alive. Some integers may also be cached.

## 17. What happens when you write `a = b = c = 100`?

- **WHY?** Chained assignment assigns one evaluated value to several names concisely.
- **WHAT?** Each name receives a binding to the resulting object.
- **HOW?** Python evaluates the right-hand expression and then binds each target.
- **WHERE?** In the namespaces containing `a`, `b`, and `c`.
- **WHEN?** As the assignment statement executes.
- **WHO?** The interpreter evaluates and binds the names.
- **WHAT IF?** The value is mutable; all names may alias the same object, so changes are shared.

## 18. Are `a`, `b`, and `c` three copies of `100`?

- **WHY?** Sharing immutable values can avoid unnecessary copies.
- **WHAT?** The names are separate bindings and may refer to one integer object.
- **HOW?** Each binding stores a reference to the same value object.
- **WHERE?** Bindings are in namespaces; the object is in process memory.
- **WHEN?** Sharing may occur immediately after chained assignment.
- **WHO?** The runtime chooses its representation and may reuse objects.
- **WHAT IF?** With a mutable value, modifying through one alias is observable through the others.

## 19. What happens to variables when a function finishes?

- **WHY?** Local scope keeps temporary function state organized.
- **WHAT?** Local bindings stop being active when the call frame ends.
- **HOW?** The runtime returns from the function and releases its local references.
- **WHERE?** Locals are associated with the function's execution frame/namespace.
- **WHEN?** On return or exception unwinding.
- **WHO?** The runtime manages frames; the memory manager manages objects.
- **WHAT IF?** A local object is returned or stored elsewhere; it remains reachable.

## 20. Who cleans unused memory?

- **WHY?** Reclaiming unused allocations makes memory available for new work.
- **WHAT?** Memory management tracks which objects remain in use.
- **HOW?** CPython primarily uses reference counting plus cyclic garbage collection; other runtimes use different approaches.
- **WHERE?** In the language runtime and allocator, with the OS managing process memory.
- **WHEN?** When an object is no longer reachable or explicitly released.
- **WHO?** The runtime, programmer, and OS have different responsibilities.
- **WHAT IF?** A reference is accidentally retained; memory stays occupied even if logically unnecessary.

## Memory (21–30)

## 21. What is RAM actually doing while your program runs?

- **WHY?** The processor needs fast working space for active instructions and data.
- **WHAT?** RAM holds pages of code and data currently used by processes and the OS.
- **HOW?** The OS maps virtual memory to physical pages, which hardware reads and writes.
- **WHERE?** In the computer's main memory.
- **WHEN?** While programs and the OS are active.
- **WHO?** The OS, processor, memory controller, and programs participate.
- **WHAT IF?** Memory pressure rises; the OS may reclaim caches, page data, or terminate processes.

## 22. What is the difference between RAM and storage?

- **WHY?** A computer needs both temporary working memory and persistent data retention.
- **WHAT?** RAM is fast and usually volatile; SSD/HDD storage retains files without power.
- **HOW?** Programs load data from storage into memory, work on it, and may save changes back.
- **WHERE?** RAM is main memory; storage is a persistent device.
- **WHEN?** RAM serves active work; storage preserves data across restarts.
- **WHO?** Applications and the OS coordinate reads, writes, and caching.
- **WHAT IF?** Unsaved data only in RAM is lost when power stops.

## 23. Where does a Python variable live?

- **WHY?** The name-to-object model avoids requiring programmers to manage raw addresses.
- **WHAT?** A Python variable is a name binding; its object is a separate value.
- **HOW?** Namespace lookup resolves a name to an object reference.
- **WHERE?** In process virtual memory; exact placement depends on implementation.
- **WHEN?** While the name remains in scope and the object remains reachable.
- **WHO?** The Python runtime manages the binding and object.
- **WHAT IF?** A name leaves scope but its object escapes through a return value; the object remains alive.

## 24. What is a memory address?

- **WHY?** Hardware and software need a way to locate instructions and data.
- **WHAT?** An address identifies a location in an address space.
- **HOW?** Hardware commonly translates virtual addresses to physical memory using page tables.
- **WHERE?** In a process's virtual address space and the machine's memory system.
- **WHEN?** During memory access and low-level debugging.
- **WHO?** Processors, OSes, runtimes, and debuggers use addresses.
- **WHAT IF?** A program accesses an invalid address; the OS may stop it with a protection fault.

## 25. Why can't we normally see memory addresses in Python?

- **WHY?** Most Python programs should not depend on implementation-specific memory layouts.
- **WHAT?** Python exposes names and object behavior rather than a stable physical-address interface.
- **HOW?** The runtime abstracts allocation and references.
- **WHERE?** Addresses remain internal, though debuggers and extensions may inspect them.
- **WHEN?** Low-level diagnostics may need them.
- **WHO?** Runtime authors provide abstraction; extension authors can use lower-level interfaces.
- **WHAT IF?** Code relies on an address; it can break across runs, implementations, or versions.

## 26. What is a stack?

- **WHY?** Nested function calls need temporary execution state.
- **WHAT?** A call stack is a last-in, first-out sequence of active call frames.
- **HOW?** Calls add frames; returns remove them.
- **WHERE?** Each thread commonly has its own stack.
- **WHEN?** Whenever functions call one another.
- **WHO?** Runtime/compiler conventions, processor, and OS cooperate to manage it.
- **WHAT IF?** Calls become too deep; stack overflow can stop execution.

## 27. What is a heap?

- **WHY?** Some data needs flexible size or lifetime beyond one function call.
- **WHAT?** The heap is a common term for dynamically managed memory.
- **HOW?** Allocators reserve and reuse blocks; runtimes may track object lifetimes.
- **WHERE?** Within a process's virtual address space.
- **WHEN?** When dynamically sized or longer-lived data is needed.
- **WHO?** Runtime allocators, collectors, or programmers manage allocations.
- **WHAT IF?** Allocations grow without release; performance degrades or the process fails.

## 28. What is garbage collection?

- **WHY?** Automatic reclamation reduces manual memory-management work.
- **WHAT?** A process identifies unreachable objects and makes their memory reusable.
- **HOW?** Collectors may use reference counting, tracing, or generational strategies.
- **WHERE?** In a language runtime or managed environment.
- **WHEN?** As required by runtime policy; exact timing can vary.
- **WHO?** The runtime collects; programmers should still avoid retaining needless references.
- **WHAT IF?** An unused object remains reachable; the collector cannot reclaim it.

## 29. Why doesn't unused memory remain forever?

- **WHY?** Reuse prevents needless memory growth.
- **WHAT?** Unreachable allocations can be reclaimed, though the process may keep memory cached for reuse.
- **HOW?** The allocator recycles blocks and may return pages to the OS.
- **WHERE?** Within the process allocator and OS memory manager.
- **WHEN?** According to runtime and allocator policy after memory is no longer needed.
- **WHO?** The runtime and OS handle separate layers.
- **WHAT IF?** Process memory stays high after collection; freed blocks may be retained for later allocations.

## 30. What happens when your program consumes too much memory?

- **WHY?** Physical memory and process limits are finite.
- **WHAT?** Excess use can cause paging, allocation failure, runtime errors, or process termination.
- **HOW?** The runtime and OS respond according to available resources and limits.
- **WHERE?** Effects may be limited to a process or affect a container or whole machine.
- **WHEN?** When demand exceeds available memory or configured quotas.
- **WHO?** Application code, runtime, OS, and service operator affect the result.
- **WHAT IF?** Measure allocation and retention, reduce the working set, then adjust capacity or limits as appropriate.

Continue with [Variables](./variables.md), [Memory](./memory.md), [Stack and heap](./stack-and-heap.md), and [Garbage collection](./garbage-collection.md).
