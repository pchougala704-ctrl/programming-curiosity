# Stack and heap

The stack and heap are common ways to describe areas used to manage a program's memory. They are useful mental models, but exact details depend on the language, runtime, and machine.

The **call stack** keeps track of active function calls. Each call has information such as its local variables and where to continue when the function returns. When a function finishes, its call information can be removed. Deep or endless recursion can use more stack space than is available.

The **heap** is an area commonly used for data that needs a more flexible lifetime, such as objects and dynamically sized collections. A program or runtime must manage that data's lifetime, through explicit allocation and release, garbage collection, or other ownership rules.

Do not assume every local value always lives on the stack or every object always lives on the heap. Compilers and runtimes can optimize storage, and language rules vary.

## Challenge questions

- **19.** What happens to variables when a function finishes?
- **26.** What is a stack?
- **27.** What is a heap?

Read the [seven-lens answers](./challenge-answers.md#variables-and-memory-seven-lens-answers).
