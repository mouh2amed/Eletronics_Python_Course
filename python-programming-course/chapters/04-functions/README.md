# Chapter 4 — Functions

**Weeks 8–10 | 9 contact hours**

---

## Overview

This chapter transforms your approach from writing sequential scripts to building reusable, composable tools. All nine syllabus objectives are covered across three weeks, culminating in a complete engineering function library in the lab.

---

## Learning Objectives

By the end of this chapter you will be able to:

1. Use Python's built-in functions fluently.
2. Define parameterless, single-parameter, and multi-parameter functions.
3. Use default parameter values to make functions flexible.
4. Assign function objects to variables and pass them as arguments.
5. Write variadic functions using `*args` and `**kwargs`.
6. Predict the behaviour of mutable vs immutable argument passing.
7. Reason about variable scope using the LEGB rule.
8. Write anonymous lambda functions for use as key/sort expressions.

---

## Files in This Chapter

| File | Purpose |
|---|---|
| `prep/session-prep.md` | Pre-reading: objectives, pitfalls, prerequisites |
| `lecture/04-lecture.ipynb` | Full lecture notebook — 3 weeks of content |
| `lab/04-tp-functions.ipynb` | Student lab workbook |
| `lab/04-tp-solutions.ipynb` | Worked solutions with explanations |

---

## Key Pitfalls

- Never use a mutable default argument (e.g., `def f(data=[]):`). Use `None` instead.
- `.sort()` returns `None`; store the result of `sorted()`, not `.sort()`.
- A function that only prints (no `return`) returns `None`. Storing the result gives `None`.
- Assigning a new value to a function parameter (for an immutable type) does not modify the caller's variable.
- Modifying a list in-place inside a function DOES modify the caller's list.
- Lambda functions are limited to a single expression — no `if` blocks or loops.
