# Chapter 1 — Session Preparation: Getting Started with Python

**Weeks 1–2 | 6 contact hours**

---

## Learning Objectives

By the end of this chapter you will be able to:

1. Explain what Python is and why it is widely used in engineering and scientific computing.
2. Start an interactive Python session using the REPL (command-line shell) and evaluate simple expressions.
3. Open and use IDLE, the graphical editor bundled with Python.
4. Explain the historical role of IEP and why modern tooling (JupyterLab, VS Code) has superseded it.
5. Verify a successful Python installation by checking the version from the command line.
6. Write and run a minimal Python script (`hello.py`) from both the terminal and IDLE.
7. Navigate the Jupyter Notebook interface and execute code cells.

---

## Why This Matters for Engineers

Python has become the dominant scripting and automation language in engineering disciplines. Civil, structural, mechanical, and electrical engineers use it to:

- Automate repetitive calculations (beam load tables, unit conversions, factor-of-safety sweeps).
- Process measurement data from sensors and data-acquisition systems.
- Prototype numerical algorithms before implementing them in C or MATLAB.
- Produce publication-quality plots from lab data.

In this course you will build skills directly transferable to professional engineering practice. Every concept introduced — even something as basic as "how to run a Python script" — is a foundational competency in the modern engineering workflow.

---

## Subtopics (in order)

These match the official syllabus bullets for Chapter 1:

1. **What is Python?** — interpreted, dynamically typed, open-source; version history (2 vs 3); the Python Software Foundation.
2. **The Python command-line REPL** — launching `python` or `python3`; the `>>>` prompt; evaluating expressions; `exit()`.
3. **IEP — Interactive Editor for Python** — historical context; what it provided; why it is no longer maintained; modern equivalents.
4. **Installing Python locally** — downloading from python.org; PATH configuration; verifying installation.
5. **IDLE — the built-in GUI** — launching IDLE; the shell window; the script editor; running a file with F5.

---

## Prerequisite Check

Before attending Week 1, confirm you can do the following:

- [ ] Open a terminal (Command Prompt on Windows; Terminal on macOS/Linux).
- [ ] Navigate directories with `cd`.
- [ ] Create a text file with a text editor (Notepad, gedit, TextEdit, etc.).
- [ ] Download a file from the internet and locate it afterwards.

If any of these feel uncertain, spend 30 minutes on a command-line basics tutorial before the first session.

---

## Time Budget

| Activity | Duration |
|---|---|
| Week 1 lecture: REPL, installation, IDLE demo | 3 h |
| Week 2 lecture: Jupyter environment, first scripts | 3 h |
| Self-study / lab practice outside contact hours | ~2 h recommended |

---

## Common Misconceptions and Pitfalls

**"Python 2 still works, so why use Python 3?"**
Python 2 reached end-of-life in January 2020. All course materials use Python 3.12. Never install Python 2 for new work.

**"`python` vs `python3` on the command line"**
On some systems (particularly macOS and Linux), `python` may still invoke Python 2, while `python3` invokes Python 3. Always check with `python --version` or `python3 --version`. On Windows with a clean Python 3 install, `python` is correct.

**"Forgetting to tick 'Add Python to PATH' on Windows"**
This is the single most common Windows setup error. If `python` is not recognized in the terminal, this is almost certainly the cause. The fix is to reinstall, ticking that checkbox.

**"IDLE is only a shell"**
Students sometimes use IDLE only as an interactive shell and do not discover the File → New File script editor. Make sure to use both.

**"Jupyter is complicated"**
Jupyter Notebook/Lab is simply a web application running locally. Nothing is uploaded to the internet. Your browser is just being used as a display.

---

## What to Have Ready for Class

- Python 3.12 installed and `python --version` returning the correct version.
- IDLE launching successfully from the Start menu (Windows) or terminal.
- The virtual environment created and activated (see `docs/environment-setup.md`).
- JupyterLab installed (`pip install jupyterlab`) and launching with `jupyter lab`.
- The course repository folder accessible in JupyterLab.
