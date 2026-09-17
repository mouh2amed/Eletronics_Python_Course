# Chapter 5 — Files and Exception Handling

**Weeks 11–13 | 9 contact hours**

---

## Overview

The final chapter of the course. You will read the real sensor data files from `assets/`, process them with functions built in earlier chapters, write reports, and handle errors gracefully. This chapter directly demonstrates the value of everything learned in Chapters 1–4.

---

## Learning Objectives

By the end of this chapter you will be able to:

1. Navigate the filesystem using `os.getcwd()`, `os.listdir()`, `os.path.exists()`, `os.path.join()`, `os.makedirs()`.
2. Read text files using `open()` in `with` block form.
3. Read files with `.read()`, `.readlines()`, and iteration.
4. Write and append to files using `'w'` and `'a'` modes.
5. Copy files with `shutil.copy()` and `shutil.copy2()`.
6. Parse CSV files using `csv.DictReader` and write with `csv.DictWriter`.
7. Write variable values to files using f-string formatting.
8. Catch specific exceptions with `try/except`.
9. Use `else` and `finally` clauses.
10. Raise exceptions with `raise` and descriptive messages.

---

## Files in This Chapter

| File | Purpose |
|---|---|
| `prep/session-prep.md` | Pre-reading: objectives, pitfalls, prerequisites |
| `lecture/05-lecture.ipynb` | Full lecture notebook — 3 weeks of content |
| `lab/05-tp-files-exceptions.ipynb` | Student lab workbook |
| `lab/05-tp-solutions.ipynb` | Worked solutions with explanations |

---

## Data Files Used

Both files are in `assets/` at the repository root:

- `sensor_data.csv` — 10 records, 5 columns (timestamp, sensor_id, temperature_C, pressure_kPa, status)
- `sample_log.txt` — 7 log entries with INFO, WARNING, and ERROR levels

---

## Key Pitfalls

- Always use `with open(...) as f:` — never `open()` without closing.
- Mode `'w'` silently overwrites. Check with `os.path.exists()` first, or use `'a'` to append.
- Never use a bare `except:` — always catch specific exceptions.
- `finally` always runs, even if no exception was raised.
- `raise` terminates normal flow — use it to enforce preconditions.
- `csv.DictWriter` requires `newline=''` in the `open()` call on Windows to avoid blank lines.
