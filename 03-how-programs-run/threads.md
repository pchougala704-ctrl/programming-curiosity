# Threads

A thread is a sequence of work being carried out within a process. A process can have one thread or several. Threads in the same process share many resources, including the process's memory, while each thread has its own execution path and call stack.

Multiple threads can help an application handle independent work or make use of multiple processor cores. They can also make programs harder to reason about: if threads access the same data at the same time, the result may depend on timing.

Locks and other synchronization tools help coordinate shared access, but they must be used carefully. Some languages and runtimes also offer asynchronous programming, which can handle waiting tasks without necessarily creating one thread per task.

## Challenge question

- **34.** What is a thread?

Read the [seven-lens answer](./challenge-answers.md#how-programs-run-seven-lens-answers).
