# PwC GenAI / AI Engineer assessment: six-hour training README

Prepared: 1 October 2026. Scope: the job description supplied in this conversation, including Python, React/TypeScript, FastAPI, agentic AI, LangChain/LangGraph/CrewAI, SQL/NoSQL, Docker/Kubernetes, cloud and CI/CD.

**This is an original practice bank, not an official PwC paper or leaked question set.** No source can establish every possible assessment question. Topic priority below is a study recommendation, not a verified percentage distribution. Framework details can vary by installed version; focus on concepts and check version-specific syntax against official documentation.

## What public reports actually establish

A public candidate discussion describes an assessment containing Python output questions and agentic reasoning/definitions without coding. Another commenter describes 30 MCQs plus Python and easy-to-medium DSA coding. These are unverified personal reports and do not establish your assessment's exact format or its exact questions. Your invitation and recruiter instructions are authoritative for format and duration.

Source: [PwC GenAI Interview Assessment — candidate discussion](https://www.reddit.com/r/PWCindiaunofficial/comments/1v508ig/pwc_genai_interview_assessment_what_should_i/). Independently checked on 1 October 2026. The practice questions below were created for preparation; none is claimed to have appeared at PwC.

## Six-hour plan — 360 minutes including breaks

| Elapsed time | Minutes | Work |
|---|---:|---|
| 00:00–01:05 | 65 | Python primer, fundamentals and output questions; trace before running |
| 01:05–01:10 | 5 | Break |
| 01:10–02:10 | 60 | Agent architecture, LangChain, LangGraph and CrewAI |
| 02:10–02:15 | 5 | Break |
| 02:15–03:00 | 45 | LLMs, RAG, prompt injection and evaluation |
| 03:00–03:40 | 40 | FastAPI, Pydantic, HTTP and API security |
| 03:40–03:45 | 5 | Break |
| 03:45–04:20 | 35 | React, JavaScript, TypeScript and React Native |
| 04:20–04:45 | 25 | SQL/NoSQL and data modeling |
| 04:45–05:05 | 20 | Docker, Kubernetes, cloud, CI/CD and code review |
| 05:05–05:35 | 30 | Closed-book mock test: 30 questions |
| 05:35–06:00 | 25 | Review mock mistakes, final traps and optional coding drills |

## How to use this file

1. Read each short primer, then attempt its questions without expanding the answer.
2. Record an answer and confidence: high, medium or low. A lucky guess still needs revision.
3. Expand the answer and explain why the other options are weaker.
4. For output questions, track references, mutation, scope and execution order manually.
5. Finish the mixed mock under a 30-minute timer. There is no assumed negative marking: follow your actual assessment rules.
6. Revisit wrong and low-confidence answers first. If short on time, prioritize Python outputs, tool calling, graph state/reducers, persistence, RAG and async behavior.

## Contents

- [Python fundamentals and OOP](#python-fundamentals-and-oop)
- [Python output questions](#python-output-questions)
- [Agentic AI and architecture](#agentic-ai-and-architecture)
- [LangChain and LangGraph](#langchain-and-langgraph)
- [LLMs, RAG and evaluation](#llms-rag-and-evaluation)
- [FastAPI, Pydantic, HTTP and API security](#fastapi-pydantic-http-and-api-security)
- [React, JavaScript, TypeScript and React Native](#react-javascript-typescript-and-react-native)
- [SQL, NoSQL and data modeling](#sql-nosql-and-data-modeling)
- [Docker, Kubernetes, cloud, CI/CD and professional judgment](#docker-kubernetes-cloud-cicd-and-professional-judgment)
- [Timed mock test](#timed-mock-test)
- [Coding drills](#coding-drills)
- [Final revision sheet](#final-revision-sheet)
- [Sources and further reading](#sources-and-further-reading)

## Python fundamentals and OOP

Revise objects and references before memorizing syntax. Assignment binds names; it does not copy objects. Lists, dictionaries and sets are mutable. Tuples are immutable containers, but may contain mutable objects. Hashability, rather than immutability alone, determines whether an object can be a dictionary key.

Functions are objects. Default argument expressions are evaluated when the function is defined. Closures capture variables; use a default argument when you need to capture the current loop value. Python type hints are not automatically enforced at runtime. Assume Python 3 for this guide.

### Q001. Which comparison checks whether two names refer to the same object?

- **A.** `is`
- **B.** `==`
- **C.** `!=`
- **D.** `in`

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Equality compares values; identity compares objects.

</details>

### Q002. Which built-in container is immutable?

- **A.** List
- **B.** Dictionary
- **C.** Set
- **D.** Tuple

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A tuple cannot have its element references reassigned; contained objects can still mutate.

</details>

### Q003. Which is a valid dictionary key?

- **A.** `[1, 2]`
- **B.** `{"a": 1}`
- **C.** `(1, 2)`
- **D.** `{1, 2}`

<details>
<summary>Answer and explanation</summary>

**Answer: C.** The tuple contains only hashable elements; the other choices are unhashable.

</details>

### Q004. What does `d.get("missing", 0)` return when the key is absent?

- **A.** `None` always
- **B.** `0`
- **C.** `KeyError`
- **D.** The first dictionary value

<details>
<summary>Answer and explanation</summary>

**Answer: B.** get uses the supplied default without inserting the key.

</details>

### Q005. When are default function argument expressions evaluated?

- **A.** When the function is defined
- **B.** On every call
- **C.** Only on the first call
- **D.** After returning

<details>
<summary>Answer and explanation</summary>

**Answer: A.** A mutable default can therefore be shared across calls.

</details>

### Q006. What does `*args` collect in a function definition?

- **A.** Extra keyword arguments as a dictionary
- **B.** All global variables
- **C.** Only string arguments
- **D.** Extra positional arguments as a tuple

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Positional arguments are packed into a tuple.

</details>

### Q007. What does `**kwargs` collect?

- **A.** Positional arguments as a list
- **B.** Return values as a tuple
- **C.** Extra keyword arguments as a dictionary
- **D.** Exceptions as a set

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Keyword names map to their provided values.

</details>

### Q008. What is the main difference between shallow and deep copying?

- **A.** Shallow copying always copies every nested object
- **B.** Deep copying recursively copies nested objects
- **C.** Deep copying only copies the outer object
- **D.** They are identical for all objects

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A shallow copy retains references to nested objects; deep copy tracks and copies supported nested structures.

</details>

### Q009. Which keyword makes an ordinary function a generator function?

- **A.** `yield`
- **B.** `await`
- **C.** `pass`
- **D.** `global`

<details>
<summary>Answer and explanation</summary>

**Answer: A.** A generator yields values while retaining suspended execution state.

</details>

### Q010. What happens after a generator is exhausted?

- **A.** It automatically restarts
- **B.** It returns the last value forever
- **C.** It becomes a list
- **D.** Further next calls raise StopIteration

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A generator is a single-pass iterator.

</details>

### Q011. What is a decorator usually used for?

- **A.** Declaring a database index
- **B.** Converting all variables to strings
- **C.** Wrapping or transforming a callable
- **D.** Allocating a separate process

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Decorators can add logging, authorization or caching around functions.

</details>

### Q012. What does `with open(...) as f` help ensure?

- **A.** The file is never buffered
- **B.** The file is closed when the block exits
- **C.** Every read is asynchronous
- **D.** The file is encrypted

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The context manager performs cleanup even if the block raises an exception.

</details>

### Q013. When does a try statement's `else` block run?

- **A.** When its try block completes normally without an exception
- **B.** After any exception
- **C.** Before the try block
- **D.** Only when finally raises

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Use else for work that should run only after successful try execution.

</details>

### Q014. When does a for loop's `else` block run on normal completion?

- **A.** Only after break
- **B.** Before the first iteration
- **C.** On every iteration
- **D.** When the loop finishes without break

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Loop else is skipped when break terminates the loop.

</details>

### Q015. What does `enumerate(items)` provide?

- **A.** Sorted values only
- **B.** Unique elements only
- **C.** Index and element pairs
- **D.** A deep copy

<details>
<summary>Answer and explanation</summary>

**Answer: C.** The default starting index is zero.

</details>

### Q016. What happens to dictionary insertion order in modern Python 3.7+?

- **A.** It is always alphabetical
- **B.** It is preserved
- **C.** It is randomized on each iteration
- **D.** Dictionaries cannot be iterated

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Do not confuse insertion order with key sorting.

</details>

### Q017. What is the typical average-case complexity of a dictionary lookup?

- **A.** O(1)
- **B.** O(n squared)
- **C.** O(n log n)
- **D.** Always O(n)

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Hash tables generally provide constant average lookup; pathological cases can be slower.

</details>

### Q018. What does an instance method's `self` conventionally refer to?

- **A.** The parent class only
- **B.** A global variable
- **C.** The module loader
- **D.** The current instance

<details>
<summary>Answer and explanation</summary>

**Answer: D.** The instance is supplied when the method is called through an object.

</details>

### Q019. What does `@classmethod` receive as its first argument?

- **A.** The instance only
- **B.** No argument
- **C.** The class
- **D.** The current module

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Conventionally named cls; it is useful for alternate constructors.

</details>

### Q020. What does `@staticmethod` imply?

- **A.** Every call creates a new object
- **B.** No automatic self or cls argument
- **C.** The method cannot return data
- **D.** It runs in a background thread

<details>
<summary>Answer and explanation</summary>

**Answer: B.** It groups related functionality without automatic instance/class binding.

</details>

### Q021. What is method overriding?

- **A.** A subclass supplies its own implementation of an inherited method
- **B.** Defining two global variables
- **C.** Copying a list
- **D.** Sorting class names

<details>
<summary>Answer and explanation</summary>

**Answer: A.** The subclass implementation changes inherited behavior.

</details>

### Q022. What does `super()` commonly support?

- **A.** Calling every method in every class
- **B.** Disabling inheritance
- **C.** Creating a global instance
- **D.** Calling the next implementation in the method resolution order

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Cooperative multiple inheritance follows Python's MRO.

</details>

### Q023. What does `nonlocal` allow in a nested function?

- **A.** Making a value immutable
- **B.** Importing a module
- **C.** Rebinding a variable in an enclosing non-global function scope
- **D.** Creating a process

<details>
<summary>Answer and explanation</summary>

**Answer: C.** It differs from global, which targets the module scope.

</details>

### Q024. What is a virtual environment primarily for?

- **A.** Encrypting Python source
- **B.** Isolating project Python dependencies
- **C.** Running Kubernetes pods
- **D.** Improving algorithm complexity

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Isolation prevents projects from sharing incompatible package sets.

</details>

### Q025. What is the main purpose of `if __name__ == "__main__":`?

- **A.** Run a block when a module is executed as the main program
- **B.** Run a block on every import only
- **C.** Declare a class
- **D.** Guarantee multithreading

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Imported modules usually have their module name instead of __main__.

</details>

### Q026. What does calling an `async def` function normally produce?

- **A.** Its final return value immediately
- **B.** A new OS process
- **C.** A generator list
- **D.** A coroutine object

<details>
<summary>Answer and explanation</summary>

**Answer: D.** The coroutine needs to be awaited or scheduled to execute.

</details>

### Q027. Which operation can block an asyncio event loop?

- **A.** Awaiting asyncio.sleep
- **B.** Awaiting a nonblocking network client
- **C.** Calling time.sleep inside an async task
- **D.** Scheduling another coroutine

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Synchronous blocking work prevents other tasks on that event-loop thread from progressing.

</details>

### Q028. Which workload often benefits from asynchronous I/O?

- **A.** Pure Python CPU-heavy arithmetic on one event loop
- **B.** Many network requests waiting on responses
- **C.** GPU model training solely because async is used
- **D.** Sorting a small in-memory list solely because async is used

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Async concurrency overlaps waits; it does not itself add CPU parallelism.

</details>

### Q029. For a standard GIL-enabled CPython build, which is generally better for CPU-heavy pure Python parallel work?

- **A.** Multiple processes
- **B.** More threads alone
- **C.** More await keywords
- **D.** Longer network timeouts

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Processes can use multiple cores; free-threaded builds and native code have different behavior.

</details>

### Q030. What is `pytest` principally used for?

- **A.** Database replication
- **B.** Container networking
- **C.** Tokenization
- **D.** Automated Python testing

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Test cases check behavior and regressions.

</details>

## Python output questions

Assume each snippet runs independently in Python 3 with no preceding state. For options containing `/`, the slash separates output lines; the expanded answer shows the original line breaks.

### Q031. What is the output or exception? — Aliasing

```python
a = [1, 2]
b = a
b.append(3)
print(a)
```

- **A.** `[1, 2]`
- **B.** `[3]`
- **C.** `[1, 2, 3]`
- **D.** `TypeError`

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Both names refer to the same list.

</details>

### Q032. What is the output or exception? — Equality and identity

```python
a = [1, 2]
b = [1, 2]
print(a == b, a is b)
```

- **A.** `True True`
- **B.** `True False`
- **C.** `False True`
- **D.** `False False`

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The values match but the lists are separate objects.

</details>

### Q033. What is the output or exception? — Shallow copy

```python
a = [[1], [2]]
b = a.copy()
b[0].append(9)
print(a)
```

- **A.** `[[1, 9], [2]]`
- **B.** `[[1], [2]]`
- **C.** `[[9], [2]]`
- **D.** `TypeError`

<details>
<summary>Answer and explanation</summary>

**Answer: A.** The copied outer list shares its inner lists.

</details>

### Q034. What is the output or exception? — Deep copy

```python
import copy
a = [[1], [2]]
b = copy.deepcopy(a)
b[0].append(9)
print(a)
```

- **A.** `[[1, 9], [2]]`
- **B.** `[[9], [2]]`
- **C.** `TypeError`
- **D.** `[[1], [2]]`

<details>
<summary>Answer and explanation</summary>

**Answer: D.** The supported nested lists are independently copied.

</details>

### Q035. What is the output or exception? — Mutable default

```python
def f(x, values=[]):
    values.append(x)
    return values
print(f(1))
print(f(2))
```

- **A.** `[1] / [2]`
- **B.** `[1, 2] / [1, 2]`
- **C.** `[1] / [1, 2]`
- **D.** `TypeError`

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Both calls use the same default list.

Expected output:

```text
[1]
[1, 2]
```

</details>

### Q036. What is the output or exception? — Safe default

```python
def f(x, values=None):
    if values is None:
        values = []
    values.append(x)
    return values
print(f(1))
print(f(2))
```

- **A.** `[1] / [1, 2]`
- **B.** `[1] / [2]`
- **C.** `[] / []`
- **D.** `NameError`

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A new list is created in each call without an explicit list.

Expected output:

```text
[1]
[2]
```

</details>

### Q037. What is the output or exception? — Slicing

```python
print([0, 1, 2, 3, 4][1:4:2])
```

- **A.** `[1, 3]`
- **B.** `[1, 2, 3]`
- **C.** `[1, 3, 4]`
- **D.** `[2, 4]`

<details>
<summary>Answer and explanation</summary>

**Answer: A.** The slice includes index 1 and index 3; stop index 4 is excluded.

</details>

### Q038. What is the output or exception? — Negative indexing

```python
print("python"[-2])
```

- **A.** `n`
- **B.** `h`
- **C.** `IndexError`
- **D.** `o`

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Negative indices count from the end.

</details>

### Q039. What is the output or exception? — Comprehension

```python
print([x * x for x in range(5) if x % 2 == 0])
```

- **A.** `[0, 1, 4, 9, 16]`
- **B.** `[1, 9]`
- **C.** `[0, 4, 16]`
- **D.** `[2, 4]`

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Even x values are 0, 2 and 4.

</details>

### Q040. What is the output or exception? — List mutation return value

```python
a = [3, 1, 2]
b = a.sort()
print(a, b)
```

- **A.** `[3, 1, 2] [1, 2, 3]`
- **B.** `[1, 2, 3] None`
- **C.** `[1, 2, 3] [1, 2, 3]`
- **D.** `TypeError`

<details>
<summary>Answer and explanation</summary>

**Answer: B.** sort mutates the list and returns None.

</details>

### Q041. What is the output or exception? — Sorted copy

```python
a = [3, 1, 2]
b = sorted(a)
print(a, b)
```

- **A.** `[3, 1, 2] [1, 2, 3]`
- **B.** `[1, 2, 3] None`
- **C.** `[1, 2, 3] [1, 2, 3]`
- **D.** `[3, 1, 2] None`

<details>
<summary>Answer and explanation</summary>

**Answer: A.** sorted creates a new list.

</details>

### Q042. What is the output or exception? — Tuple containing a list

```python
t = ([1], 2)
t[0].append(3)
print(t)
```

- **A.** `([1], 2)`
- **B.** `TypeError`
- **C.** `([3], 2)`
- **D.** `([1, 3], 2)`

<details>
<summary>Answer and explanation</summary>

**Answer: D.** The tuple is immutable, but its contained list can change.

</details>

### Q043. What is the output or exception? — Boolean operands

```python
print([] or "fallback")
print("hello" and 7)
```

- **A.** `False / True`
- **B.** `[] / hello`
- **C.** `fallback / 7`
- **D.** `fallback / hello`

<details>
<summary>Answer and explanation</summary>

**Answer: C.** and/or return operands selected by truthiness.

Expected output:

```text
fallback
7
```

</details>

### Q044. What is the output or exception? — Floor division

```python
print(-7 // 2, -7 % 2)
```

- **A.** `-3 -1`
- **B.** `-4 1`
- **C.** `-3 1`
- **D.** `-4 -1`

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Floor division rounds downward; modulo satisfies a = b*q + r.

</details>

### Q045. What is the output or exception? — Loop else

```python
for i in range(2):
    print(i)
else:
    print("done")
```

- **A.** `0 / 1 / done`
- **B.** `0 / 1`
- **C.** `done`
- **D.** `1 / 2 / done`

<details>
<summary>Answer and explanation</summary>

**Answer: A.** The loop finishes without break, so else runs.

Expected output:

```text
0
1
done
```

</details>

### Q046. What is the output or exception? — Loop break

```python
for i in range(3):
    if i == 1:
        break
    print(i)
else:
    print("done")
```

- **A.** `0 / done`
- **B.** `0 / 1 / 2 / done`
- **C.** `1`
- **D.** `0`

<details>
<summary>Answer and explanation</summary>

**Answer: D.** break skips the loop else.

</details>

### Q047. What is the output or exception? — Finally return

```python
def f():
    try:
        return 1
    finally:
        return 2
print(f())
```

- **A.** `1`
- **B.** `None`
- **C.** `2`
- **D.** `SyntaxError`

<details>
<summary>Answer and explanation</summary>

**Answer: C.** The finally return overrides the earlier return; avoid this pattern.

</details>

### Q048. What is the output or exception? — Closure binding

```python
functions = [lambda: i for i in range(3)]
print([f() for f in functions])
```

- **A.** `[0, 1, 2]`
- **B.** `[2, 2, 2]`
- **C.** `[0, 0, 0]`
- **D.** `NameError`

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The lambdas read the final value of the shared captured variable.

</details>

### Q049. What is the output or exception? — Capture current value

```python
functions = [lambda i=i: i for i in range(3)]
print([f() for f in functions])
```

- **A.** `[0, 1, 2]`
- **B.** `[2, 2, 2]`
- **C.** `[0, 0, 0]`
- **D.** `TypeError`

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Each default argument captures the current i at function creation.

</details>

### Q050. What is the output or exception? — Generator exhaustion

```python
g = (x * 2 for x in range(3))
print(list(g))
print(list(g))
```

- **A.** `[0, 2, 4] / [0, 2, 4]`
- **B.** `[] / []`
- **C.** `TypeError`
- **D.** `[0, 2, 4] / []`

<details>
<summary>Answer and explanation</summary>

**Answer: D.** The first list consumes the generator.

Expected output:

```text
[0, 2, 4]
[]
```

</details>

### Q051. What is the output or exception? — Dictionary overwrite

```python
d = {"a": 1, "a": 2}
print(d["a"], len(d))
```

- **A.** `1 2`
- **B.** `2 2`
- **C.** `2 1`
- **D.** `KeyError`

<details>
<summary>Answer and explanation</summary>

**Answer: C.** The later value replaces the earlier value for the same key.

</details>

### Q052. What is the output or exception? — None and truthiness

```python
print(bool("False"), bool(""), bool(None))
```

- **A.** `False False False`
- **B.** `True False False`
- **C.** `True True False`
- **D.** `False True True`

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A nonempty string is truthy regardless of its spelling.

</details>

### Q053. What is the output or exception? — Shared nested rows

```python
rows = [[0] * 2] * 2
rows[0][0] = 9
print(rows)
```

- **A.** `[[9, 0], [9, 0]]`
- **B.** `[[9, 0], [0, 0]]`
- **C.** `[[0, 0], [9, 0]]`
- **D.** `TypeError`

<details>
<summary>Answer and explanation</summary>

**Answer: A.** List multiplication repeats references to the same inner row.

</details>

### Q054. What is the output or exception? — Scope error

```python
x = 10
def f():
    print(x)
    x = 20
f()
```

- **A.** `10`
- **B.** `20`
- **C.** `None`
- **D.** `UnboundLocalError`

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Assignment makes x local throughout the function unless declared otherwise.

</details>

### Q055. What is the output or exception? — Async execution order

```python
import asyncio
async def work():
    print("B")
    await asyncio.sleep(0)
    print("C")
async def main():
    task = asyncio.create_task(work())
    print("A")
    await task
asyncio.run(main())
```

- **A.** `B / A / C`
- **B.** `A / C / B`
- **C.** `A / B / C`
- **D.** `C / B / A`

<details>
<summary>Answer and explanation</summary>

**Answer: C.** The current task prints A before yielding control to the scheduled task.

Expected output:

```text
A
B
C
```

</details>

## Agentic AI and architecture

An agent selects actions using a model and observes results in a bounded loop. A workflow can instead follow explicitly programmed steps. Neither pattern is automatically better: predictable tasks often benefit from deterministic workflows.

Tool calling typically means the model produces a structured request; the application validates authorization and arguments, executes the tool, and feeds back a result. Treat tool responses and retrieved text as untrusted inputs. Use budgets, timeouts, stopping rules, audit records and approval gates for consequential actions.

### Q056. Which best distinguishes an agent from a fixed sequence of LLM calls?

- **A.** It always has more parameters
- **B.** It can dynamically choose actions based on observations
- **C.** It must use multiple GPUs
- **D.** It must never call an API

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Agentic control can adapt the next step instead of following only a predetermined chain.

</details>

### Q057. What does ReAct combine?

- **A.** Reasoning and acting
- **B.** Retrieval and activation functions
- **C.** React components and CSS
- **D.** Regression and accuracy

<details>
<summary>Answer and explanation</summary>

**Answer: A.** The pattern interleaves action selection with observations.

</details>

### Q058. Who usually executes an LLM-requested tool call?

- **A.** The tokenizer
- **B.** The prompt string itself
- **C.** The embedding vector
- **D.** The application or agent runtime

<details>
<summary>Answer and explanation</summary>

**Answer: D.** The model emits a request; executable application code performs the action.

</details>

### Q059. Why define a tool's input schema?

- **A.** To guarantee the tool can never fail
- **B.** To increase the model context window
- **C.** To specify and validate its expected arguments
- **D.** To bypass authorization

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Schemas help constrain structure but do not replace permission checks.

</details>

### Q060. Which control best restricts an agent's database access?

- **A.** Unrestricted admin credentials in the prompt
- **B.** A least-privilege tool with authorization and validated queries
- **C.** Allowing arbitrary SQL from users
- **D.** Relying only on a polite instruction

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Security must be enforced outside model text generation.

</details>

### Q061. What is a supervisor in a multi-agent architecture?

- **A.** A coordinator that routes work among specialist agents
- **B.** A vector database index
- **C.** A GPU scheduler only
- **D.** An HTML component

<details>
<summary>Answer and explanation</summary>

**Answer: A.** It orchestrates delegation and combines or routes results.

</details>

### Q062. When might a single agent be preferable to multiple agents?

- **A.** Whenever the system must be distributed globally
- **B.** Whenever each task has incompatible security domains
- **C.** When independent specialists must run in parallel
- **D.** When the task is simple and coordination overhead is unnecessary

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Additional agents introduce communication cost and more failure paths.

</details>

### Q063. An agent repeatedly calls a tool without making progress. What helps?

- **A.** Unlimited recursive calls
- **B.** Raising temperature alone
- **C.** Step budgets and termination conditions
- **D.** Removing all logging

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Bounded execution prevents runaway latency and expense.

</details>

### Q064. Which is an example of human-in-the-loop?

- **A.** Asking another LLM to approve everything
- **B.** Pausing before a sensitive action for explicit human approval
- **C.** Logging the action only after completion
- **D.** Disabling monitoring

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Human approval is a distinct external decision point.

</details>

### Q065. What should happen when required approval is denied?

- **A.** Follow a defined rejection path without performing the action
- **B.** Execute anyway because the model chose it
- **C.** Retry until someone accidentally approves
- **D.** Hide the rejection from the audit log

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Approval gates must control actual execution.

</details>

### Q066. Which pattern reduces duplicate effects when a tool request is retried?

- **A.** Randomizing each request ID
- **B.** Increasing token limits
- **C.** Removing the request log
- **D.** Idempotency keys checked by the executing service

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Reuse the same operation key so the service can detect duplicates.

</details>

### Q067. When is automatic retry most appropriate?

- **A.** Invalid credentials without any change
- **B.** A denied permission
- **C.** A transient failure of an operation that is safe to retry
- **D.** A non-idempotent operation with an unknown outcome and no deduplication

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Retry policy should consider error type and duplicate side effects.

</details>

### Q068. A tool times out after submitting an action. What is the safest next step?

- **A.** Assume the action did not happen
- **B.** Check the operation status before resubmitting
- **C.** Always switch providers and duplicate it
- **D.** Delete all records

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Timeout does not prove that the remote service failed to execute.

</details>

### Q069. What is prompt injection?

- **A.** Untrusted content attempting to redirect model behavior
- **B.** Normal compression of tokens
- **C.** Encrypting an embedding
- **D.** An HTTP authentication scheme

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Retrieved documents or tool output can contain hostile instructions.

</details>

### Q070. Which data should generally be excluded from ordinary agent logs?

- **A.** Redacted tool names
- **B.** Operation durations
- **C.** Non-sensitive status codes
- **D.** Raw credentials and unnecessary personal information

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Log useful diagnostics while minimizing sensitive exposure.

</details>

### Q071. What is a useful end-to-end agent metric?

- **A.** Token count alone
- **B.** Number of agents alone
- **C.** Successful task completion under cost and safety constraints
- **D.** Number of prompts alone

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Measure outcomes, latency, costs and unsafe actions together.

</details>

### Q072. What does a circuit breaker do?

- **A.** Retries forever
- **B.** Temporarily blocks calls after repeated failures and later probes recovery
- **C.** Makes every API synchronous
- **D.** Encrypts the database

<details>
<summary>Answer and explanation</summary>

**Answer: B.** It prevents a failing dependency from being overloaded.

</details>

### Q073. What is a good fallback when an agent cannot complete a task safely?

- **A.** Return a clear limitation or route to a human
- **B.** Invent the missing result
- **C.** Claim success without evidence
- **D.** Bypass validation

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Graceful failure preserves correctness and trust.

</details>

### Q074. What is a CrewAI crew conceptually?

- **A.** A Python virtual environment
- **B.** A database migration
- **C.** A browser-only UI library
- **D.** A team of agents collaborating on tasks

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Crews organize agents, tasks and execution processes.

</details>

### Q075. What is a CrewAI task primarily?

- **A.** A cloud region
- **B.** A secret key
- **C.** A defined unit of work with expected output
- **D.** A vector similarity metric

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Explicit task outcomes help coordinate the agent team.

</details>

## LangChain and LangGraph

LangChain supplies model, tool and application integrations. LangGraph describes execution as nodes connected by edges over shared state. Nodes usually return partial state updates; a reducer determines how updates to a state key are combined. Without a reducer, an update generally replaces that key's value.

Checkpointers persist thread state; stores support application-defined information across threads. An in-memory saver is useful for development but loses data on process restart. Durable resumption does not automatically make an external write execute exactly once: make side effects idempotent.

### Q076. What is a LangGraph node typically?

- **A.** A mandatory separate server
- **B.** A computation that reads state and returns updates
- **C.** A vector dimension
- **D.** A SQL index

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A node can be an ordinary function, a model call or a tool step.

</details>

### Q077. What does an edge represent?

- **A.** A transition between graph steps
- **B.** An embedding coordinate
- **C.** A database primary key
- **D.** A model parameter

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Edges specify control flow.

</details>

### Q078. What is a conditional edge used for?

- **A.** Making all nodes run in every case
- **B.** Encrypting state
- **C.** Removing tool arguments
- **D.** Routing based on current state or output

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A routing function selects the next destination.

</details>

### Q079. What is graph state?

- **A.** Only the model's training weights
- **B.** A browser cookie only
- **C.** Information carried through workflow execution
- **D.** The GPU temperature

<details>
<summary>Answer and explanation</summary>

**Answer: C.** It can contain messages, intermediate results and application fields.

</details>

### Q080. What is a reducer used for?

- **A.** Reducing all tokens to one number
- **B.** Defining how updates to a state field combine
- **C.** Deleting every earlier message
- **D.** Choosing a cloud region

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Reducers can append lists, add numbers or implement custom merging.

</details>

### Q081. Two parallel nodes update a shared field. What should the design specify?

- **A.** A valid combining strategy or non-conflicting writes
- **B.** Arbitrary last writer always wins safely
- **C.** No state schema
- **D.** A higher model temperature

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Uncoordinated concurrent updates can fail or produce undesired state.

</details>

### Q082. What does `compile()` commonly produce from a LangGraph builder?

- **A.** Trained model weights
- **B.** A Docker image
- **C.** A React component
- **D.** An executable graph

<details>
<summary>Answer and explanation</summary>

**Answer: D.** The compiled graph can be invoked or streamed.

</details>

### Q083. What do START and END represent?

- **A.** Cloud server hostnames
- **B.** Embedding vectors
- **C.** Graph entry and termination markers
- **D.** Python package versions

<details>
<summary>Answer and explanation</summary>

**Answer: C.** They describe where execution begins and ends.

</details>

### Q084. What does a checkpointer primarily persist?

- **A.** Only LLM model weights
- **B.** Thread-scoped graph state snapshots
- **C.** Frontend CSS
- **D.** Cloud billing accounts

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Checkpoints support continuation and recovery within a thread.

</details>

### Q085. Why provide `thread_id` when using a checkpointer?

- **A.** To identify the execution/conversation thread
- **B.** To specify CPU core count
- **C.** To disable memory
- **D.** To choose an embedding model

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Reusing a thread identifier accesses that thread's checkpoint history.

</details>

### Q086. What is a LangGraph store typically suited for?

- **A.** Replacing all authorization
- **B.** Training a new tokenizer
- **C.** Browser rendering
- **D.** Application-defined memory across threads

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A store can hold durable preferences or facts separately from thread state.

</details>

### Q087. Does an in-memory checkpointer survive a process restart?

- **A.** Yes without configuration
- **B.** Only if temperature is zero
- **C.** No
- **D.** Only if all nodes are async

<details>
<summary>Answer and explanation</summary>

**Answer: C.** RAM data is lost; use durable storage when restart recovery matters.

</details>

### Q088. What does `interrupt()` enable in LangGraph?

- **A.** Killing every running graph
- **B.** Pausing for external input or approval
- **C.** Changing model weights
- **D.** Creating a Kubernetes deployment

<details>
<summary>Answer and explanation</summary>

**Answer: B.** With persistence configured, execution can resume with supplied input.

</details>

### Q089. Why must code before an interrupt be designed carefully?

- **A.** The node can restart from its beginning on resumption
- **B.** It never executes
- **C.** It automatically executes exactly once externally
- **D.** It always runs on a different cloud

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Replayed code can duplicate side effects unless designed safely.

</details>

### Q090. What is `Command(resume=...)` associated with?

- **A.** Deploying a frontend
- **B.** Training an embedding model
- **C.** Resetting a database password
- **D.** Supplying a value to resume an interrupted execution

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Resume uses the saved thread/checkpoint context.

</details>

### Q091. What does `add_messages` help manage?

- **A.** Encrypting every message
- **B.** Running SQL joins
- **C.** Merging message updates with message-ID awareness
- **D.** Converting messages to images

<details>
<summary>Answer and explanation</summary>

**Answer: C.** It can append new messages and replace matching IDs.

</details>

### Q092. What is streaming useful for?

- **A.** Guaranteeing no model errors
- **B.** Delivering incremental outputs or execution updates
- **C.** Removing all network latency
- **D.** Increasing model training data

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Clients can observe progress instead of waiting for only a final result.

</details>

### Q093. What is LCEL's pipe operator commonly used for?

- **A.** Composing runnable steps into a pipeline
- **B.** Starting OS processes
- **C.** Performing a SQL union
- **D.** Declaring React props

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Runnable components can be composed into sequential transformations.

</details>

### Q094. What does binding tools to a chat model primarily supply?

- **A.** Automatic permission to execute anything
- **B.** New model training weights
- **C.** Unlimited retries
- **D.** Tool descriptions and argument schemas

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Tool execution and enforcement remain application responsibilities.

</details>

### Q095. How can a tools node route back to an agent node?

- **A.** By renaming the Python file
- **B.** By changing the vector dimensions
- **C.** An explicit edge back to the agent
- **D.** By disabling the state schema

<details>
<summary>Answer and explanation</summary>

**Answer: C.** The graph supports iterative model-tool cycles.

</details>

## LLMs, RAG and evaluation

RAG has two phases. Indexing: load documents, split them, embed chunks and store representations plus metadata. Querying: process the question, retrieve candidates, optionally rerank, pass selected evidence to the model, generate and validate the answer.

Retrieval does not guarantee truth. Documents may be irrelevant, stale or malicious. Evaluate retrieval relevance separately from answer groundedness. Low temperature typically reduces sampling variability; it does not guarantee identical output or factual accuracy.

### Q096. What does RAG stand for?

- **A.** Recursive Agent Graph
- **B.** Retrieval-Augmented Generation
- **C.** Random Answer Generation
- **D.** Relational API Gateway

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Retrieval provides external evidence for generation.

</details>

### Q097. What is an embedding?

- **A.** A numerical vector representation of data
- **B.** A secret authentication token
- **C.** A complete SQL table
- **D.** A Docker layer

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Embeddings represent properties useful for similarity and other tasks.

</details>

### Q098. Why chunk documents before indexing?

- **A.** To guarantee that every answer is true
- **B.** To avoid using any storage
- **C.** To remove all metadata
- **D.** To retrieve useful portions within practical context limits

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Chunk size affects context, specificity and retrieval quality.

</details>

### Q099. What does chunk overlap aim to preserve?

- **A.** Database write locks
- **B.** Model training weights
- **C.** Context spanning chunk boundaries
- **D.** Authentication state

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Overlap can help continuity but increases duplication and storage.

</details>

### Q100. What is a reranker used for?

- **A.** Encrypting all retrieved text
- **B.** Reordering retrieved candidates by relevance to the query
- **C.** Replacing the tokenizer
- **D.** Building a Docker image

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A second-stage model scores a smaller candidate set more precisely.

</details>

### Q101. What is hybrid retrieval?

- **A.** Combining lexical and vector-based search
- **B.** Using two GPUs exclusively
- **C.** Joining two prompt strings only
- **D.** Always using two LLMs

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Lexical search helps exact terms; vector search helps semantic matches.

</details>

### Q102. Why filter retrieval by user permissions?

- **A.** To increase temperature
- **B.** To remove all citations
- **C.** To eliminate vector storage
- **D.** To prevent retrieval of unauthorized content

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Enforce access controls before evidence reaches the model.

</details>

### Q103. What is a context window?

- **A.** A browser viewport
- **B.** The number of GPUs
- **C.** The token capacity available for a model interaction
- **D.** The database connection count

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Relevant input and generated output must fit applicable model limits.

</details>

### Q104. What is a token?

- **A.** Always one complete English word
- **B.** A model-specific unit of text or other represented input
- **C.** Always one character
- **D.** Always one sentence

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Token boundaries depend on the tokenizer and language.

</details>

### Q105. What does temperature generally affect?

- **A.** Sampling variability
- **B.** Database consistency
- **C.** User authentication
- **D.** Embedding dimensionality

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Lower settings generally yield less variable sampling, not a correctness guarantee.

</details>

### Q106. What is a hallucination?

- **A.** Any short answer
- **B.** An authorized API call
- **C.** A low-latency response
- **D.** A plausible-sounding unsupported or incorrect generated claim

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Fluency does not establish factual grounding.

</details>

### Q107. Which statement about RAG is accurate?

- **A.** It eliminates all hallucinations
- **B.** It always changes model weights
- **C.** It can reduce unsupported answers but cannot guarantee correctness
- **D.** It removes the need for evaluation

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Retrieval quality and source reliability still matter.

</details>

### Q108. How does fine-tuning differ from ordinary RAG?

- **A.** Both always retrain all weights
- **B.** Fine-tuning changes model parameters; ordinary RAG supplies retrieved context
- **C.** RAG always changes model parameters
- **D.** Fine-tuning only performs SQL queries

<details>
<summary>Answer and explanation</summary>

**Answer: B.** They can be combined for behavior adaptation and external knowledge access.

</details>

### Q109. What does cosine similarity measure?

- **A.** Directional similarity between vectors
- **B.** Database storage size
- **C.** HTTP response speed
- **D.** Total token count

<details>
<summary>Answer and explanation</summary>

**Answer: A.** It is the normalized dot product; nonzero vectors are required.

</details>

### Q110. What is the cosine similarity of nonzero orthogonal vectors?

- **A.** 1
- **B.** -1
- **C.** Undefined for every case
- **D.** 0

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Their dot product is zero.

</details>

### Q111. What does top-k retrieval select?

- **A.** Only documents with k words
- **B.** k model training epochs
- **C.** A chosen number of highest-ranked candidates
- **D.** The newest document regardless of query

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Higher k can improve recall but also add irrelevant context.

</details>

### Q112. What is retrieval recall concerned with?

- **A.** Only answer grammar
- **B.** How much relevant material was retrieved
- **C.** Only network throughput
- **D.** Only tokenization speed

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Recall measures relevant items found relative to relevant items available.

</details>

### Q113. What is answer groundedness concerned with?

- **A.** Whether the answer is supported by provided evidence
- **B.** Whether every sentence is long
- **C.** Whether the answer uses Markdown
- **D.** Whether the model has many parameters

<details>
<summary>Answer and explanation</summary>

**Answer: A.** An answer can sound correct while lacking evidence support.

</details>

### Q114. Why use held-out evaluation examples?

- **A.** To increase prompt length arbitrarily
- **B.** To bypass validation
- **C.** To remove edge cases
- **D.** To assess performance beyond examples used for development or training

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Leakage creates overly optimistic evaluation results.

</details>

### Q115. What does structured output with a schema help achieve?

- **A.** Guaranteed semantic correctness
- **B.** Guaranteed safe authorization
- **C.** A predictable response shape
- **D.** Zero network failures

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Shape validation must be followed by semantic and business-rule validation.

</details>

### Q116. What is FAISS most precisely?

- **A.** A complete general-purpose SQL database
- **B.** A library for efficient vector similarity search
- **C.** An LLM provider
- **D.** An HTTP authentication standard

<details>
<summary>Answer and explanation</summary>

**Answer: B.** It can support a vector index without being a full managed database.

</details>

### Q117. Which metric exposes slow tail behavior?

- **A.** p95 or p99 latency
- **B.** Average prompt length alone
- **C.** Number of files alone
- **D.** Repository star count

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Percentiles reveal long waits hidden by average latency.

</details>

### Q118. What is a useful defense against injected instructions in retrieved text?

- **A.** Assume internal documents are always safe
- **B.** Give retrieved text system-level authority
- **C.** Disable logging permanently
- **D.** Treat evidence as data and enforce tool permissions outside the model

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Prompt separation helps, but enforcement must not depend solely on prompts.

</details>

### Q119. What is an LLM-as-judge evaluation limitation?

- **A.** It is always perfectly objective
- **B.** It never needs a rubric
- **C.** It can be biased and should be calibrated against human judgments
- **D.** It guarantees reproducibility

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Judge models have preferences and error modes.

</details>

### Q120. What is the purpose of a system instruction?

- **A.** To store database backups
- **B.** To define high-level behavior for the model interaction
- **C.** To train the tokenizer instantly
- **D.** To allocate GPU memory directly

<details>
<summary>Answer and explanation</summary>

**Answer: B.** It shapes behavior but does not substitute for external security controls.

</details>

## FastAPI, Pydantic, HTTP and API security

FastAPI uses type annotations and Pydantic for request/response modeling. Use async endpoints with awaitable libraries for asynchronous I/O. Synchronous endpoint functions are normally run in a thread pool; calling a blocking helper directly from an async endpoint still blocks its event-loop thread.

Validate data, authenticate identity and authorize actions separately. Browser CORS is not an authentication system. JWT claims are trustworthy only after appropriate signature, issuer, audience and expiry validation.

### Q121. What does `@app.get("/users")` declare?

- **A.** A GET route at /users
- **B.** A SQL table
- **C.** A Python class
- **D.** A database migration

<details>
<summary>Answer and explanation</summary>

**Answer: A.** The decorator registers an HTTP path operation.

</details>

### Q122. What is Pydantic mainly used for?

- **A.** Container scheduling
- **B.** Frontend reconciliation
- **C.** Vector indexing
- **D.** Data validation and serialization

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Models describe fields and validate supplied data.

</details>

### Q123. What does FastAPI's `Depends` support?

- **A.** Automatic CPU parallelism
- **B.** Database denormalization
- **C.** Dependency injection
- **D.** Training a neural network

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Reusable dependencies can provide authentication, sessions or configuration.

</details>

### Q124. What does a FastAPI response model help do?

- **A.** Guarantee a response is authorized
- **B.** Validate, document and filter returned data
- **C.** Retry failed requests indefinitely
- **D.** Encrypt all responses automatically

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Explicit output schemas help avoid exposing unintended fields.

</details>

### Q125. What is the common default status for FastAPI request validation errors?

- **A.** 422
- **B.** 201
- **C.** 301
- **D.** 503

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Applications can customize exception handling, but the default is 422.

</details>

### Q126. Which is appropriate for awaitable HTTP calls in an async endpoint?

- **A.** Use time.sleep while waiting
- **B.** Call a blocking client without considering offloading
- **C.** Add async to a variable name
- **D.** Await an asynchronous client call

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Nonblocking clients allow other tasks to progress during I/O waits.

</details>

### Q127. What does HTTP 201 indicate?

- **A.** Authentication failed
- **B.** A permanent redirect
- **C.** A resource was created
- **D.** A gateway timeout

<details>
<summary>Answer and explanation</summary>

**Answer: C.** It is commonly returned for successful resource creation.

</details>

### Q128. What does HTTP 401 indicate?

- **A.** The resource was created
- **B.** Missing or invalid authentication credentials
- **C.** The server is permanently offline
- **D.** The request succeeded with no body

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The response concerns authentication requirements.

</details>

### Q129. What does HTTP 403 indicate?

- **A.** The server refuses to fulfill the request
- **B.** The user is necessarily authenticated in every possible case
- **C.** The request always lacks valid JSON
- **D.** The resource was created

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Authorization failure is common; authentication is not guaranteed by the status itself.

</details>

### Q130. What does HTTP 429 indicate?

- **A.** A syntax error in Python
- **B.** A successful delete
- **C.** A permanent redirect
- **D.** Too many requests under a rate limit

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Respect server retry guidance when provided.

</details>

### Q131. Which method is defined as idempotent by HTTP semantics?

- **A.** POST
- **B.** CONNECT
- **C.** PUT
- **D.** All methods are idempotent by definition

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Repeating the same PUT has the same intended effect, though responses can differ.

</details>

### Q132. What distinguishes PATCH from PUT in typical resource APIs?

- **A.** PATCH is always read-only
- **B.** PATCH applies partial changes; PUT replaces a representation
- **C.** PUT always returns a JWT
- **D.** PATCH is always idempotent by definition

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A PATCH operation may or may not be idempotent depending on its design.

</details>

### Q133. What does CORS primarily regulate?

- **A.** Browser access to responses across origins
- **B.** Database user permissions
- **C.** JWT signature correctness
- **D.** Server-to-server authorization

<details>
<summary>Answer and explanation</summary>

**Answer: A.** CORS is a browser mechanism, not a backend security boundary.

</details>

### Q134. What is a key requirement when accepting a JWT?

- **A.** Decode its payload and trust it immediately
- **B.** Trust any token whose header says admin
- **C.** Store the signing secret in frontend code
- **D.** Verify its signature and relevant claims

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Validate algorithm policy, expiry, issuer and audience as applicable.

</details>

### Q135. What does parameterized SQL chiefly prevent?

- **A.** Every possible authorization bug
- **B.** All slow queries
- **C.** SQL injection through supplied values
- **D.** Network failure

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Parameters separate data from executable query structure.

</details>

### Q136. When should a long-running, durable agent job usually run?

- **A.** Only in the browser tab memory
- **B.** In a worker/job system with persistent status
- **C.** Only in an untracked local variable
- **D.** Always in one HTTP request without a timeout

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A job identifier supports progress checks, retries and recovery.

</details>

### Q137. What does OpenAPI provide for an API?

- **A.** A machine-readable description of its contract
- **B.** Encryption of stored passwords
- **C.** Automatic database backups
- **D.** GPU scheduling

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Documentation and client generation can use the schema.

</details>

### Q138. What should a secret API key be stored in?

- **A.** A public React bundle
- **B.** A public Git README
- **C.** An error response sent to users
- **D.** A protected secret store or appropriately controlled runtime configuration

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Limit access and avoid committing or exposing secrets.

</details>

## React, JavaScript, TypeScript and React Native

React state is a snapshot for each render. When an update depends on previous state, prefer a functional setter. Effects synchronize with external systems and require appropriate cleanup. In development Strict Mode, React can run an additional effect setup/cleanup cycle.

TypeScript types generally disappear at runtime; validate external input separately. React Native uses components such as View and Text backed by native platform primitives, rather than browser div and span elements.

### Q139. What does `useState` provide?

- **A.** An automatic database connection
- **B.** A CSS compiler
- **C.** Component state and a setter
- **D.** A global mutable variable shared by all components

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Updating state schedules a render.

</details>

### Q140. Which update is best when the new count depends on the previous count?

- **A.** `count++` without a setter
- **B.** `setCount(c => c + 1)`
- **C.** Assigning directly to props
- **D.** Changing a DOM attribute only

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A functional update uses the pending previous state.

</details>

### Q141. What is `useEffect` primarily for?

- **A.** Synchronizing with external systems
- **B.** Calculating every derived value unnecessarily
- **C.** Mutating props
- **D.** Defining TypeScript interfaces

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Subscriptions, timers and network synchronization often need effects.

</details>

### Q142. What should an effect cleanup typically do?

- **A.** Trigger an infinite render loop
- **B.** Mutate every prop
- **C.** Delete unrelated component state
- **D.** Remove subscriptions or cancel owned resources

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Cleanup runs before applicable reruns and at unmount.

</details>

### Q143. Why might an empty-dependency effect run an extra setup/cleanup cycle during development?

- **A.** Empty arrays mean run on every render in production
- **B.** The network always retries
- **C.** React Strict Mode checks effect cleanup behavior
- **D.** TypeScript forces duplicate execution

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Do not assume exactly-once side effects from the mount lifecycle.

</details>

### Q144. Why use stable keys in a rendered list?

- **A.** To encrypt props
- **B.** To identify elements consistently during reconciliation
- **C.** To sort items automatically
- **D.** To prevent every re-render

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Keys associate list items with their identity.

</details>

### Q145. Why can array-index keys be problematic in reorderable lists?

- **A.** State can become associated with the wrong item
- **B.** They are invalid JavaScript syntax
- **C.** They always cause an exception
- **D.** They prohibit CSS

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Indices change when items move or are inserted.

</details>

### Q146. What is the proper way to update an array in React state?

- **A.** Mutate the array and never call the setter
- **B.** Change the props array in place
- **C.** Modify an unrelated DOM element
- **D.** Create a new array and pass it to the setter

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Immutable updates preserve correct change detection and reasoning.

</details>

### Q147. What does `useRef` retain without its mutation automatically causing a render?

- **A.** A database transaction
- **B.** A CSS rule
- **C.** A mutable reference value
- **D.** A new React root

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Refs can store DOM references and non-rendering mutable information.

</details>

### Q148. What is a stale closure in a React callback?

- **A.** A closed browser tab
- **B.** A callback using values captured from an earlier render
- **C.** An expired database cursor only
- **D.** A malformed JSX tag

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Dependencies and functional updates help prevent related bugs.

</details>

### Q149. What does TypeScript `unknown` require before property use?

- **A.** Type narrowing or validation
- **B.** No checks at all
- **C.** Conversion to any in every case
- **D.** A runtime TypeScript server

<details>
<summary>Answer and explanation</summary>

**Answer: A.** unknown is safer than any for unchecked external values.

</details>

### Q150. What does a TypeScript interface commonly describe?

- **A.** A runtime encryption algorithm
- **B.** A network socket
- **C.** A database index
- **D.** The shape of an object

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Interfaces contribute compile-time checking.

</details>

### Q151. Does a TypeScript interface automatically validate JSON at runtime?

- **A.** Yes for every JSON response
- **B.** Only when React is used
- **C.** No
- **D.** Only on Azure

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Use a runtime validator or explicit checks for untrusted data.

</details>

### Q152. What is a discriminated union useful for?

- **A.** Increasing heap size
- **B.** Narrowing variants using a shared literal-valued field
- **C.** Disabling null checks
- **D.** Encrypting messages

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A kind or status field can identify a specific union member.

</details>

### Q153. What does JavaScript `===` avoid compared with `==`?

- **A.** Type coercion during equality comparison
- **B.** Every floating-point precision issue
- **C.** Object identity comparison
- **D.** All runtime errors

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Strict equality checks without loose-equality conversions.

</details>

### Q154. When do Promise callbacks run relative to synchronous code in the same turn?

- **A.** Before any synchronous code
- **B.** Only in a separate process
- **C.** Exactly one second later
- **D.** After the current synchronous call stack completes

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Promise reactions are scheduled as microtasks.

</details>

### Q155. What does `Promise.all` do if one input rejects?

- **A.** It cancels all other operations automatically
- **B.** It always waits and returns only successes
- **C.** The aggregate promise rejects
- **D.** It converts every error to null

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Other work can continue unless explicitly canceled.

</details>

### Q156. What does React Native `View` most closely represent?

- **A.** An HTML iframe
- **B.** A fundamental layout container
- **C.** A SQL view
- **D.** An LLM context window

<details>
<summary>Answer and explanation</summary>

**Answer: B.** It is a native UI building block.

</details>

### Q157. Which React Native component is intended for rendering text?

- **A.** Text
- **B.** div
- **C.** paragraph
- **D.** SQLText

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Browser HTML tags are not the standard native rendering primitives.

</details>

### Q158. Why prefer FlatList for a large React Native list?

- **A.** It renders every possible item immediately
- **B.** It guarantees zero memory usage
- **C.** It removes the need for item keys
- **D.** It supports virtualized rendering

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Virtualization limits the amount of UI mounted at once.

</details>

## SQL, NoSQL and data modeling

Know joins, NULL semantics, aggregation, indexes and transactions. WHERE filters rows; HAVING filters aggregated groups. SQL NULL is not ordinary equality: use IS NULL. Indexes can improve reads but cost storage and write maintenance.

Relational and NoSQL databases are design choices, not a universal performance ranking. Choose based on access patterns, consistency, relationships, transactions, scale and operational needs.

### Q159. What does an INNER JOIN return?

- **A.** Every left row regardless of match
- **B.** Every right row regardless of match
- **C.** Rows whose join condition matches on both sides
- **D.** Only unmatched rows

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Matching is determined by the ON condition.

</details>

### Q160. What does a LEFT JOIN preserve?

- **A.** Only all rows from the right table
- **B.** All rows from the left table
- **C.** Only unmatched right rows
- **D.** No rows with null values

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Missing right-side matches produce NULL right-side columns.

</details>

### Q161. What does WHERE filter in an aggregate query?

- **A.** Input rows before grouping
- **B.** Only completed groups
- **C.** Only column names
- **D.** Only indexes

<details>
<summary>Answer and explanation</summary>

**Answer: A.** HAVING filters group results.

</details>

### Q162. What does HAVING filter?

- **A.** Individual rows before grouping only
- **B.** Database users
- **C.** Join algorithms
- **D.** Groups after aggregation

<details>
<summary>Answer and explanation</summary>

**Answer: D.** It can test expressions such as COUNT(*) greater than a threshold.

</details>

### Q163. Which predicate tests for missing SQL values?

- **A.** `= NULL`
- **B.** `== NULL`
- **C.** `IS NULL`
- **D.** `LIKE NULL`

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Equality with NULL does not evaluate to true in ordinary SQL three-valued logic.

</details>

### Q164. What is the difference between COUNT(*) and COUNT(column)?

- **A.** COUNT(*) excludes every NULL-containing row
- **B.** COUNT(column) excludes NULL values; COUNT(*) counts rows
- **C.** Both always exclude every NULL-containing row
- **D.** COUNT(column) counts only distinct values

<details>
<summary>Answer and explanation</summary>

**Answer: B.** DISTINCT requires an explicit qualifier.

</details>

### Q165. What is a primary key's central purpose?

- **A.** Uniquely identify rows with non-null key values
- **B.** Store passwords
- **C.** Sort every query automatically
- **D.** Allow arbitrary duplicate row identity

<details>
<summary>Answer and explanation</summary>

**Answer: A.** It enforces entity identity.

</details>

### Q166. What does a foreign key enforce?

- **A.** Alphabetical sorting
- **B.** Encryption
- **C.** Automatic performance improvement for every query
- **D.** A referential relationship with allowed referenced keys

<details>
<summary>Answer and explanation</summary>

**Answer: D.** It protects referential integrity subject to defined database rules.

</details>

### Q167. What is an index tradeoff?

- **A.** Faster every operation without cost
- **B.** Guaranteed removal of all locks
- **C.** Faster suitable reads with storage and write overhead
- **D.** Automatic normalization

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Performance depends on query patterns and selectivity.

</details>

### Q168. Which ACID property means all-or-nothing transaction effects?

- **A.** Availability
- **B.** Atomicity
- **C.** Cardinality
- **D.** Durability

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A transaction's changes commit together or are rolled back.

</details>

### Q169. Which ACID property concerns committed changes surviving failures?

- **A.** Durability
- **B.** Atomicity
- **C.** Isolation
- **D.** Dependency

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Persistence mechanisms support durable commits.

</details>

### Q170. What is normalization primarily intended to reduce?

- **A.** All joins
- **B.** All indexes
- **C.** All constraints
- **D.** Redundancy and update anomalies

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Structured relationships avoid duplicating facts unnecessarily.

</details>

### Q171. Why might a document database fit an application?

- **A.** It never needs modeling
- **B.** It guarantees every query is faster than SQL
- **C.** It stores document-shaped data aligned with access patterns
- **D.** It cannot support indexes

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Model choices and consistency behavior remain important.

</details>

### Q172. How do ROW_NUMBER and RANK differ with tied ordering values?

- **A.** Both always assign the same value to ties
- **B.** ROW_NUMBER assigns distinct numbers; RANK gives ties the same rank and may leave gaps
- **C.** RANK never leaves gaps
- **D.** ROW_NUMBER is an aggregate sum

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Add a deterministic tie-breaker when stable row numbering matters.

</details>

### Q173. What causes an N+1 query problem?

- **A.** Fetching a collection then issuing a separate query per item
- **B.** One indexed query returning n rows
- **C.** A single JOIN alone
- **D.** One database connection

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Batch fetching or appropriate joins can reduce round trips.

</details>

## Docker, Kubernetes, cloud, CI/CD and professional judgment

A container packages an application process environment. Kubernetes orchestrates workloads; a Pod is its smallest deployable unit. Distinguish startup, readiness and liveness checks. A Secret's base64 representation is not encryption.

Review correctness, maintainability, security and tests. In client work, clarify measurable requirements and constraints before implementing assumptions. In delivery pipelines, use reproducible builds, protected credentials, appropriate checks and observable rollback strategies.

### Q174. What is a Docker image?

- **A.** Always a running process
- **B.** A Kubernetes node
- **C.** A cloud subscription
- **D.** A packaged template of filesystem layers and configuration

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Containers are created from images.

</details>

### Q175. What is a Docker container?

- **A.** A full physical server by definition
- **B.** A source-control branch
- **C.** An isolated process environment created from an image
- **D.** A vector index

<details>
<summary>Answer and explanation</summary>

**Answer: C.** A stopped container also exists; it need not currently be running.

</details>

### Q176. What is a multi-stage Docker build useful for?

- **A.** Eliminating every vulnerability
- **B.** Keeping build tools out of the final runtime image
- **C.** Replacing application tests
- **D.** Disabling caching

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Smaller runtime images can reduce size and attack surface.

</details>

### Q177. What is Kubernetes' smallest deployable workload unit?

- **A.** Pod
- **B.** Deployment
- **C.** Namespace
- **D.** Cluster

<details>
<summary>Answer and explanation</summary>

**Answer: A.** A Pod contains one or more closely associated containers.

</details>

### Q178. What does a Deployment commonly manage?

- **A.** External domain ownership
- **B.** Database schemas
- **C.** LLM tokenization
- **D.** Desired replicas and rolling updates

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Deployments manage ReplicaSets for suitable workloads.

</details>

### Q179. What does a Kubernetes Service provide?

- **A.** Permanent local file storage
- **B.** Model fine-tuning
- **C.** A stable networking abstraction for selected endpoints
- **D.** Secret encryption by itself

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Service types control how access is exposed.

</details>

### Q180. What does a readiness probe indicate?

- **A.** Whether credentials are encrypted
- **B.** Whether a container is ready to receive traffic
- **C.** Whether the node must be deleted
- **D.** Whether a database is normalized

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Failing readiness removes readiness for service routing; it is not itself a restart signal.

</details>

### Q181. What does a liveness probe help detect?

- **A.** A container requiring restart due to an unhealthy state
- **B.** A newly created cloud account
- **C.** A SQL join error only
- **D.** A missing README

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Misconfigured probes can cause unnecessary restarts.

</details>

### Q182. What does a startup probe help with?

- **A.** Encrypting startup arguments
- **B.** Ensuring all deployments use one replica
- **C.** Replacing a load balancer
- **D.** Allowing slow initialization before liveness/readiness checks take over

<details>
<summary>Answer and explanation</summary>

**Answer: D.** It protects slow-starting applications from premature probe action.

</details>

### Q183. Which statement about Kubernetes Secrets is accurate?

- **A.** Base64 prevents any administrator reading them
- **B.** They need no access controls
- **C.** Base64 encoding alone does not provide encryption
- **D.** They are always safe to commit publicly

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Use RBAC, encryption at rest as configured and sound secret management.

</details>

### Q184. What does continuous integration emphasize?

- **A.** Only manually copying production files
- **B.** Frequently integrating changes with automated checks
- **C.** Skipping tests for every merge
- **D.** Releasing without version control

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Builds and tests detect integration problems early.

</details>

### Q185. How does continuous delivery differ from continuous deployment?

- **A.** Delivery keeps releases deployable; deployment automatically releases passing changes to production
- **B.** Delivery never uses automation
- **C.** Deployment means only unit testing
- **D.** They always mean exactly the same thing

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Delivery can retain a production approval gate.

</details>

### Q186. What is infrastructure as code?

- **A.** Storing secrets in source by default
- **B.** Manually clicking every cloud change
- **C.** Embedding infrastructure only in CSS
- **D.** Managing infrastructure through versioned declarative or scripted definitions

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Reviewable definitions help repeatability and change tracking.

</details>

### Q187. Which cloud identity practice is strongest?

- **A.** Shared administrator passwords everywhere
- **B.** Publicly embedded access keys
- **C.** Least-privilege roles and managed identities where suitable
- **D.** No auditing

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Grant only needed permissions and rotate or avoid long-lived secrets.

</details>

### Q188. What should happen to credentials in a CI pipeline?

- **A.** Print them in every build log
- **B.** Retrieve them securely and limit exposure
- **C.** Commit them in a public repository
- **D.** Send them to the frontend

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Protect masking, access scope and lifecycle.

</details>

### Q189. What is blue-green deployment?

- **A.** Keeping two environments and switching traffic to the new version
- **B.** Updating database rows alphabetically
- **C.** Deploying only CSS colors
- **D.** Disabling health checks

<details>
<summary>Answer and explanation</summary>

**Answer: A.** It supports traffic switching and rollback when dependencies remain compatible.

</details>

### Q190. What is a canary release?

- **A.** Immediately deleting the old version
- **B.** Only running unit tests locally
- **C.** Changing all secrets at once
- **D.** Sending a limited portion of traffic to a new version first

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Observe errors and performance before broader rollout.

</details>

### Q191. What should a code review prioritize?

- **A.** Formatting alone
- **B.** Number of lines alone
- **C.** Correctness, security, maintainability and meaningful tests
- **D.** The author's seniority

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Review should assess behavior and risks as well as readability.

</details>

### Q192. A client requirement is ambiguous. What is the best first action?

- **A.** Implement whichever interpretation is fastest without discussion
- **B.** Clarify outcomes, constraints and acceptance criteria
- **C.** Ignore the request
- **D.** Promise every possible feature

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A shared contract prevents costly rework.

</details>

### Q193. An evaluation dataset contains sensitive client records. What should you do?

- **A.** Use approved access, minimization and anonymization where appropriate
- **B.** Upload it to any public tool
- **C.** Commit it into a public repository
- **D.** Email it broadly without checking permissions

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Protect data according to applicable organizational controls.

</details>

### Q194. A dashboard's average latency looks fine, but users report occasional long waits. What should you inspect?

- **A.** Only repository size
- **B.** Only CSS colors
- **C.** Only mean CPU temperature
- **D.** Tail latency and traces across dependencies

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Correlated traces help identify the slow request path.

</details>

### Q195. Which practice best supports safe rollback?

- **A.** Deleting the previous build immediately
- **B.** Untracked manual edits
- **C.** Versioned artifacts and tested compatibility of application and data changes
- **D.** Ignoring migrations

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Database changes can make a code-only rollback unsafe.

</details>


## Timed mock test

**30 questions / 30 minutes.** Close notes and do not read the key until you finish. One point per correct answer; this scoring is for practice only. These are additional original questions, not reused copies of the main bank.

### M01 / Q196. A nested list was shallow-copied. Mutating an inner list in the copy changes the original. Why?

- **A.** Shallow copy retrains the model
- **B.** Lists are immutable
- **C.** The inner list references are shared
- **D.** Python forbids nested lists

### M02 / Q197. A function uses `cache={}` as a default and results leak between calls. Which correction fits?

- **A.** Add more callers
- **B.** Use None as the default and create a dictionary inside the function
- **C.** Rename cache only
- **D.** Replace return with print

### M03 / Q198. What does `print(list(range(2, 7, 2)))` output?

- **A.** [2, 4, 6]
- **B.** [2, 4, 6, 7]
- **C.** [2, 3, 4, 5, 6]
- **D.** [0, 2, 4, 6]

### M04 / Q199. What does `print(len({1, 1, 2, 3}))` output?

- **A.** 4
- **B.** 2
- **C.** TypeError
- **D.** 3

### M05 / Q200. An ordinary function reaches its end without return. What does it return?

- **A.** 0
- **B.** False
- **C.** None
- **D.** An empty string

### M06 / Q201. You need to retain generator laziness while transforming values. Which expression fits?

- **A.** `[x*x for x in values]`
- **B.** `(x*x for x in values)`
- **C.** `list(values)`
- **D.** `sorted(values)`

### M07 / Q202. An async endpoint calls a synchronous blocking API directly. What can happen?

- **A.** Its event-loop thread is blocked during the call
- **B.** The call automatically becomes awaitable
- **C.** A separate process is always created
- **D.** The call is automatically canceled

### M08 / Q203. A coroutine object is created but never awaited or scheduled. What is true?

- **A.** It always runs immediately to completion
- **B.** It automatically becomes a thread
- **C.** It always returns a list
- **D.** Its body does not execute merely because the object was created

### M09 / Q204. An LLM proposes `delete_file(path)`. Where should authorization be enforced?

- **A.** Only in the model's natural-language reasoning
- **B.** In the tokenizer
- **C.** In the executing application/tool layer
- **D.** In the CSS

### M10 / Q205. An agent has already made 20 unsuccessful attempts. Which design helps control cost?

- **A.** Unlimited retries
- **B.** An explicit step/token/time budget with an exit path
- **C.** A larger prompt with no stopping rule
- **D.** More agents without monitoring

### M11 / Q206. A specialist produces a result for a coordinator to assess and route. Which architecture is this?

- **A.** Supervisor with specialist agents
- **B.** A database JOIN
- **C.** A browser reconciliation loop
- **D.** A container image build

### M12 / Q207. The tool says an operation timed out, but the remote service may have completed it. What should you do?

- **A.** Assume no side effect occurred
- **B.** Immediately repeat with a new identity
- **C.** Report certain failure without checking
- **D.** Query status using the same operation identity before retrying

### M13 / Q208. Two graph nodes append independent results to one list field in parallel. What is needed?

- **A.** A longer cloud region name
- **B.** An extra CSS class
- **C.** A compatible reducer and well-defined update semantics
- **D.** A lower token price

### M14 / Q209. You need conversation continuity within one graph thread. Which mechanism fits?

- **A.** A new random thread identifier for every message
- **B.** A checkpointer with the appropriate thread identifier
- **C.** A static HTML file only
- **D.** A model temperature increase

### M15 / Q210. You need preferences available in several conversation threads. Which mechanism fits?

- **A.** A cross-thread store
- **B.** Only an isolated thread checkpoint
- **C.** Only a React key
- **D.** Only a startup probe

### M16 / Q211. A node performs an external write before an interrupt. Why is that risky?

- **A.** Interrupts guarantee exactly-once external writes
- **B.** Interrupts remove all state
- **C.** Writes are forbidden in Python
- **D.** Node replay can repeat the write after resumption

### M17 / Q212. Your RAG system finds semantically related material but misses exact product codes. Which approach can help?

- **A.** Increasing temperature alone
- **B.** Deleting all metadata
- **C.** Hybrid lexical and vector retrieval
- **D.** Disabling retrieval

### M18 / Q213. Retrieved text tells the model to ignore policy and send secrets. What is this?

- **A.** Ordinary vector normalization
- **B.** Prompt injection in untrusted evidence
- **C.** A valid authorization grant
- **D.** Database atomicity

### M19 / Q214. A schema-valid response contains a wrong total. What does this show?

- **A.** Structural validation does not guarantee semantic correctness
- **B.** JSON schemas guarantee every fact
- **C.** Type hints automatically fix arithmetic
- **D.** Temperature zero guarantees correctness

### M20 / Q215. Why evaluate retrieval separately from generation?

- **A.** To eliminate all test data
- **B.** To bypass human review always
- **C.** To remove all cost measurements
- **D.** To identify whether failures came from missing evidence or answer construction

### M21 / Q216. A FastAPI response must omit internal password hashes. What helps?

- **A.** Returning every database field
- **B.** Adding the hash to the frontend
- **C.** A response model exposing only approved fields
- **D.** Disabling serialization

### M22 / Q217. An authenticated user lacks permission for an action. Which HTTP status commonly fits?

- **A.** 201
- **B.** 403
- **C.** 200
- **D.** 301

### M23 / Q218. You need to reuse authentication checks across endpoints. Which FastAPI mechanism fits?

- **A.** Depends
- **B.** useEffect
- **C.** ROW_NUMBER
- **D.** Docker COPY

### M24 / Q219. From initial count zero, two `setCount(c => c + 1)` calls are processed. What is the resulting count?

- **A.** 1
- **B.** 0
- **C.** Always undefined
- **D.** 2

### M25 / Q220. A component subscribes on mount and listeners accumulate on remount. What is missing?

- **A.** A database index
- **B.** A larger image
- **C.** Effect cleanup that unsubscribes
- **D.** A primary key

### M26 / Q221. External JSON is typed as a TypeScript interface but has invalid data. What is still needed?

- **A.** More interface names only
- **B.** Runtime validation
- **C.** A browser refresh only
- **D.** A Kubernetes Service

### M27 / Q222. After a LEFT JOIN, a WHERE clause requires `right.status = 'active'`. What happens to unmatched left rows?

- **A.** They are filtered out because the comparison with NULL is not true
- **B.** They always remain
- **C.** They become right-table rows
- **D.** They duplicate indefinitely

### M28 / Q223. A group must have at least five rows. Which clause fits?

- **A.** WHERE COUNT(*) >= 5
- **B.** ORDER BY COUNT(*) >= 5 alone
- **C.** LIMIT COUNT(*) >= 5
- **D.** HAVING COUNT(*) >= 5

### M29 / Q224. A pod should stop receiving traffic while temporarily unready but need not restart. Which probe fits?

- **A.** Liveness only
- **B.** Startup only
- **C.** Readiness
- **D.** No probe can express this

### M30 / Q225. A new version serves 5% of traffic while errors are monitored. What is this?

- **A.** Full cutover
- **B.** Canary release
- **C.** Unit testing only
- **D.** Database normalization

<details>
<summary>Mock answer key and explanations — open after completing all 30</summary>

| Question | Answer | Explanation |
|---|---|---|
| M01 | C | Only the outer container is independently copied. |
| M02 | B | Mutable defaults persist across calls unless you create fresh per-call state. |
| M03 | A | The stop value is excluded and the step is two. |
| M04 | D | Sets deduplicate equal hashable elements. |
| M05 | C | Python implicitly returns None. |
| M06 | B | A generator expression produces values on demand. |
| M07 | A | Use an async library or suitable offloading for blocking work. |
| M08 | D | Invocation creates a coroutine object; execution requires awaiting or scheduling. |
| M09 | C | Tool requests are not proof of permission. |
| M10 | B | Bounded execution limits runaway loops. |
| M11 | A | The coordinator delegates work and controls subsequent routing. |
| M12 | D | Ambiguous outcomes require reconciliation and deduplication. |
| M13 | C | The reducer defines how concurrent updates combine. |
| M14 | B | Consistent thread identity links requests to saved state. |
| M15 | A | Long-term application memory is distinct from thread state. |
| M16 | D | Isolate side effects and enforce idempotency. |
| M17 | C | Exact lexical matches complement semantic search. |
| M18 | B | Treat embedded instructions as untrusted content. |
| M19 | A | Business-rule checks and calculation tools are separate controls. |
| M20 | D | Component-specific metrics make diagnosis possible. |
| M21 | C | Output filtering reduces accidental exposure; authorization is still required. |
| M22 | B | Forbidden is suitable for a refused operation due to access policy. |
| M23 | A | Dependencies provide reusable request-time behavior. |
| M24 | D | Functional updates are applied in sequence using pending state. |
| M25 | C | Cleanup releases the subscription owned by that effect. |
| M26 | B | Compile-time declarations do not validate network payloads. |
| M27 | A | Put the condition in ON when the intention is to preserve unmatched left rows while restricting matches. |
| M28 | D | Aggregate group filtering uses HAVING. |
| M29 | C | Readiness controls whether it is suitable for traffic. |
| M30 | B | A limited rollout reduces exposure while observing behavior. |

Practice interpretation, not a PwC pass threshold:

- **26–30:** Review low-confidence answers and code-output traps.
- **21–25:** Revisit your weakest two topic groups.
- **16–20:** Repeat Python and agent workflow fundamentals before more mocks.
- **0–15:** Work through the primers slowly and explain each missed concept aloud.

</details>

## Coding drills

These are supplementary exercises because some candidate reports include coding. They are original practice problems, not verified PwC questions. Spend 5–10 minutes on one after the mock; use the others for later preparation.

### Drill 1 — character frequencies

Write `frequencies(text)` returning a character-to-count dictionary. Preserve case and count spaces. `frequencies("aba")` must return `{"a": 2, "b": 1}`. Empty input returns `{}`.

<details><summary>Reference solution</summary>

```python
from collections import Counter

def frequencies(text):
    return dict(Counter(text))
```

Time O(n); extra space O(k), where k is the number of distinct characters.

</details>

### Drill 2 — deduplicate without losing order

Given a list of hashable values, return the first occurrence of each. `[3, 1, 3, 2, 1]` becomes `[3, 1, 2]`.

<details><summary>Reference solution</summary>

```python
def unique_in_order(values):
    return list(dict.fromkeys(values))
```

Average time O(n), space O(k). Requires hashable elements; it does not handle arbitrary nested lists as keys.

</details>

### Drill 3 — two sum

Return two distinct indices whose values sum to the target; return `None` if there is no match. `[2, 7, 11, 15]`, target `9`, returns `(0, 1)`. Include duplicate-value cases such as `[3, 3]`, target `6`.

<details><summary>Reference solution</summary>

```python
def two_sum(values, target):
    seen = {}
    for i, value in enumerate(values):
        complement = target - value
        if complement in seen:
            return seen[complement], i
        seen[value] = i
    return None
```

Average time O(n), space O(n). Checking before inserting prevents using the same index twice.

</details>

### Drill 4 — group records

Given dictionaries with a `department` field, return a dictionary from department to matching records. Explain what your function should do if the field is missing.

<details><summary>Reference solution with explicit missing-field policy</summary>

```python
from collections import defaultdict

def group_by_department(records):
    groups = defaultdict(list)
    for record in records:
        department = record["department"]  # missing field raises KeyError
        groups[department].append(record)
    return dict(groups)
```

Time O(n), space O(n) for output references. A missing-field policy should be explicit rather than silently invented.

</details>

### Drill 5 — bounded asynchronous calls

Implement an async mapper that limits simultaneous calls to five. Results should retain input order. Assume `fetch(item)` is an async callable. This bounds active calls, not the total number of created tasks; very large inputs need a bounded queue/worker approach.

<details><summary>Reference solution</summary>

```python
import asyncio

async def bounded_map(items, fetch, limit=5):
    if limit < 1:
        raise ValueError("limit must be positive")
    semaphore = asyncio.Semaphore(limit)

    async def one(item):
        async with semaphore:
            return await fetch(item)

    return await asyncio.gather(*(one(item) for item in items))
```

`gather` preserves input-result order. Its default exception propagation does not by itself provide transactional cancellation of every other operation. Define timeout, cancellation and partial-result policy for production use.

</details>

### Drill 6 — aggregate SQL

Table: `tickets(id, team, status)`. Return teams with more than three open tickets, along with their open-ticket count.

<details><summary>Reference solution</summary>

```sql
SELECT team, COUNT(*) AS open_count
FROM tickets
WHERE status = 'open'
GROUP BY team
HAVING COUNT(*) > 3;
```

WHERE selects open rows before grouping; HAVING tests each team's resulting count.

</details>

### Drill 7 — validated FastAPI request

Create a POST endpoint `/tasks` accepting a nonempty title and integer priority between 1 and 5. Return a validated response with `id`, `title` and `priority`. Assume current Pydantic v2-compatible FastAPI. Storage below is illustrative only.

<details><summary>Reference solution</summary>

```python
from uuid import uuid4
from fastapi import FastAPI
from pydantic import BaseModel, Field

app = FastAPI()

class TaskCreate(BaseModel):
    title: str = Field(min_length=1)
    priority: int = Field(ge=1, le=5)

class TaskOut(TaskCreate):
    id: str

@app.post("/tasks", response_model=TaskOut, status_code=201)
def create_task(task: TaskCreate):
    return TaskOut(id=str(uuid4()), **task.model_dump())
```

This enforces string length, not a requirement that the title contain non-whitespace text. Pydantic may coerce compatible input types unless strict validation is configured. Persist data and add authentication/authorization in a real application.

</details>

### Drill 8 — graph routing pseudocode

Design a graph that reads a question, chooses a tool if needed, incorporates its result, and ends with an answer. Add a maximum of five tool attempts and a human-review branch for sensitive actions. Explain which fields must be persisted.

<details><summary>Expected reasoning</summary>

- State: messages, proposed tool call, tool result, attempt count, approval status and final answer.
- Start at the agent node. Route to END if it produces a final answer.
- Route to approval when a proposed action needs human review.
- Route to a validated tool node only when authorized and within the attempt budget.
- After the tool result, return to the agent; increment the attempt counter consistently.
- On denied approval, exhausted budget or unrecoverable failure, return a clear outcome without executing the action.
- Use a thread checkpointer for resumption and durable storage where restarts matter.
- Make externally visible side effects idempotent; checkpointing alone does not guarantee exactly-once execution.

</details>

## Final revision sheet

| Topic | Remember | Common trap |
|---|---|---|
| Python assignment | Names bind to objects | Assignment is not copying |
| Tuple | Container is immutable | Contained lists may still mutate |
| Default arguments | Evaluated at definition time | Mutable defaults leak state |
| Copy | Shallow shares nested references | Outer copies do not isolate inner objects |
| List methods | sort/append mutate and return None | sorted creates a new list |
| Closures | Capture variables | Loop lambdas can share the final value |
| Generator | Lazy, single-pass iterator | Consumed generators do not restart |
| Async | Overlap nonblocking I/O waits | async alone does not accelerate CPU work |
| Agent | Select action, execute, observe, repeat | Agent is not synonymous with multi-agent |
| Tool calling | Model proposes; runtime executes | Tool schemas do not grant permission |
| LangGraph state | Carry information between nodes | Returning updates is not necessarily appending |
| Reducer | Specify how a key's updates merge | Concurrent writes need a defined strategy |
| Persistence | Checkpointer for threads; store across threads | In-memory persistence is not restart durability |
| Interrupt | Pause and resume with input | A resumed node may replay preceding code |
| RAG | Retrieve evidence before generation | Retrieved evidence can be wrong or malicious |
| Temperature | Influences sampling variability | Zero does not prove truth or reproducibility |
| Embeddings | Vector representations | Similarity is not factual verification |
| Response schema | Validate shape | Semantic correctness needs separate checks |
| FastAPI | Type-driven models and dependencies | A blocking helper inside async still blocks |
| HTTP | 401 authentication; 403 refusal; 429 rate limit | 403 does not universally prove authentication |
| React state | Snapshot plus scheduled updates | Use functional updates for dependent changes |
| Effect | Setup and cleanup external synchronization | Development Strict Mode can run an extra cycle |
| TypeScript | Compile-time checking | Interfaces do not validate incoming JSON |
| SQL | WHERE rows; HAVING groups | NULL is tested with IS NULL |
| LEFT JOIN | Preserves left rows before later filtering | WHERE on right fields can remove unmatched rows |
| Container | Can be running or stopped | A container is not always a currently running instance |
| Kubernetes | Pod, Deployment, Service | Readiness and liveness serve different purposes |
| Secrets | Need access control and appropriate encryption | Base64 is not encryption |
| CI/CD | Integration checks; delivery vs deployment | Production rollback can depend on data compatibility |
| Reliability | Timeout does not establish remote failure | Blind retry can duplicate effects |

### Ten questions to answer aloud before the assessment

1. Explain mutable default arguments with a two-call example.
2. Explain shallow copy using an outer list and shared inner list.
3. Explain who executes a model-requested tool and who authorizes it.
4. Explain graph state, node, edge, conditional edge and reducer.
5. Explain checkpointer vs store and in-memory vs durable persistence.
6. Explain how an interrupted workflow resumes without duplicating a sensitive action.
7. Explain indexing vs query-time RAG and when hybrid search helps.
8. Explain why schemas, RAG and low temperature do not guarantee correctness.
9. Explain blocking I/O inside an async endpoint and React effect cleanup.
10. Explain WHERE vs HAVING, readiness vs liveness and delivery vs deployment.

## Sources and further reading

Public assessment information is limited to candidate reports. Technical reference links below are primary documentation; they support concepts, not predictions about what PwC will ask. Links checked on 1 October 2026. Some examples here deliberately use pseudocode or stable concepts rather than prescribing version-specific package APIs.

| Area | Official reference |
|---|---|
| Python control flow, defaults and function arguments | [Python tutorial](https://docs.python.org/3/tutorial/controlflow.html) |
| Python data structures | [Python data structures](https://docs.python.org/3/tutorial/datastructures.html) |
| Python asyncio | [asyncio documentation](https://docs.python.org/3/library/asyncio.html) |
| LangGraph state, nodes, edges and reducers | [Graph API overview](https://docs.langchain.com/oss/python/langgraph/graph-api) |
| LangGraph persistence | [Persistence](https://docs.langchain.com/oss/python/langgraph/persistence) |
| Human approval and resumption | [LangGraph interrupts](https://docs.langchain.com/oss/python/langgraph/interrupts) |
| LangChain retrieval | [Retrieval documentation](https://docs.langchain.com/oss/python/langchain/retrieval) |
| LangChain tools | [Tools documentation](https://docs.langchain.com/oss/python/langchain/tools) |
| CrewAI teams and processes | [Crews documentation](https://docs.crewai.com/en/concepts/crews) |
| FastAPI asynchronous behavior | [Concurrency and async/await](https://fastapi.tiangolo.com/async/) |
| FastAPI response filtering | [Response models](https://fastapi.tiangolo.com/tutorial/response-model/) |
| FastAPI dependency injection | [Dependencies](https://fastapi.tiangolo.com/tutorial/dependencies/) |
| React effects and cleanup | [useEffect](https://react.dev/reference/react/useEffect) |
| TypeScript narrowing | [Narrowing](https://www.typescriptlang.org/docs/handbook/2/narrowing.html) |
| React Native UI primitives | [Core and native components](https://reactnative.dev/docs/intro-react-native-components) |
| SQL aggregation | [PostgreSQL aggregate functions tutorial](https://www.postgresql.org/docs/current/tutorial-agg.html) |
| Container fundamentals | [Docker containers](https://docs.docker.com/get-started/docker-concepts/the-basics/what-is-a-container/) |
| Kubernetes workload fundamentals | [Pods](https://kubernetes.io/docs/concepts/workloads/pods/) |
| Cloud security principles | [Azure Well-Architected security principles](https://learn.microsoft.com/en-us/azure/well-architected/security/principles) |
| LLM application security | [OWASP GenAI security project](https://owasp.org/www-project-top-10-for-large-language-model-applications/) |
| HTTP status reference | [MDN HTTP response status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status) |

## Coverage and limitations

This README contains **225 original MCQs**: **195 topic questions including 25 executable Python output questions**, plus **30 additional mixed mock questions**, and **8 coding/design drills**. Every MCQ has four options and one intended correct answer with an explanation. It covers the supplied JD, but is not an exhaustive catalogue of computer science, AI or all PwC hiring assessments. Cloud questions focus on architecture and security rather than vendor certification trivia. Broader operating-system, network, aptitude or specialist ML questions may still appear if your invitation names those areas.
