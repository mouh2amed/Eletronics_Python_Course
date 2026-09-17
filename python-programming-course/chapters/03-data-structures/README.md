# Chapter 3 — Data Structures: Lists and Dictionaries

**Weeks 6–7 | 6 contact hours**

---

## Overview

This chapter introduces Python's two most important built-in collection types. Lists provide ordered, indexed storage for sequences of values. Dictionaries provide fast, named access to structured records. Together they cover the vast majority of data-handling needs in engineering scripts.

---

## Learning Objectives

By the end of this chapter you will be able to:

1. Create, index, slice, and modify Python lists.
2. Use key list methods: `.append()`, `.insert()`, `.remove()`, `.pop()`, `.sort()`, `.reverse()`.
3. Use `len()`, `min()`, `max()`, `sum()`, and `sorted()` on lists.
4. Write list comprehensions with filtering and transformation.
5. Create dictionaries and access values by key.
6. Use `.get()` for safe access, and `.items()`, `.keys()`, `.values()` for iteration.
7. Build and query a list of dictionaries representing tabular data.

---

## Files in This Chapter

| File | Purpose |
|---|---|
| `prep/session-prep.md` | Pre-reading: objectives, pitfalls, prerequisites |
| `lecture/03-lecture.ipynb` | Full lecture notebook |
| `lab/03-tp-data-structures.ipynb` | Student lab workbook |
| `lab/03-tp-solutions.ipynb` | Worked solutions with explanations |

---

## Key Data

The `assets/sensor_data.csv` file is represented inline in this chapter's notebooks. Chapter 5 shows how to load it from disk.

---

## Key Pitfalls to Watch

- `.sort()` returns `None`; use `sorted()` when you need a new sorted list.
- `.remove()` removes the **first** occurrence only.
- Dictionary key access `d[key]` raises `KeyError` if the key is missing; always use `.get()` when existence is uncertain.
- Lists are mutable — assignments like `b = a` do NOT copy; both `a` and `b` refer to the same object. Use `a.copy()` for a shallow copy.
