# Interpreter

An interpreter is a program that executes instructions from another program. Depending on the language, it may read source code directly, or it may first process it into an intermediate representation such as bytecode.

Interpreted execution can make it convenient to try code quickly, but it is not automatically slower than compiled execution. Real performance depends on the implementation, the program, and techniques such as just-in-time compilation.

Many popular languages use a mixture of approaches. For example, a runtime might translate source code to bytecode, then interpret it and compile frequently used sections into machine code.

## Challenge questions

- **35.** Where does the Python interpreter run?
- **36.** How does Python read your `.py` file?
- **37.** Does Python directly understand your source code?
- **39.** What is the Python Virtual Machine?

Read the [seven-lens answers](./challenge-answers.md#how-programs-run-seven-lens-answers).
