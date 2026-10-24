# Programming Curiosity Challenge

The goal of this challenge is to build the habit of asking:

> **But how does this actually work?**

Don't search for the answers immediately. Pick questions, discuss them with your team, write down your assumptions, and then investigate how things really work.

Questions are grouped by the repository's numbered folders and, where possible, by the matching topic file. Question numbers are preserved so you can refer to the original challenge. Each topic section links to its reading and answer guide.

## 01 - Programming basics

### [Why programming?](./01-programming-basics/why-programming.md)
[Answers](./01-programming-basics/challenge-answers.md)

1. What exactly is programming?
2. Why was programming invented?
3. Why can't humans directly communicate with a computer?

### [Programming languages](./01-programming-basics/programming-languages.md)
[Answers](./01-programming-basics/challenge-answers.md)

4. How does a computer understand `if`, `for`, `while`, and `function`?
5. Who decides what a programming language can do?
6. Why are there hundreds of programming languages?
7. Why do we need Python, Java, JavaScript, C, C++, Go, Rust, and others?
8. What makes one programming language different from another?
9. Why does a programming language need a compiler or interpreter?

### [How code runs](./01-programming-basics/how-code-runs.md)
[Answers](./01-programming-basics/challenge-answers.md)

10. What actually happens when you run a program?

## 02 - Variables and memory

### [Variables](./02-variables-and-memory/variables.md)
[Answers](./02-variables-and-memory/challenge-answers.md)

11. What happens internally when you write `x = 10`?
12. Where is `10` stored?
13. Where is `x` stored?
14. Is `x` actually the value `10`?
15. What happens when you write `x = 10` and then `x = 20`?
16. What happens to `10`?
17. What happens when you write `a = b = c = 100`?
18. Are `a`, `b`, and `c` three copies of `100`?

### [Memory](./02-variables-and-memory/memory.md)
[Answers](./02-variables-and-memory/challenge-answers.md)

21. What is RAM actually doing while your program runs?
22. What is the difference between RAM and storage?
23. Where does a Python variable live?
24. What is a memory address?
25. Why can't we normally see memory addresses in Python?
30. What happens when your program consumes too much memory?

### [Stack and heap](./02-variables-and-memory/stack-and-heap.md)
[Answers](./02-variables-and-memory/challenge-answers.md)

19. What happens to variables when a function finishes?
26. What is a stack?
27. What is a heap?

### [Garbage collection](./02-variables-and-memory/garbage-collection.md)
[Answers](./02-variables-and-memory/challenge-answers.md)

20. Who cleans unused memory?
28. What is garbage collection?
29. Why doesn't unused memory remain forever?

## 03 - How programs run

Suppose you execute `python app.py`.

### [Process](./03-how-programs-run/process.md)
[Answers](./03-how-programs-run/challenge-answers.md)

31. Who receives this command?
32. How does the operating system know where Python is?
33. What is a process?
40. What happens when the program crashes?

### [Threads](./03-how-programs-run/threads.md)
[Answers](./03-how-programs-run/challenge-answers.md)

34. What is a thread?

### [Interpreter](./03-how-programs-run/interpreter.md)
[Answers](./03-how-programs-run/challenge-answers.md)

35. Where does the Python interpreter run?
36. How does Python read your `.py` file?
37. Does Python directly understand your source code?
39. What is the Python Virtual Machine?

### [Compiler](./03-how-programs-run/compiler.md)
[Answers](./03-how-programs-run/challenge-answers.md)

38. What is bytecode?

## 04 - Internet

### [DNS](./04-internet/dns.md)
[Answers](./04-internet/challenge-answers.md)

41. What happens when you type `google.com` into a browser?
42. How does your computer find Google's server?
43. What is DNS?

### [IP addresses](./04-internet/ip.md)
[Answers](./04-internet/challenge-answers.md)

44. What is an IP address?
45. Why do we need ports?
49. How does your request travel thousands of kilometres?
50. How does the server know where to send the response?

### [HTTP](./04-internet/http.md)
[Answers](./04-internet/challenge-answers.md)

46. What is HTTP?
48. What happens when you click a button on a website?

### [HTTPS](./04-internet/https.md)
[Answers](./04-internet/challenge-answers.md)

47. Why was HTTPS created?

## 05 - APIs

### [What is an API?](./05-apis/what-is-api.md)
[Answers](./05-apis/challenge-answers.md)

51. What exactly is an API?
52. Why can't two applications simply access each other's variables?
53. What happens when a React application calls a Node.js or Python API?

### [Request and response](./05-apis/request-response.md)
[Answers](./05-apis/challenge-answers.md)

54. What is a request?
55. What is a response?
56. Why do APIs commonly use JSON?
59. What happens if an API takes 10 seconds to respond?
60. What happens if the API server is completely down?

### [REST APIs](./05-apis/rest-api.md)
[Answers](./05-apis/challenge-answers.md)

57. What are HTTP methods?
58. Why do we have `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`?

## 06 - Databases

