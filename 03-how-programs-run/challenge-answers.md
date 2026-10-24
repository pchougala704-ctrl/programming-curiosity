# How programs run: seven-lens answers

Answers correspond to questions 31–40 in the [Programming Curiosity Challenge](../CHALLENGE.md). This describes a common command-line workflow; platform details vary.

## 31. Who receives the command `python app.py`?

- **WHY?** Commands need a program to interpret and launch them.
- **WHAT?** The command-line shell receives the text entered in the terminal.
- **HOW?** The shell parses the command, resolves `python`, and requests process creation.
- **WHERE?** In the terminal's shell process.
- **WHEN?** After Enter submits the command.
- **WHO?** The shell, then the operating system and Python executable.
- **WHAT IF?** The command is misspelled or unavailable; the shell reports a lookup error.

## 32. How does the operating system know where Python is?

- **WHY?** The system must locate the executable before it can start Python.
- **WHAT?** Shell command lookup searches configured paths or uses an explicit path.
- **HOW?** On common systems, the shell checks directories in `PATH`; Windows can also use command resolution and file associations.
- **WHERE?** In environment configuration and filesystem locations.
- **WHEN?** When the shell processes the command name.
- **WHO?** The shell performs lookup; the OS loads the selected executable.
- **WHAT IF?** Multiple Python installations exist; the first matching executable may not be the one expected.

## 33. What is a process?

- **WHY?** The OS needs an isolated unit in which to run a program and track its resources.
- **WHAT?** A process is a running program instance with execution state and resources.
- **HOW?** The OS creates an address space, handles, and scheduling state for it.
- **WHERE?** In the operating system's process and memory-management systems.
- **WHEN?** When a program is launched or a process is created by another.
- **WHO?** The OS manages it; users and programs can start or stop processes.
- **WHAT IF?** A process crashes; the OS reclaims its resources, while other processes usually continue.

## 34. What is a thread?

- **WHY?** A process may need multiple concurrent paths of work.
- **WHAT?** A thread is an execution sequence within a process.
- **HOW?** The OS/runtime schedules threads; threads share process resources but have their own stacks and state.
- **WHERE?** Inside a process.
- **WHEN?** When a program creates threads or its runtime provides them.
- **WHO?** The OS scheduler and runtime coordinate execution.
- **WHAT IF?** Threads modify shared data without coordination; race conditions can occur.

## 35. Where does the Python interpreter run?

- **WHY?** Python source needs an implementation that can process its language rules.
- **WHAT?** The interpreter is native executable code running as a process.
- **HOW?** The processor executes the interpreter's machine instructions, which process Python code.
- **WHERE?** In the OS process on the computer or server.
- **WHEN?** After the Python executable is launched.
- **WHO?** The OS loads and schedules it; the Python runtime executes the script.
- **WHAT IF?** The interpreter is unavailable or incompatible; the script cannot run in that environment.

## 36. How does Python read your `.py` file?

- **WHY?** The runtime needs to turn source text into executable language operations.
- **WHAT?** It decodes, tokenizes, parses, and compiles the file, typically into bytecode.
- **HOW?** Python reads file contents, checks grammar, builds an internal representation, and executes it.
- **WHERE?** The file is on storage; parsed structures and runtime state are in process memory.
- **WHEN?** During startup or when the code is imported.
- **WHO?** The Python interpreter performs these steps.
- **WHAT IF?** The file has invalid syntax or encoding; Python reports an error before the affected code runs.

## 37. Does Python directly understand your source code?

- **WHY?** Source must be processed according to the language's syntax and meaning.
- **WHAT?** Python implementations understand Python semantics; the processor itself only executes machine instructions.
- **HOW?** The interpreter parses and executes source-derived bytecode or another internal representation.
- **WHERE?** Processing happens inside the runtime process.
- **WHEN?** At startup or during import, with implementation-specific compilation behavior.
- **WHO?** The runtime handles Python semantics; the CPU executes the runtime.
- **WHAT IF?** A feature is unsupported by that Python version; parsing or execution can fail.

## 38. What is bytecode?

- **WHY?** An intermediate instruction form can be easier for a runtime to execute than source text.
- **WHAT?** Bytecode is a runtime-specific representation, not usually native machine code.
- **HOW?** A compiler turns parsed source into instructions for a virtual machine.
- **WHERE?** It may be held in memory and sometimes cached on storage.
- **WHEN?** It is produced before or during execution, depending on implementation.
- **WHO?** The language compiler/runtime defines and executes it.
- **WHAT IF?** Bytecode is incompatible across runtime versions; it may need to be regenerated.

## 39. What is the Python Virtual Machine?

- **WHY?** Bytecode needs an execution engine.
- **WHAT?** The Python Virtual Machine is the runtime component that carries out Python bytecode instructions.
- **HOW?** Its evaluation loop performs operations and calls runtime services.
- **WHERE?** Inside the Python interpreter process.
- **WHEN?** While bytecode is being executed.
- **WHO?** The Python implementation provides it; the processor executes its native code.
- **WHAT IF?** Execution raises an exception; the runtime unwinds frames and reports it if unhandled.

## 40. What happens when the program crashes?

- **WHY?** The OS must stop faulty work and release its resources.
- **WHAT?** An unhandled exception, native fault, or external termination ends or interrupts the process.
- **HOW?** The runtime may print an error and unwind; a severe fault may terminate the process directly.
- **WHERE?** In the running process and OS process manager.
- **WHEN?** When an error is unhandled, a fatal fault occurs, or a supervisor/user stops it.
- **WHO?** Runtime, OS, and sometimes a supervisor respond.
- **WHAT IF?** Data was not saved or cleanup did not run; recovery requires durable writes and restart-safe design.

Continue with [Compiler](./compiler.md), [Interpreter](./interpreter.md), [Process](./process.md), and [Threads](./threads.md).
