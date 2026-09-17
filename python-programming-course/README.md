# Python Programming Course — ELNI 5.5

**Programmation Python** | Semester 5 | Coefficient 2 | 3 Credits | 45 hours

A complete, hands-on university course repository for the official Algerian engineering-school module *Programmation Python* (code ELNI 5.5). All materials are in English, publication-quality, and ready to use.

---

## Quick Start

### 1. Prerequisites

- Python 3.12 or later installed (see `docs/environment-setup.md`)
- A terminal (Command Prompt, PowerShell, or bash)

### 2. Set Up the Environment

```bash
# Clone or download this repository, then:
cd python-programming-course

# Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate          # Linux/macOS
.venv\Scripts\activate.bat         # Windows CMD

# Install dependencies
pip install -r environment/requirements.txt
```

### 3. Launch Jupyter

```bash
jupyter lab
```

Open any chapter notebook in the `chapters/` folder and start learning.

---

## Course Overview

| Chapter | Topic | Weeks | Hours |
|---|---|---|---|
| 1 | Getting Started with Python | 1–2 | 6h |
| 2 | First Steps in Python | 3–5 | 9h |
| 3 | Data Structures | 6–7 | 6h |
| 4 | Functions | 8–10 | 9h |
| 5 | Files and Exception Handling | 11–13 | 9h |

---

## Repository Structure

```
python-programming-course/
├── README.md                          ← You are here
├── docs/
│   ├── syllabus.md                    ← Official module syllabus
│   ├── environment-setup.md           ← Installation and setup guide
│   ├── grading-and-structure.md       ← Assessment and course structure
│   ├── style-guide.md                 ← Python coding conventions
│   └── decisions.md                   ← Design decisions + coverage checklist
├── environment/
│   ├── requirements.txt               ← pip dependencies
│   └── environment.yml                ← conda environment
├── assets/
│   ├── sensor_data.csv                ← Sensor data (10 rows, used in Ch.3 & 5)
│   └── sample_log.txt                 ← System event log (used in Ch.5)
└── chapters/
    ├── 01-getting-started/
    │   ├── prep/session-prep.md
    │   ├── lecture/01-lecture.ipynb
    │   ├── lab/01-tp-getting-started.ipynb
    │   ├── lab/01-tp-solutions.ipynb
    │   └── README.md
    ├── 02-first-steps/
    ├── 03-data-structures/
    ├── 04-functions/
    └── 05-files-and-exceptions/
```

---

## For Students

### How to Study

1. **Before each chapter**: Read `chapters/XX/prep/session-prep.md`. It lists the learning objectives, tells you what to install, and warns you about common mistakes.

2. **During lecture**: Open `chapters/XX/lecture/XX-lecture.ipynb` in JupyterLab. Run every code cell. Experiment with the examples. The "Check Your Understanding" cells are mini-exercises — try them before reading the answers.

3. **Lab work**: Complete `chapters/XX/lab/XX-tp-*.ipynb`. Fill in every `# TODO`. Do not look at solutions until you have made a genuine attempt.

4. **Review**: Check your work against `chapters/XX/lab/XX-tp-solutions.ipynb`. Read the explanations, not just the code.

### File Naming Convention

| Pattern | Meaning |
|---|---|
| `XX-lecture.ipynb` | Lecture notebook — run with instructor |
| `XX-tp-*.ipynb` | Lab workbook — student's own work |
| `XX-tp-solutions.ipynb` | Worked solutions — post-lab reference |
| `session-prep.md` | Pre-reading for the chapter |

---

## For Instructors

### Delivery Notes

- Lecture notebooks are designed to be run top-to-bottom in class. Each chapter's notebook covers its full 2–3 week content.
- "Check Your Understanding" cells make natural pause points for class discussion.
- Lab notebooks contain `# TODO` markers. The surrounding code provides scaffolding appropriate for first-year students.
- Solution notebooks include prose explanations before each code solution — suitable for releasing after lab sessions.

### Assessment

| Component | Weight |
|---|---|
| TP lab reports (5 × submitted notebooks) | 30% |
| Mid-semester exam (covers Chapters 1–3) | 30% |
| Final exam (covers all chapters) | 40% |

Full rubric in `docs/grading-and-structure.md`.

---

## Documentation Index

| Document | Contents |
|---|---|
| `docs/syllabus.md` | Official module syllabus with detailed weekly breakdown |
| `docs/environment-setup.md` | Step-by-step installation guide for Windows, macOS, Linux |
| `docs/grading-and-structure.md` | Assessment components, rubrics, and how to use the materials |
| `docs/style-guide.md` | PEP 8 summary, f-strings, naming, docstrings |
| `docs/decisions.md` | Design decisions + full syllabus coverage traceability matrix |

---

## Learning Outcomes

Upon completing this course, students will be able to:

1. Install and configure a Python development environment (IDLE, JupyterLab, VS Code).
2. Use the Python REPL for interactive computation.
3. Write programs using arithmetic, formatted output, variables, strings, loops, and conditionals.
4. Read keyboard input and perform type conversion.
5. Create and manipulate lists and dictionaries.
6. Define and use functions with positional, keyword, default, and variadic parameters.
7. Understand variable scope and write lambda functions.
8. Read, write, and copy files using Python's standard library.
9. Parse CSV data and write structured output.
10. Handle runtime errors with `try/except/else/finally` and raise informative exceptions.

---

## Technical Requirements

| Component | Version |
|---|---|
| Python | 3.12+ |
| JupyterLab | 4.0+ |
| Notebook | 7.0+ |
| Operating system | Windows 10+, macOS 12+, or any modern Linux |

All notebooks are valid JSON and run without errors on Python 3.12+. No external libraries beyond the standard library are required to run course content.

---

## Module Information

| Field | Value |
|---|---|
| Module code | ELNI 5.5 |
| Full name | Programmation Python |
| Semester | 5 |
| Coefficient | 2 |
| Credits | 3 ECTS |
| Total volume | 45 hours (3h/week × 15 weeks) |
| Language | English |