### [SQL](./06-databases/sql.md)
[Answers](./06-databases/challenge-answers.md)

61. Why can't we simply store everything in Python variables?
62. Why do applications need databases?
63. What happens when you click “Save”?
64. Where does the data physically go?
65. What is a table?
66. What is a row?
67. What is a column?
68. Why do we need primary keys?

### [Indexes](./06-databases/indexes.md)
[Answers](./06-databases/challenge-answers.md)

69. Why do we need indexes?

### [NoSQL](./06-databases/nosql.md)
[Answers](./06-databases/challenge-answers.md)

70. What is the difference between SQL and NoSQL?

## 07 - Security

### [Authentication](./07-security/authentication.md)
[Answers](./07-security/challenge-answers.md)

71. How does a website know who you are after login?
72. Where is your password stored?
73. Why shouldn't passwords be stored as plain text?
79. What is a token?

### [Authorization](./07-security/authorization.md)
[Answers](./07-security/challenge-answers.md)

76. What happens if someone changes an API request?
78. How does a server know whether you are authorized?
80. How can one careless line of code expose millions of users?

### [Hashing](./07-security/hashing.md)
[Answers](./07-security/challenge-answers.md)

75. What is hashing?

### [Encryption](./07-security/encryption.md)
[Answers](./07-security/challenge-answers.md)

74. What is encryption?

### Browser security and cross-origin requests
[Answers](./07-security/challenge-answers.md)

77. What is CORS?

## 08 - Cloud and deployment

### [Servers](./08-cloud-and-deployment/server.md)
[Answers](./08-cloud-and-deployment/challenge-answers.md)

91. Where does your application actually run after deployment?
92. What happens when one user uses your application?
95. What is a server?
98. What happens when a server crashes?
99. How does Netflix, YouTube, or Instagram handle millions of users?
100. If you had to build WhatsApp from scratch, what would you need?

### [Cloud computing](./08-cloud-and-deployment/cloud.md)
[Answers](./08-cloud-and-deployment/challenge-answers.md)

96. What is cloud computing?
97. What is AWS or Azure actually providing?

### [Scaling](./08-cloud-and-deployment/scaling.md)
[Answers](./08-cloud-and-deployment/challenge-answers.md)

93. What changes when one million users use your application?
94. Why can't we simply buy one huge computer?
99. How does Netflix, YouTube, or Instagram handle millions of users?

## 09 - Language comparisons

### [Python](./09-language-comparisons/python.md)
[Answers](./09-language-comparisons/challenge-answers.md)

81. Why is Python popular for AI?
87. Is Python actually slower than Java?
89. Can Python call code written in C?

### [JavaScript](./09-language-comparisons/javascript.md)
[Answers](./09-language-comparisons/challenge-answers.md)

82. Why is JavaScript used in browsers?
83. Why is Node.js able to run JavaScript on servers?

### [Java](./09-language-comparisons/java.md)
[Answers](./09-language-comparisons/challenge-answers.md)

84. Why is Java still heavily used in enterprise applications?
87. Is Python actually slower than Java?

### [Python vs JavaScript vs Java](./09-language-comparisons/python-vs-javascript-vs-java.md)
[Answers](./09-language-comparisons/challenge-answers.md)

85. Why is C still important?
86. Why is Rust becoming popular?
88. Does a “faster language” always mean a “better language”?
90. Can different programming languages communicate with each other?

## 10 - Rabbit holes

Follow each question beyond its first answer. Trace the connections between concepts and look for the next question each answer raises. [Read the expanded answers](./10-rabbit-holes/challenge-answers.md).

1. **Variables and memory:** When I type `x = 10`, where exactly does `10` go?  
   Trace: Variable → Object → Memory → RAM → Process → Operating system.
2. **How programs run:** When I type `python app.py`, what happens between pressing Enter and seeing the output?
3. **Internet:** When I enter `google.com`, how does my computer find another computer somewhere in the world?
4. **Security:** When I click Login, how does my password travel from my phone to the server and come back as “Login successful”?
5. **Cloud and deployment:** When I upload a photo to Instagram, where does that photo actually go?
6. **Scaling:** How can millions of people use the same application at the same time?
7. **Databases:** What happens if two users try to modify the same database record at exactly the same time?
8. **Processes:** How does a program know that another program has crashed?
9. **Language comparisons:** If Python, JavaScript, and Java are completely different languages, how can they communicate with each other?
10. **Internet and deployment:** If the Internet disappeared tomorrow, which parts of your application would still work?

## Ask seven questions about anything you learn

Whenever you learn something, ask:

**WHY? → WHAT? → HOW? → WHERE? → WHEN? → WHO? → WHAT IF?**

For example, don't stop at “I learned MongoDB.” Ask:

- **What** is MongoDB?
- **Why** do we use it?
- **How** does it store data?
- **Where** is the data physically stored?
- **When** should I choose MongoDB?
- **Who** uses it in the industry?
- **What if** MongoDB goes down?

A good programmer doesn't just learn answers. A good programmer develops better questions.
