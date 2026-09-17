# Grading and Course Structure

**Module**: Programmation Python — ELNI 5.5
**Semester**: 5
**Coefficient**: 2 | **Credits**: 3
**Total volume**: 45 hours

---

## Course Structure

### Pacing Overview

| Chapter | Topic | Weeks | Lecture Hours | Lab (TP) Hours |
|---|---|---|---|---|
| 1 | Getting Started with Python | 1–2 | 6 | 0 |
| 2 | First Steps in Python | 3–5 | 9 | 0 |
| 3 | Data Structures | 6–7 | 6 | 0 |
| 4 | Functions | 8–10 | 9 | 0 |
| 5 | Files and Exception Handling | 11–13 | 9 | 0 |
| **Total** | | **13 weeks** | **39h** | **6h** |

> The 45-hour volume includes 3 contact hours per week across 13 teaching weeks (39h) plus 6 hours of scheduled laboratory/practical sessions (TPs). Additional self-study is expected outside contact hours.

---

## Grading Components

### Assessment Structure

| Component | Weight | Description |
|---|---|---|
| Lab (TP) reports | 30% | Submitted Jupyter notebooks from each chapter lab |
| Mid-semester exam | 30% | Written test covering Chapters 1–3 (end of Week 7) |
| Final exam | 40% | Written/practical test covering all chapters (end of Week 13) |

### Lab Report Grading Rubric

Each submitted TP notebook is graded out of 20 points:

| Criterion | Points | Description |
|---|---|---|
| Correctness | 8 | Code runs without errors; output matches expected results |
| Coverage | 4 | All required exercises completed; no TODOs left |
| Style | 4 | PEP 8 compliant; descriptive names; f-strings used |
| Documentation | 2 | Each function has a docstring; comments explain reasoning |
| Stretch goal | 2 | Bonus for completing the stretch exercise |

### Exam Format

**Mid-semester exam (45 minutes)**
- Part A: Short answer — trace through code and predict output (6 points)
- Part B: Fill in the blank — complete partially written programs (8 points)
- Part C: Write a short program from a specification (6 points)

**Final exam (90 minutes)**
- Part A: Trace and explain code (8 points)
- Part B: Debug and fix errors in given code (6 points)
- Part C: Write complete programs from specifications (6 points, two problems)

---

## Repository Layout Explained

```
python-programming-course/
├── README.md                   ← Start here
├── docs/                       ← Course administration documents
│   ├── syllabus.md             ← Official syllabus content
│   ├── environment-setup.md    ← Installation instructions
│   ├── grading-and-structure.md← This file
│   ├── style-guide.md          ← Python coding conventions
│   └── decisions.md            ← Coverage traceability matrix
├── environment/                ← Dependency files
│   ├── requirements.txt        ← pip install list
│   └── environment.yml         ← conda environment spec
├── chapters/                   ← Course content, one folder per chapter
│   ├── 01-getting-started/
│   │   ├── prep/session-prep.md        ← Instructor/student pre-reading
│   │   ├── lecture/01-lecture.ipynb    ← Lecture notebook (run in class)
│   │   ├── lab/01-tp-getting-started.ipynb  ← Student lab workbook
│   │   ├── lab/01-tp-solutions.ipynb   ← Worked solutions (instructor copy)
│   │   └── README.md                   ← Chapter overview
│   ├── 02-first-steps/         ← (same structure)
│   ├── 03-data-structures/     ← (same structure)
│   ├── 04-functions/           ← (same structure)
│   └── 05-files-and-exceptions/← (same structure)
└── assets/                     ← Shared data files
    ├── sensor_data.csv         ← Temperature/pressure sensor log (10 rows)
    └── sample_log.txt          ← System event log file
```

---

## How to Use the Materials

### For Students

1. **Before each lecture**: Read `prep/session-prep.md` for the corresponding chapter. This lists the learning objectives and prerequisite checks.
2. **During lecture**: Work through `lecture/XX-lecture.ipynb` with the instructor. All cells are runnable — experiment freely.
3. **After lecture / lab session**: Complete `lab/XX-tp-*.ipynb`. Exercises are numbered in order of difficulty. Do not open the solutions file until you have made a genuine attempt.
4. **Self-check**: Compare your work against `lab/XX-tp-solutions.ipynb` to understand alternative approaches.

### For Instructors

- The lecture notebooks are designed to be run top-to-bottom in class. "Check your understanding" cells are natural pause points for discussion.
- The lab notebooks include `# TODO` markers indicating exactly what students must fill in. The surrounding code provides scaffolding.
- Solution notebooks include prose explanations — suitable for posting after lab sessions.

---

## Academic Integrity Policy

All submitted lab notebooks must represent the student's own work. The following are permitted:
- Consulting lecture notebooks and course notes.
- Searching Python official documentation (https://docs.python.org).
- Discussing concepts with classmates (but not sharing code).

The following are not permitted:
- Submitting another student's notebook as your own work.
- Copying solutions from online sources without attribution and understanding.
- Using AI code-generation tools for assessed submissions unless explicitly permitted.

---

## Prerequisites

Students enrolling in this module are expected to:
- Understand binary, decimal, and hexadecimal number representations.
- Have elementary exposure to algorithmic thinking (flowcharts or pseudocode).
- Be able to operate a computer file system (create folders, navigate paths).

No prior Python experience is required.

---

## Learning Outcomes

Upon successful completion of this module, the student will be able to:

1. Install and configure a Python development environment.
2. Use the Python REPL and IDLE for interactive exploration.
3. Write Python programs performing arithmetic, string manipulation, and formatted output.
4. Declare and use variables of appropriate types; apply type conversion.
5. Control program flow using `if/elif/else` and `for`/`while` loops.
6. Read data from the keyboard using `input()`.
7. Create, index, slice, and manipulate Python lists.
8. Create and query Python dictionaries.
9. Define and call functions with positional, keyword, default, and variadic parameters.
10. Understand and apply variable scope rules.
11. Write lambda (anonymous) functions.
12. Read, write, and append text files using Python's built-in file I/O.
13. Handle runtime errors using `try/except/finally` blocks.
14. Navigate and manipulate the filesystem using the `os` module.
