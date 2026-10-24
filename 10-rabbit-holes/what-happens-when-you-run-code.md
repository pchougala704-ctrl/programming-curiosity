# What happens when you run code?

Running code is a chain of steps from a source file to work performed by a processor. The exact sequence depends on the language and operating system, but the following outline gives a useful starting point.

1. A development tool saves source code to a file.
2. A compiler, interpreter, or runtime checks and processes the code.
3. The operating system starts a process and assigns it resources.
4. The processor executes instructions while the runtime and operating system provide services.
5. The program may read input, change data, write output, or communicate with other systems.
6. When it finishes or is stopped, its process resources are released.

Errors can happen at different stages. A syntax error may stop code from being processed; a logic error may let it run but produce the wrong answer; a runtime error may interrupt it while running. Debugging means finding which step or assumption went wrong.

## Related challenge

The [expanded seven-lens answers](./challenge-answers.md#rabbit-holes-seven-lens-answers) also explain what happens when you type `python app.py` and how a program detects another program's crash.
