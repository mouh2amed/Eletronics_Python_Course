# Design Decisions and Coverage Checklist

**Module**: Programmation Python — ELNI 5.5

---

## Purpose

This document records:
1. Key design decisions made during course development.
2. A traceability matrix mapping every syllabus bullet to specific files and exercises.

---

## Design Decisions

### Decision 1 — IEP Treatment

**Situation**: The official syllabus lists "IEP (Interactive Editor for Python)" as a required topic.

**Finding**: IEP's last known release is version 3.6 (approximately 2015). The project has not been actively maintained since then and has known compatibility issues with Python 3.10+ and modern operating systems. Installing IEP on a fresh 2026 machine is unreliable.

**Decision**: IEP is covered as a **historical tool** in Chapter 1 (lecture Section 1.2 and lab Exercise 6). Students learn what IEP was, what it provided, and why JupyterLab and VS Code have superseded it. The `docs/environment-setup.md` contains a dedicated "IEP Historical Note" section. This approach honours the syllabus objective (understanding IEP) without recommending a broken installation.

### Decision 2 — Python Version

**Situation**: The course specifies Python 3. The most recent stable release as of the course build date (September 2026) is Python 3.14.x; Python 3.12 is in security-only support but still widely installed.

**Decision**: Notebooks declare `"version": "3.12.0"` in their kernel metadata as a widely-deployed LTS baseline. All code is compatible with Python 3.12 and later. The `environment-setup.md` notes that Python 3.13/3.14 are also compatible.

### Decision 3 — f-strings as Standard

**Situation**: Python has three string formatting mechanisms: `%`-formatting (legacy), `.format()` (Python 3.0+), and f-strings (Python 3.6+).

**Decision**: All course materials use **f-strings exclusively** for new code. This is consistent with PEP 8 guidance and modern Python best practice. Legacy formats are shown once in `docs/style-guide.md` for recognition only.

### Decision 4 — `with` Statement for File I/O

**Situation**: Files can be opened with `open()` and manually closed with `.close()`, or managed automatically with `with open() as f:`.

**Decision**: All course materials use **only the `with` statement** for file I/O. Manual `.close()` is shown once in Chapter 5 lecture (in the `finally` block demonstration) as an illustration of what the `with` statement replaces.

### Decision 5 — List of Dicts as Tabular Data Pattern

**Situation**: Tabular data (like sensor readings) can be represented as parallel lists, a list of lists, a list of dicts, or a Pandas DataFrame.

**Decision**: The **list of dicts** pattern is used throughout Chapters 3–5. It is more readable than parallel lists and list of lists, requires no external libraries, and directly mirrors what `csv.DictReader` produces in Chapter 5.

### Decision 6 — No External Libraries Beyond stdlib + Jupyter

**Situation**: The syllabus mentions no specific libraries. Engineering courses sometimes use NumPy/Pandas.

**Decision**: The course uses **only the Python standard library** (plus Jupyter for the notebook environment). This keeps the installation simple, focuses on language fundamentals, and avoids NumPy/Pandas syntax obscuring the Python basics being learned. `requirements.txt` includes these packages for future use but none are required to run course notebooks.

### Decision 7 — Asset Files as Real Data

**Situation**: Lab exercises need realistic data.

**Decision**: Two asset files are included: `sensor_data.csv` (10 rows, temperature/pressure sensor data with one ERROR row) and `sample_log.txt` (7 lines, system event log). These files are small enough to inspect manually but realistic enough to demonstrate all file I/O concepts. The ERROR row in `sensor_data.csv` is essential for exception handling exercises.

---

## Coverage Traceability Matrix

Every bullet in the official syllabus is mapped below to the specific file(s) where it is covered.

### Chapter 1 — Getting Started with Python

| Syllabus Bullet | Covered In |
|---|---|
| Python command-line REPL | `chapters/01-getting-started/lecture/01-lecture.ipynb` §1.1; `lab/01-tp-getting-started.ipynb` Ex.4 |
| IEP (Interactive Editor for Python) | `lecture/01-lecture.ipynb` §1.2; `lab/01-tp-getting-started.ipynb` Ex.6; `docs/environment-setup.md` §6 |
| Installing Python locally | `lecture/01-lecture.ipynb` §1.3; `docs/environment-setup.md` §1 |
| IDLE GUI shipped with Python | `lecture/01-lecture.ipynb` §1.4; `lab/01-tp-getting-started.ipynb` Ex.5 |

### Chapter 2 — First Steps in Python

