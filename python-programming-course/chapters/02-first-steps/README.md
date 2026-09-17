# Chapter 2 — First Steps in Python

**Weeks 3–5 | 9 contact hours**

---

## Overview

This is the core language chapter. By the end of Week 5, students can write real Python programs performing calculations, formatted output, string manipulation, decision-making, and iteration. The engineering examples throughout this chapter are drawn from structural mechanics, fluid dynamics, and sensor data processing.

---

## Learning Objectives

By the end of this chapter you will be able to:

1. Use all seven Python arithmetic operators and understand operator precedence.
2. Format output using `print()` with f-strings and format specifiers (alignment, decimal places, scientific notation).
3. Assign and use variables with appropriate types (`int`, `float`, `str`, `bool`).
4. Convert between types using `int()`, `float()`, `str()`, `bool()`.
5. Index, slice, and process strings using built-in methods.
6. Write `if`/`elif`/`else` blocks for multi-way decision logic.
7. Write `for` loops over `range()` and sequences; use `while` loops with convergence criteria.
8. Use `break` and `continue` to control loop flow.
9. Use `input()` to read keyboard input and convert it appropriately.

---

## Files in This Chapter

| File | Purpose |
|---|---|
| `prep/session-prep.md` | Pre-reading: objectives, pitfalls, prerequisites |
| `lecture/02-lecture.ipynb` | Full lecture notebook — 3 weeks of content |
| `lab/02-tp-first-steps.ipynb` | Student lab workbook |
| `lab/02-tp-solutions.ipynb` | Worked solutions with explanations |

---

## Topics Covered

1. Arithmetic operators: `+`, `-`, `*`, `/`, `//`, `%`, `**`; the `math` module
2. `print()` with `sep`, `end`; f-string formatting specifiers
3. Variable assignment; `int`, `float`, `str`, `bool`, `None`; `type()`; type conversion
4. String literals, indexing, slicing; methods: `.strip()`, `.split()`, `.upper()`, `.lower()`, `.find()`, `.replace()`
5. `if`/`elif`/`else`; comparison operators; `and`, `or`, `not`; chained comparisons
6. `for` over `range()` and lists; `while`; `break`; `continue`; `enumerate()`; `zip()`
7. `input()` and required type conversion

---

## Key Pitfalls to Watch

- `input()` always returns a string — always convert before arithmetic.
- `7 / 2 = 3.5` (not 3) in Python 3. Use `//` for integer division.
- Strings are immutable — you cannot assign to `s[0]`.
- `=` is assignment; `==` is comparison.
- Indentation is syntax — 4 spaces, no mixing tabs and spaces.
