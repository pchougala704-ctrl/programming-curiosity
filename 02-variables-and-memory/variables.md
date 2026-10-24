# Variables

A variable is a name a program uses to refer to a value. Instead of repeatedly writing a number or piece of text directly, a program can give it a meaningful name and use that name in later calculations.

```python
score = 10
score = score + 5
print(score)  # 15
```

Here, `score` refers to the current value. In many languages, assigning a new value changes what the name refers to. The exact rules differ: some languages require a variable's type to be declared, while others infer or allow it to change.

Variables help make programs easier to understand and update. Names like `total_price` explain intent better than unexplained values scattered throughout the code.

## Challenge questions

- **11.** What happens internally when you write `x = 10`?
- **12.** Where is `10` stored?
- **13.** Where is `x` stored?
- **14.** Is `x` actually the value `10`?
- **15.** What happens when you write `x = 10` and then `x = 20`?
- **16.** What happens to `10`?
- **17.** What happens when you write `a = b = c = 100`?
- **18.** Are `a`, `b`, and `c` three copies of `100`?

Read the [seven-lens answers](./challenge-answers.md#variables-and-memory-seven-lens-answers).

The [rabbit-hole answer](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers) also traces `x = 10` from a variable name through an object, memory, RAM, process, and operating system.

### Related rabbit-hole question

**When I type `x = 10`, where exactly does `10` go?**

Read the [seven-lens rabbit-hole answer](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers).