| Syllabus Bullet | Covered In |
|---|---|
| Arithmetic in Python | `chapters/02-first-steps/lecture/02-lecture.ipynb` §2.1; `lab/02-tp-first-steps.ipynb` Ex.1 |
| Output/printing | `lecture/02-lecture.ipynb` §2.2; `lab/02-tp-first-steps.ipynb` Ex.2 |
| Variables and types | `lecture/02-lecture.ipynb` §2.3; `lab/02-tp-first-steps.ipynb` Ex.3 |
| Strings | `lecture/02-lecture.ipynb` §2.4; `lab/02-tp-first-steps.ipynb` Ex.4 |
| Loops and conditionals | `lecture/02-lecture.ipynb` §2.5; `lab/02-tp-first-steps.ipynb` Ex.5, Ex.6 |
| Reading keyboard input | `lecture/02-lecture.ipynb` §2.6; `lab/02-tp-first-steps.ipynb` Ex.7 |

### Chapter 3 — Data Structures

| Syllabus Bullet | Covered In |
|---|---|
| Lists | `chapters/03-data-structures/lecture/03-lecture.ipynb` §3.1; `lab/03-tp-data-structures.ipynb` Ex.1, Ex.2, Ex.3 |
| Dictionaries | `lecture/03-lecture.ipynb` §3.2; `lab/03-tp-data-structures.ipynb` Ex.4, Ex.5, Ex.6 |

### Chapter 4 — Functions

| Syllabus Bullet | Covered In |
|---|---|
| Built-in functions | `chapters/04-functions/lecture/04-lecture.ipynb` §4.1; `lab/04-tp-functions.ipynb` Ex.1 |
| Simple parameterless functions | `lecture/04-lecture.ipynb` §4.2; `lab/04-tp-functions.ipynb` Ex.2 |
| Functions with parameters | `lecture/04-lecture.ipynb` §4.3; `lab/04-tp-functions.ipynb` Ex.3 |
| Default parameter values | `lecture/04-lecture.ipynb` §4.4; `lab/04-tp-functions.ipynb` Ex.4 |
| Assigning a function to a variable | `lecture/04-lecture.ipynb` §4.5; `lab/04-tp-functions.ipynb` Ex.5 |
| Variadic functions (*args/**kwargs) | `lecture/04-lecture.ipynb` §4.6; `lab/04-tp-functions.ipynb` Ex.6 |
| Mutable vs immutable argument passing | `lecture/04-lecture.ipynb` §4.7; `lab/04-tp-functions.ipynb` Ex.7 |
| Local vs global scope | `lecture/04-lecture.ipynb` §4.8; `lab/04-tp-functions.ipynb` Ex.8 |
| Anonymous (lambda) functions | `lecture/04-lecture.ipynb` §4.9; `lab/04-tp-functions.ipynb` Ex.9 |

### Chapter 5 — Files and Exception Handling

| Syllabus Bullet | Covered In |
|---|---|
| Working with current directory | `chapters/05-files-and-exceptions/lecture/05-lecture.ipynb` §5.1; `lab/05-tp-files-exceptions.ipynb` Ex.1 |
| File manipulation (read/write) | `lecture/05-lecture.ipynb` §5.2, §5.3; `lab/05-tp-files-exceptions.ipynb` Ex.2, Ex.3 |
| Copying files | `lecture/05-lecture.ipynb` §5.4; `lab/05-tp-files-exceptions.ipynb` Ex.5 |
| Writing variables to a file | `lecture/05-lecture.ipynb` §5.5; `lab/05-tp-files-exceptions.ipynb` Ex.4 |
| Exception handling | `lecture/05-lecture.ipynb` §5.6–§5.7; `lab/05-tp-files-exceptions.ipynb` Ex.6, Ex.7 |

---

## Asset File Usage

| File | Used In |
|---|---|
| `assets/sensor_data.csv` | Ch.3 lecture (inline as list of dicts); Ch.5 lecture §5.6; Ch.5 lab Ex.3, Ex.4, Ex.5, Ex.7, Stretch |
| `assets/sample_log.txt` | Ch.5 lecture §5.2; Ch.5 lab Ex.2, Ex.5, Stretch |

---

## Coverage Completeness Verification

All 22 syllabus bullets have been mapped to at least one lecture section and at least one lab exercise. No bullet is covered by lecture alone without a corresponding practical exercise.

| Status | Count |
|---|---|
| Fully covered (lecture + lab exercise) | 22 |
| Partially covered (lecture only) | 0 |
| Not covered | 0 |
