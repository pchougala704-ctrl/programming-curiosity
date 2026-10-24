# Process

A process is a running instance of a program. When you launch an application, the operating system creates a process and gives it resources such as memory, access to files, and time on the processor.

Each process has its own execution state and typically a protected address space. A process can create other processes, and processes can communicate using operating-system features such as pipes, shared memory, or network connections.

A program is the instructions stored on disk; a process is those instructions in action. Starting the same program twice can create two separate processes with independent state.

## Challenge questions

- **31.** Who receives the command `python app.py`?
- **32.** How does the operating system know where Python is?
- **33.** What is a process?
- **40.** What happens when the program crashes?

Read the [seven-lens answers](./challenge-answers.md#how-programs-run-seven-lens-answers).

The [rabbit-hole answers](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers) also explain how one program detects that another has crashed.

### Related rabbit-hole questions

- When I type `python app.py`, what happens between pressing Enter and seeing the output?
- How does a program know that another program has crashed?

Read the [seven-lens rabbit-hole answers](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers).
