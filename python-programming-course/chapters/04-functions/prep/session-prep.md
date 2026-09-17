# Chapter 4 — Session Preparation: Functions

**Weeks 8–10 | 9 contact hours**

---

## Learning Objectives

By the end of this chapter you will be able to:

1. Call and explain the behaviour of common Python built-in functions: `print()`, `len()`, `range()`, `type()`, `int()`, `float()`, `str()`, `abs()`, `round()`, `min()`, `max()`, `sum()`, `sorted()`, `enumerate()`, `zip()`.
2. Define a simple function with no parameters using `def`.
3. Define functions with one or more positional parameters and a `return` statement.
4. Define functions with default parameter values.
5. Assign a function object to a variable and call it through that variable.
6. Define variadic functions accepting any number of positional arguments with `*args`.
7. Define variadic functions accepting any number of keyword arguments with `**kwargs`.
8. Explain the difference between mutable and immutable argument passing and predict behaviour.
9. Distinguish between local and global variable scope; use the `global` keyword when necessary (sparingly).
10. Define and use anonymous (lambda) functions for short, one-expression operations.

---

## Why This Matters for Engineers

Functions are the primary tool for code reuse. Without functions, every time you need to compute, say, the second moment of area, you copy-paste the formula. With a function `moment_of_area(b, h)`, you write it once, test it once, and call it everywhere.

In engineering practice:
- A **library of unit-conversion functions** saves hours of copy-paste errors.
- A **variadic function** can process any number of measurement channels without rewriting.
- **Lambda functions** allow inline sorting and filtering of data tables.
- Understanding **scope** prevents subtle bugs where a function silently modifies data it should not touch.

This chapter transforms code from "a sequence of instructions" into "a library of reusable tools."

---

## Subtopics (in order)

1. **Built-in functions** — reviewing the most important ones; reading the `help()` documentation.
2. **Simple parameterless functions** — `def` syntax; `return`; functions that print vs functions that return.
3. **Functions with parameters** — positional arguments; type hints (optional); docstrings.
4. **Default parameter values** — syntax; why the argument is optional; mutable default anti-pattern.
5. **Assigning a function to a variable** — first-class functions; passing functions as arguments.
6. **Variadic functions** — `*args` (any number of positional args); `**kwargs` (any number of keyword args); combining fixed and variadic parameters.
7. **Mutable vs immutable argument passing** — integers/strings are passed by value (effectively); lists/dicts are passed by reference (modifying in-place affects the caller).
8. **Local vs global scope** — LEGB rule (Local, Enclosing, Global, Built-in); the `global` keyword; why globals are generally avoided.
9. **Lambda functions** — `lambda` keyword; single expression; used with `sorted()`, `map()`, `filter()`.

---

## Prerequisite Check

Before Week 8, confirm:

- [ ] You are comfortable writing `for` loops and `if/elif/else` blocks (Chapter 2).
- [ ] You can create and access lists and dictionaries (Chapter 3).
- [ ] You have read the docstring section in `docs/style-guide.md`.

---

## Time Budget

| Activity | Duration |
|---|---|
| Week 8 lecture: built-ins, parameterless, parameters, defaults | 3 h |
| Week 9 lecture: function variables, *args/**kwargs, mutability | 3 h |
| Week 10 lecture: scope, lambda | 3 h |
| Self-study and lab practice | ~3 h recommended |

---

## Common Misconceptions and Pitfalls

**Return vs print**
A function that `print()`s a value and a function that `return`s a value are very different. `print()` produces output to the screen; `return` makes the value available to the calling code. `result = my_function()` only stores something useful if the function `return`s something.

**`None` return**
A function without an explicit `return` statement (or with a bare `return`) implicitly returns `None`. Storing the result of such a function and then trying to use it numerically causes `TypeError`.

**Mutable default argument anti-pattern**
`def f(data=[]):` is a classic Python bug. The default list is created ONCE when the function is defined, and shared across all calls that use the default. Use `def f(data=None): if data is None: data = []` instead.

**List modification in function**
Passing a list to a function and modifying it inside the function changes the original list. This surprises students who expect function arguments to be copied. For immutable types (int, str, float, tuple), there is no such surprise.

**Global scope overuse**
Students sometimes solve "my variable isn't accessible" problems by making everything global. This creates fragile, hard-to-test code. Prefer passing values as arguments and receiving results via `return`.

**Lambda limitations**
A `lambda` can contain only a single expression — no `if`/`else` blocks, no loops, no assignments. It is appropriate for simple key functions. For anything more complex, use a named function.

---

## What to Have Ready for Class

- Chapters 1–3 material reviewed.
- `docs/style-guide.md` section on docstrings re-read.
- Be ready to discuss: "what is the difference between passing an `int` and passing a `list` to a function?"
