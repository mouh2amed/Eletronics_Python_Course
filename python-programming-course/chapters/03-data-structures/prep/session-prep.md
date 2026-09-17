# Chapter 3 — Session Preparation: Data Structures

**Weeks 6–7 | 6 contact hours**

---

## Learning Objectives

By the end of this chapter you will be able to:

1. Create, index, and slice Python lists.
2. Modify lists using `.append()`, `.insert()`, `.remove()`, `.pop()`, `.sort()`, and `.reverse()`.
3. Iterate over a list using `for` loops and use `len()`, `min()`, `max()`, `sum()`.
4. Use list comprehensions to build filtered or transformed lists concisely.
5. Create Python dictionaries with literal syntax and the `dict()` constructor.
6. Access, add, update, and delete dictionary entries.
7. Iterate over dictionary keys, values, and key-value pairs.
8. Use `.get()` for safe access with a default value.
9. Explain when to use a list versus a dictionary.
10. Build lists of dictionaries to represent tabular data (e.g., rows of sensor readings).

---

## Why This Matters for Engineers

Individual variables are not enough once you have multiple data points. In real engineering:

- A sensor network produces a **list** of readings — one number per timestamp.
- A configuration file maps parameter names to values — a **dictionary** is a natural fit.
- A data table (like `sensor_data.csv`) is best represented as a **list of dictionaries**, one dictionary per row.
- Filtering, averaging, and summarising data all require iterating over collections.

Mastering lists and dictionaries is the step from "writing one-off calculations" to "processing data sets." Everything built in Chapters 4 and 5 will use these structures.

---

## Subtopics (in order)

1. **Lists** — creation; indexing and slicing; mutability; `len()`; `in` operator; common methods; `sorted()` vs `.sort()`; list comprehensions.
2. **Dictionaries** — creation; key-value pairs; accessing with `[]` and `.get()`; `.keys()`, `.values()`, `.items()`; adding, updating, deleting entries; iterating; nested dictionaries; list of dicts.

---

## Prerequisite Check

Before Week 6, confirm:

- [ ] You can write `for` loops over a list (Chapter 2).
- [ ] You understand variable assignment and type conversion.
- [ ] You can use f-strings for formatted output.
- [ ] You have the `sensor_data.csv` asset file available in the course `assets/` folder.

---

## Time Budget

| Activity | Duration |
|---|---|
| Week 6 lecture: Lists — creation, indexing, methods, comprehensions | 3 h |
| Week 7 lecture: Dictionaries — creation, access, iteration, nested | 3 h |
| Self-study and lab practice | ~2 h recommended |

---

## Common Misconceptions and Pitfalls

**Lists are mutable; strings are not**
`my_list[0] = 42` is valid. `my_string[0] = 'X'` raises `TypeError`. Students coming from string operations sometimes try to reassign list elements using string-style operations.

**Slicing does not modify the original list**
`my_list[1:3]` returns a *new* list. `my_list` is unchanged. To delete elements, use `del my_list[1:3]` or `.pop()`.

**`.sort()` modifies in place; `sorted()` returns a new list**
`a = my_list.sort()` assigns `None` to `a` because `.sort()` returns `None`. Use `sorted(my_list)` when you need a sorted copy.

**Dictionary keys must be immutable**
Lists cannot be keys. Strings, numbers, and tuples can. A common error: using a list as a key `{[1,2]: 'value'}` raises `TypeError`.

**KeyError vs `.get()`**
`d['nonexistent_key']` raises `KeyError`. `d.get('nonexistent_key', default)` returns `default` (or `None`) instead. Always prefer `.get()` when the key's existence is not guaranteed.

**Dictionary ordering**
Since Python 3.7, dictionaries maintain insertion order. Students should know this, but should not rely on a specific order when the order is semantically irrelevant — use `.sorted()` explicitly if alphabetical order is needed.

---

## What to Have Ready for Class

- `assets/sensor_data.csv` — this file will be read manually (as a string) in exercises before Chapter 5 introduces file I/O properly.
- A clear mental model of the difference between a list (ordered sequence) and a dictionary (key → value mapping).
