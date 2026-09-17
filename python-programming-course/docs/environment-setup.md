# Environment Setup Guide

**Module**: Programmation Python — ELNI 5.5
**Python version**: 3.12 (recommended) or 3.13+

---

## Overview

This guide walks you through every step needed to set up a working Python development environment on your personal machine. You will install Python, configure an editor, launch Jupyter notebooks, and verify that everything runs correctly.

The entire setup takes approximately 20–40 minutes on a fresh machine.

---

## 1. Install Python

### 1.1 Download

Visit the official Python website: **https://www.python.org/downloads/**

Download the latest **Python 3.12.x** installer for your operating system. Python 3.12 is the version tested with all course materials.

> **Note on Python 3.13/3.14**: Later versions are also compatible. If your machine already has Python 3.13 or 3.14, you do not need to downgrade.

### 1.2 Windows Installation

1. Run the downloaded `.exe` installer.
2. **Critical**: On the first screen, tick the checkbox **"Add Python 3.12 to PATH"** before clicking Install Now.
3. Choose "Install Now" for the default installation.
4. Click "Close" when installation completes.

Verify the installation by opening Command Prompt (`Win + R`, type `cmd`, press Enter) and running:

```
python --version
```

Expected output: `Python 3.12.x`

### 1.3 macOS Installation

1. Run the downloaded `.pkg` installer and follow the wizard.
2. After installation, open Terminal and run:

```bash
python3 --version
```

On macOS, use `python3` (not `python`) in all terminal commands.

### 1.4 Linux Installation

Most Linux distributions ship with Python 3. Check the version first:

```bash
python3 --version
```

If Python 3.12 is not available, install via your package manager:

```bash
# Ubuntu / Debian
sudo apt update
sudo apt install python3.12 python3.12-venv python3-pip

# Fedora
sudo dnf install python3.12
```

---

## 2. Create a Virtual Environment

A **virtual environment** is an isolated Python installation that keeps this course's packages separate from other projects on your machine. This is best practice and avoids package conflicts.

### Step-by-step

Open a terminal (Command Prompt on Windows, Terminal on macOS/Linux) and navigate to the course folder:

```bash
cd path/to/python-programming-course
```

Create the virtual environment:

```bash
# Windows
python -m venv .venv

# macOS / Linux
python3 -m venv .venv
```

Activate it:

```bash
# Windows (Command Prompt)
.venv\Scripts\activate.bat

# Windows (PowerShell)
.venv\Scripts\Activate.ps1

# macOS / Linux
source .venv/bin/activate
```

Your prompt will change to show `(.venv)` — this confirms the environment is active.

Deactivate when done:

```bash
deactivate
```

---

## 3. Install Course Dependencies

With the virtual environment active, install all required packages:

```bash
pip install -r environment/requirements.txt
```

This installs JupyterLab, the `black` code formatter, and other course tools.

Alternatively, if you use **Anaconda / Miniconda**, create the environment with:

```bash
conda env create -f environment/environment.yml
conda activate python-course
```

---

## 4. Launch Jupyter

### JupyterLab (recommended)

```bash
jupyter lab
```

This opens a browser tab at `http://localhost:8888/lab`. From there, navigate to any chapter folder and open `.ipynb` notebook files.

### Classic Jupyter Notebook

```bash
jupyter notebook
```

---

## 5. IDLE — Python's Built-In GUI Editor

Python ships with **IDLE** (Integrated Development and Learning Environment), a simple but capable graphical editor. It is the primary editor introduced in Chapter 1 of this course.

### Launch IDLE

- **Windows**: Search "IDLE" in the Start menu, or run `idle` in the terminal.
- **macOS**: Open Finder → Applications → Python 3.12 → IDLE.
- **Linux**: Run `idle3` or `idle-python3.12` in the terminal.

### IDLE Features Used in This Course

| Feature | How to access |
|---|---|
| Interactive shell | Opens by default — type Python commands directly |
| Script editor | File → New File (creates a `.py` file) |
| Run a script | Run → Run Module (F5) |
| Syntax highlighting | Automatic in both shell and editor |
| Debugger | Debug → Debugger |

IDLE is intentionally simple. Once you are comfortable with Python basics (Chapters 1–2), you are encouraged to migrate to a more feature-rich editor.

---

## 6. IEP — Historical Note

The course syllabus references **IEP (Interactive Editor for Python)**, a scientific Python IDE that was popular around 2012–2015. IEP has not been actively maintained since approximately 2015 and its last released version is 3.6. It is not recommended for new installations in 2026.

The relevant concepts from the IEP model (interactive shell + script editor side-by-side, variable explorer) are now better served by **JupyterLab** or **VS Code with the Python extension**.

---

## 7. Recommended Alternative Editors

After mastering IDLE in Chapter 1, consider moving to one of these:

### Visual Studio Code (VS Code)

- **Download**: https://code.visualstudio.com/
- Install the **Python extension** by Microsoft (ms-python.python) from the Extensions panel.
- Install the **Jupyter extension** to open `.ipynb` files directly.
- Features: IntelliSense, integrated terminal, Git integration, debugger.

### PyCharm Community Edition

- **Download**: https://www.jetbrains.com/pycharm/download/
- Full-featured Python IDE, free community edition.
- Good for larger projects beyond the scope of this course.

---

## 8. Verify Your Setup

Run the following verification script to confirm everything is working. In any terminal with the virtual environment active:

```bash
python -c "
import sys
print(f'Python version : {sys.version}')

import os
print(f'Current directory: {os.getcwd()}')

try:
    import notebook
    print(f'Jupyter Notebook : OK (version {notebook.__version__})')
except ImportError:
    print('Jupyter Notebook : NOT FOUND — run: pip install notebook')
"
```

You should see Python 3.12.x reported and Jupyter listed as OK.

---

## 9. Running the Python REPL

The **REPL** (Read–Eval–Print Loop) is the interactive Python shell. You will use it extensively in Chapter 1.

Open a terminal and type:

```bash
python
```

You will see the Python prompt `>>>`. Try:

```python
>>> 2 + 2
4
>>> print("Hello, engineering world!")
Hello, engineering world!
>>> exit()
```

On macOS/Linux use `python3` instead of `python`.

---

## 10. Troubleshooting

### `python` is not recognized (Windows)

Python was not added to PATH. Fix: Uninstall Python and reinstall, ticking "Add Python to PATH".
Alternative: Use the full path `C:\Python312\python.exe` or use the Windows Store Python.

### Permission error activating virtual environment (PowerShell)

Run PowerShell as Administrator and execute:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Then try activating again.

### Jupyter opens but kernels won't start

Ensure the virtual environment is active before launching Jupyter, and that the `ipykernel` package is installed:

```bash
pip install ipykernel
python -m ipykernel install --user --name=python-course
```

### `pip install` fails with SSL error

Upgrade pip first:

```bash
python -m pip install --upgrade pip
```

---

## Quick Reference Card

```
# One-time setup
python -m venv .venv
source .venv/bin/activate        # (Linux/macOS)
.venv\Scripts\activate.bat       # (Windows CMD)
pip install -r environment/requirements.txt

# Each session
source .venv/bin/activate
jupyter lab

# Check Python version
python --version

# Enter interactive REPL
python

# Exit REPL
exit()   or   Ctrl+D (Linux/macOS) / Ctrl+Z Enter (Windows)
```
