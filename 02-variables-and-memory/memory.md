# Memory

A running program needs a place to keep the data it is currently using. A computer's main memory, usually called RAM, provides fast temporary storage for program instructions and values. It is generally cleared when the computer loses power.

Programs use memory for many kinds of information: numbers, text, collections, and the state needed to continue running. The operating system gives each process a protected address space, so one program normally cannot freely read or overwrite another program's memory.

Memory is limited. Programs need to use it sensibly, and some languages or runtimes help manage the lifetime of objects. Long-term information is usually saved to storage such as a disk or database rather than kept only in RAM.

## Curiosity questions

The answers below expand questions 21–25 and 30 from the [Programming Curiosity Challenge](../CHALLENGE.md). See the [complete variables and memory answers](./challenge-answers.md) for all questions in this section.

### 21. What is RAM actually doing while your program runs?

- **WHY?** The processor needs fast working space for active instructions and data.
- **WHAT?** RAM holds pages of code and data currently used by processes and the operating system.
- **HOW?** The OS maps virtual memory to physical pages, which hardware reads and writes.
- **WHERE?** In the computer's main memory.
- **WHEN?** While programs and the OS are active.
- **WHO?** The OS, processor, memory controller, and programs participate.
- **WHAT IF?** Memory pressure rises; the OS may reclaim caches, page data, or terminate processes.

### 22. What is the difference between RAM and storage?

- **WHY?** A computer needs both temporary working memory and persistent data retention.
- **WHAT?** RAM is fast and usually volatile; SSD/HDD storage retains files without power.
- **HOW?** Programs load data from storage into memory, work on it, and may save changes back.
- **WHERE?** RAM is main memory; storage is a persistent device.
- **WHEN?** RAM serves active work; storage preserves data across restarts.
- **WHO?** Applications and the OS coordinate reads, writes, and caching.
- **WHAT IF?** Unsaved data only in RAM is lost when power stops.

### 23. Where does a Python variable live?

- **WHY?** The name-to-object model avoids requiring programmers to manage raw addresses.
- **WHAT?** A Python variable is a name binding; its object is a separate value.
- **HOW?** Namespace lookup resolves a name to an object reference.
- **WHERE?** In process virtual memory; exact placement depends on the implementation.
- **WHEN?** While the name remains in scope and the object remains reachable.
- **WHO?** The Python runtime manages the binding and object.
- **WHAT IF?** A name leaves scope but its object escapes through a return value; the object remains alive.

### 24. What is a memory address?

- **WHY?** Hardware and software need a way to locate instructions and data.
- **WHAT?** An address identifies a location in an address space.
- **HOW?** Hardware commonly translates virtual addresses to physical memory using page tables.
- **WHERE?** In a process's virtual address space and the machine's memory system.
- **WHEN?** During memory access and low-level debugging.
- **WHO?** Processors, operating systems, runtimes, and debuggers use addresses.
- **WHAT IF?** A program accesses an invalid address; the OS may stop it with a protection fault.

### 25. Why can't we normally see memory addresses in Python?

- **WHY?** Most Python programs should not depend on implementation-specific memory layouts.
- **WHAT?** Python exposes names and object behavior rather than a stable physical-address interface.
- **HOW?** The runtime abstracts allocation and references.
- **WHERE?** Addresses remain internal, though debuggers and extensions may inspect them.
- **WHEN?** Low-level diagnostics may need them.
- **WHO?** Runtime authors provide abstraction; extension authors can use lower-level interfaces.
- **WHAT IF?** Code relies on an address; it can break across runs, implementations, or versions.

### 30. What happens when your program consumes too much memory?

- **WHY?** Physical memory and process limits are finite.
- **WHAT?** Excess use can cause paging, allocation failure, runtime errors, or process termination.
- **HOW?** The runtime and OS respond according to available resources and limits.
- **WHERE?** Effects may be limited to one process or affect a container or whole machine.
- **WHEN?** When demand exceeds available memory or configured quotas.
- **WHO?** Application code, runtime, OS, and service operator affect the result.
- **WHAT IF?** Measure allocation and retention, reduce the working set, then adjust capacity or limits as appropriate.
