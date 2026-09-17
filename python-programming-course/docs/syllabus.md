# Official Course Syllabus

## Module Information

| Field | Value |
|---|---|
| Module name | Programmation Python |
| Module code | ELNI 5.5 |
| Semester | 5 |
| Coefficient | 2 |
| Credits | 3 |
| Total volume | 45 hours |
| Contact hours | 3 hours/week × 15 weeks |
| Weekly format | Lecture (cours magistral) + practical sessions (travaux pratiques) |

---

## Course Objective

To provide students with a complete introduction to the Python programming language, covering syntax, data structures, functions, file handling, and exception handling, reinforced by hands-on laboratory sessions (TPs).

---

## Target Audience

First-year engineering students (Semester 5) in structural, civil, and general engineering programmes. Students are expected to have basic algorithmic literacy (flowcharts, pseudocode) but no prior Python experience.

---

## Weekly Schedule and Chapter Breakdown

| Week(s) | Chapter | Topics |
|---|---|---|
| 1–2 | Chapter 1 — Getting Started with Python | Python command-line REPL; IEP tool (historical context); installing Python locally; IDLE GUI |
| 3–5 | Chapter 2 — First Steps in Python | Arithmetic operators; `print()` and formatted output; variables and data types; strings and string methods; loops (`for`, `while`) and conditionals (`if/elif/else`); reading keyboard input with `input()` |
| 6–7 | Chapter 3 — Data Structures | Lists: creation, indexing, slicing, methods, comprehensions; Dictionaries: key-value pairs, access, iteration, nested structures |
| 8–10 | Chapter 4 — Functions | Built-in functions; parameterless functions; functions with parameters; default parameter values; assigning functions to variables; variadic functions (`*args`, `**kwargs`); mutable vs immutable argument passing; local vs global scope; anonymous lambda functions |
| 11–13 | Chapter 5 — Files and Exception Handling | Working with the current directory (`os` module); file reading and writing; copying files (`shutil`); writing variables to files; exception handling (`try/except/else/finally`); raising exceptions |

---

## Detailed Syllabus

### Chapter 1 — Getting Started with Python (Weeks 1–2)

**Estimated time**: 6 hours (2 × 3h lectures)

1.1 What is Python? — history, characteristics, Python 2 vs Python 3
1.2 The Python command-line REPL — launching `python`/`python3`; the `>>>` prompt; evaluating expressions; `exit()`
1.3 IEP — Interactive Editor for Python — historical overview; IEP features; modern successors (JupyterLab, VS Code)
1.4 Installing Python locally — downloading from python.org; PATH configuration on Windows; verification
1.5 IDLE — Python's built-in GUI — shell window; script editor; running scripts with F5

### Chapter 2 — First Steps in Python (Weeks 3–5)

**Estimated time**: 9 hours (3 × 3h lectures)

2.1 Arithmetic in Python — operators `+`, `-`, `*`, `/`, `//`, `%`, `**`; operator precedence; `math` module
2.2 Output and printing — `print()` with multiple arguments; `sep` and `end` parameters; f-string format specifiers
2.3 Variables and types — assignment; `int`, `float`, `str`, `bool`, `None`; `type()` function; type conversion
2.4 Strings — string literals; indexing; slicing; methods: `.strip()`, `.split()`, `.upper()`, `.lower()`, `.find()`, `.replace()`; `len()`
2.5 Loops and conditionals — `if/elif/else`; comparison and boolean operators; `for` loops over `range()` and sequences; `while` loops; `break` and `continue`; `enumerate()`
2.6 Reading keyboard input — `input()` function; type conversion of input

### Chapter 3 — Data Structures (Weeks 6–7)

**Estimated time**: 6 hours (2 × 3h lectures)

3.1 Lists — creation; indexing and slicing; mutability; `append()`, `insert()`, `remove()`, `pop()`, `sort()`, `reverse()`; `len()`, `min()`, `max()`, `sum()`, `sorted()`; `in` operator; list comprehensions
3.2 Dictionaries — creation; key-value access; `.get()` for safe access; adding, updating, and deleting entries; `.keys()`, `.values()`, `.items()`; iteration; nested dictionaries; list of dictionaries pattern

### Chapter 4 — Functions (Weeks 8–10)

**Estimated time**: 9 hours (3 × 3h lectures)

4.1 Built-in functions — review of `print`, `len`, `range`, `type`, `abs`, `round`, `min`, `max`, `sum`, `sorted`, `enumerate`, `zip`; `help()` documentation
4.2 Simple parameterless functions — `def` syntax; return vs print
4.3 Functions with parameters — positional arguments; multiple return values; docstrings
4.4 Default parameter values — optional arguments; mutable default anti-pattern
4.5 Assigning a function to a variable — first-class functions; passing as arguments; function dispatch dictionaries
4.6 Variadic functions — `*args` (arbitrary positional arguments); `**kwargs` (arbitrary keyword arguments)
4.7 Mutable vs immutable argument passing — behaviour with integers/strings vs lists/dictionaries
4.8 Local and global scope — LEGB rule; the `global` keyword; why to avoid global variables
4.9 Lambda (anonymous) functions — `lambda` syntax; use with `sorted()`, `map()`, `filter()`

### Chapter 5 — Files and Exception Handling (Weeks 11–13)

**Estimated time**: 9 hours (3 × 3h lectures)

5.1 Working with the current directory — `os.getcwd()`, `os.chdir()`, `os.listdir()`, `os.path.exists()`, `os.path.join()`, `os.makedirs()`
5.2 File manipulation — `open()` with modes `'r'`, `'w'`, `'a'`; `with` statement; `.read()`, `.readline()`, `.readlines()`; iteration over lines; `.write()`, `.writelines()`
5.3 Copying files — `shutil.copy()`, `shutil.copy2()`
5.4 Writing variables to a file — f-string formatting for file output; CSV output with `csv.DictWriter`
5.5 Exception handling — `try/except`; catching specific exceptions; `except Exception as e`; `else`; `finally`; `raise` with descriptive messages

---

## Evaluation

| Component | Weight |
|---|---|
| Lab (TP) reports | 30% |
| Mid-semester written exam (end of Week 7) | 30% |
| Final exam (end of Week 13) | 40% |

---

## References and Resources

- **Official Python documentation**: https://docs.python.org/3/
- **PEP 8 — Style Guide for Python Code**: https://peps.python.org/pep-0008/
- **Python Tutorial (official)**: https://docs.python.org/3/tutorial/
- Course repository: all chapters, notebooks, and solutions in `chapters/`
- Environment setup: `docs/environment-setup.md`
- Code style: `docs/style-guide.md`
