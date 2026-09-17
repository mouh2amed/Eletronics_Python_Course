# Chapter 5 — Session Preparation: Files and Exception Handling

**Weeks 11–13 | 9 contact hours**

---

## Learning Objectives

By the end of this chapter you will be able to:

1. Determine and change the current working directory using `os.getcwd()` and `os.chdir()`.
2. List directory contents with `os.listdir()` and check path existence with `os.path.exists()`.
3. Build cross-platform file paths using `os.path.join()`.
4. Open, read, and close text files using `open()` in context manager (`with`) form.
5. Read files line by line, read all lines into a list, and read entire file as a string.
6. Write text to a new file, append to an existing file.
7. Copy files using `shutil.copy()`.
8. Write variable values (numbers, strings, lists) to a text file in a structured format.
9. Parse a CSV file manually and with the `csv` module.
10. Use `try`/`except` to catch and handle specific exceptions.
11. Use `except Exception as e` to inspect error details.
12. Use `else` and `finally` clauses with `try`.
13. Raise exceptions with `raise` and a descriptive message.

---

## Why This Matters for Engineers

Every real engineering workflow involves files:

- **Reading**: loading sensor data from a CSV, reading configuration from a text file, importing coordinates from a survey file.
- **Writing**: saving processed results, generating reports, exporting data for other software.
- **Exception handling**: real data is messy. Files are missing. Lines are malformed. Sensor values are out of range. A program that crashes on the first bad line is useless. Proper exception handling makes programs robust.

Chapter 5 completes the learning arc: now you can write programs that read data from files, process it using the functions you built in Chapter 4, and write results back to files — all while handling errors gracefully.

---

## Subtopics (in order)

1. **Working with the current directory** — `os.getcwd()`, `os.chdir()`, `os.listdir()`, `os.path.exists()`, `os.path.join()`, `os.makedirs()`.
2. **File manipulation** — `open()` with modes `'r'`, `'w'`, `'a'`; the `with` statement; reading with `.read()`, `.readline()`, `.readlines()`; iterating over lines; writing with `.write()`.
3. **Copying files** — `shutil.copy()`, `shutil.copy2()`.
4. **Writing variables to a file** — formatting values as strings before writing; using CSV format; writing structured reports.
5. **Exception handling** — `try`/`except`; specific exception types (`FileNotFoundError`, `ValueError`, `ZeroDivisionError`); `except Exception as e`; `else`; `finally`; `raise`.

---

## Prerequisite Check

Before Week 11, confirm:

- [ ] Chapters 1–4 complete: you are comfortable with variables, loops, functions, and dictionaries.
- [ ] You can navigate your filesystem from the command line.
- [ ] The `assets/sensor_data.csv` and `assets/sample_log.txt` files are present in the course repository.
- [ ] You understand what a relative vs absolute file path is.

---

## Time Budget

| Activity | Duration |
|---|---|
| Week 11 lecture: current directory, file read/write, shutil | 3 h |
| Week 12 lecture: CSV handling, writing structured data | 3 h |
| Week 13 lecture: exception handling — try/except/else/finally/raise | 3 h |
| Self-study and lab practice | ~3 h recommended |

---

## Common Misconceptions and Pitfalls

**Forgetting to close files**
`f = open('data.txt')` must be followed by `f.close()`. The `with open(...) as f:` pattern handles this automatically — always use the `with` form.

**Mode overwrites without warning**
`open('file.txt', 'w')` silently overwrites any existing file. If you want to append, use `'a'`. If you want to check first, use `os.path.exists()`.

**Relative paths and the CWD**
`open('sensor_data.csv')` looks in the current working directory. In Jupyter, the CWD is the directory containing the notebook. Confirm with `os.getcwd()` before opening files.

**Bare `except:` clause**
`except:` catches everything including `KeyboardInterrupt` and `SystemExit`. Always catch specific exceptions or at least use `except Exception:`. Catching too broadly hides bugs.

**`ValueError` from int() on bad strings**
`int("22.5")` raises `ValueError`. Always use `float()` for decimal numbers, and wrap type conversions in `try/except ValueError`.

**Raising vs printing an error**
`print("Error!")` and continuing is not error handling — it silently continues with bad data. `raise ValueError("...")` stops execution at the right place and gives the caller a chance to handle it.

---

## What to Have Ready for Class

- Both asset files accessible: confirm `os.path.exists('../../assets/sensor_data.csv')` returns `True` from the lab directory (or adjust the path as needed).
- A text editor to inspect the asset files directly.
- A clear picture of the directory structure: where is the notebook relative to `assets/`?
