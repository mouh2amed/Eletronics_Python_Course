# Chapter 2 — Session Preparation: First Steps in Python

**Weeks 3–5 | 9 contact hours**

---

## Learning Objectives

By the end of this chapter you will be able to:

1. Use Python as a calculator with all arithmetic operators: `+`, `-`, `*`, `/`, `//`, `%`, `**`.
2. Distinguish between integer division (`//`) and float division (`/`).
3. Use `print()` to display values, formatted strings, and multiple items.
4. Assign values to variables with appropriate, descriptive names following PEP 8 naming conventions.
5. Identify and use the fundamental Python data types: `int`, `float`, `str`, `bool`.
6. Perform type conversion using `int()`, `float()`, `str()`, and `bool()`.
7. Construct, index, slice, and manipulate strings.
8. Write `for` and `while` loops to repeat blocks of code.
9. Write `if`, `elif`, and `else` conditional statements.
10. Use `input()` to read text entered from the keyboard and convert it to the appropriate type.

---

## Why This Matters for Engineers

The topics in this chapter are the building blocks of every engineering calculation you will ever automate with Python:

- **Arithmetic** is how you implement formulas — Newton's second law, Ohm's law, beam bending equations.
- **Variables** are how you name physical quantities and make code readable.
- **Loops** are how you process repeated data — iterate over sensor readings, time steps, or design parameters.
- **Conditionals** are how you implement design checks — "is the stress below the allowable limit?"
- **Input** is how you build interactive calculation tools that other engineers can use without reading your code.

A student who masters these five topics can already automate a significant fraction of routine engineering calculations.

---

## Subtopics (in order)

1. **Arithmetic in Python** — operators `+`, `-`, `*`, `/`, `//`, `%`, `**`; operator precedence; `math` module functions.
2. **Output / printing** — `print()` with single and multiple arguments; separator and end parameters; formatted output with f-strings; number formatting specifiers.
3. **Variables and types** — assignment syntax; naming rules; `int`, `float`, `str`, `bool`; `type()` function; type conversion; `None`.
4. **Strings** — string literals (single, double, triple quotes); escape sequences; string operators (`+`, `*`); indexing and slicing; string methods (`.upper()`, `.lower()`, `.strip()`, `.split()`, `.replace()`, `.find()`).
5. **Loops and conditionals** — `if`/`elif`/`else` blocks; comparison operators; boolean operators (`and`, `or`, `not`); `for` loops over ranges and sequences; `while` loops; `break` and `continue`.
6. **Reading keyboard input** — `input()` function; prompts; converting `input()` return value to `int` or `float`.

---

## Prerequisite Check

Before attending Week 3, confirm:

- [ ] Chapter 1 complete: Python installed, IDLE working, Jupyter running.
- [ ] You can open a Jupyter notebook and run a code cell.
- [ ] You understand the difference between the REPL and a saved script.

---

## Time Budget

| Activity | Duration |
|---|---|
| Week 3 lecture: arithmetic, print, variables, types | 3 h |
| Week 4 lecture: strings, string methods | 3 h |
| Week 5 lecture: loops, conditionals, input() | 3 h |
| Self-study and lab practice | ~3 h recommended |

---

## Common Misconceptions and Pitfalls

**Integer division surprises**
`7 / 2` gives `3.5` in Python 3 (true division). `7 // 2` gives `3` (floor division). Students from C/Java backgrounds may expect `7 / 2 = 3`; this is not the case in Python 3.

**`input()` always returns a string**
`age = input("Enter your age: ")` gives `age = '25'` as a string, not the integer `25`. Forgetting to convert with `int(age)` is one of the most common beginner errors and will cause confusing bugs in arithmetic.

**String indexing is zero-based**
`"Python"[0]` is `'P'`, not `'y'`. Negative indices count from the end: `"Python"[-1]` is `'n'`.

**Mutable default in loops**
Students sometimes try to modify a string in-place: `s[0] = 'A'` raises a `TypeError` because strings are **immutable**. You must create a new string.

**`=` vs `==`**
`x = 5` is assignment. `x == 5` is a comparison that returns `True` or `False`. Confusing them inside an `if` statement is a classic error.

**`while True` without a `break`**
An infinite loop will hang the kernel. Always have a clear termination condition for `while` loops. If you accidentally create one, use Kernel → Interrupt.

**Indentation errors**
Python uses indentation to define code blocks. A body inside `if`, `for`, or `while` must be consistently indented (4 spaces). Mixing tabs and spaces causes `TabError`.

---

## What to Have Ready for Class

- Chapter 1 environment working (Python 3.12, Jupyter).
- This notebook open and kernel connected.
- `docs/style-guide.md` read — especially sections on naming conventions and f-strings.
