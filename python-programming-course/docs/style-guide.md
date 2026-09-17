# Code Style Guide

**Module**: Programmation Python — ELNI 5.5
**Applies to**: All lecture notebooks, lab notebooks, solution notebooks, and inline examples

---

## Purpose

This style guide defines the coding conventions used throughout this course. Consistency across examples helps students focus on concepts rather than formatting surprises. All code in this repository follows these rules; students are expected to follow them in submitted lab work.

The primary reference is **PEP 8** — the official Python style guide (https://peps.python.org/pep-0008/). What follows is a course-specific summary of the most important rules, with engineering-context examples.

---

## 1. Indentation

Use **4 spaces** per indentation level. Never use tabs.

```python
# Correct
def compute_area(length, width):
    area = length * width
    return area

# Incorrect — 2-space indentation
def compute_area(length, width):
  area = length * width
  return area
```

---

## 2. Line Length

Keep lines to a maximum of **88 characters**. This is the `black` formatter default, slightly relaxed from PEP 8's 79-character limit, and suits modern wide-screen editors.

For long expressions, break with a backslash or use parentheses:

```python
# Using parentheses for line continuation (preferred)
total_force = (
    mass * acceleration
    + friction_coefficient * normal_force
)
```

---

## 3. Blank Lines

- Two blank lines surround top-level function and class definitions.
- One blank line separates logical sections inside a function.
- One blank line may separate groups of related `import` statements.

```python
import math
import os


def celsius_to_kelvin(temp_c):
    """Convert Celsius to Kelvin."""
    return temp_c + 273.15


def kelvin_to_celsius(temp_k):
    """Convert Kelvin to Celsius."""
    return temp_k - 273.15
```

---

## 4. Imports

- One import per line.
- Standard library imports first, then third-party, then local — each group separated by a blank line.
- Use explicit imports; avoid `from module import *`.

```python
import os
import math
import csv

import numpy as np        # third-party (if used)

from utils import helpers  # local module (if applicable)
```

---

## 5. Naming Conventions

| Entity | Convention | Example |
|---|---|---|
| Variables | `snake_case` | `beam_length`, `sensor_id` |
| Functions | `snake_case` | `calculate_stress()`, `read_sensor()` |
| Constants | `UPPER_SNAKE_CASE` | `GRAVITY = 9.81`, `MAX_TEMP = 150.0` |
| Classes | `PascalCase` | `SensorReading`, `BeamSection` |
| Module files | `snake_case` | `data_utils.py` |

Choose **descriptive names**. For engineering code, unit suffixes in names are strongly encouraged:

```python
# Good — units are clear
temperature_celsius = 22.5
pressure_kpa = 101.3
beam_length_m = 5.0

# Bad — ambiguous units
temp = 22.5
p = 101.3
l = 5.0
```

---

## 6. String Formatting — Use f-strings

Always prefer **f-strings** (Python 3.6+) over `%`-formatting or `str.format()`.

```python
sensor_id = "S1"
temperature = 22.3
unit = "°C"

# Correct — f-string
print(f"Sensor {sensor_id}: {temperature:.1f} {unit}")

# Acceptable but older style
print("Sensor {}: {:.1f} {}".format(sensor_id, temperature, unit))

# Avoid — legacy percent formatting
print("Sensor %s: %.1f %s" % (sensor_id, temperature, unit))
```

Use format specifiers for numeric precision, especially in engineering output:

```python
pi_approx = 3.14159265
print(f"Pi ≈ {pi_approx:.4f}")        # 4 decimal places
print(f"Force: {force_n:>10.2f} N")   # right-aligned, 2 decimals
```

---

## 7. Comments

- Comments explain **why**, not what. The code itself should be clear enough to show what.
- Write comments in complete sentences, starting with a capital letter.
- Inline comments are acceptable but use sparingly; place them after two spaces following the code.

```python
GRAVITY = 9.81  # m/s², standard acceleration due to gravity

# Filter out faulty sensor readings before computing statistics.
valid_readings = [t for t in temperatures if t > -100]
```

---

## 8. Docstrings

Every function defined in lab work must have a docstring. Use the single-line form for simple functions, the multi-line form for anything that takes parameters.

```python
def celsius_to_fahrenheit(temp_c):
    """Convert a Celsius temperature to Fahrenheit."""
    return temp_c * 9 / 5 + 32


def compute_stress(force_n, area_m2):
    """
    Compute normal stress given applied force and cross-sectional area.

    Parameters
    ----------
    force_n : float
        Applied force in Newtons.
    area_m2 : float
        Cross-sectional area in square metres.

    Returns
    -------
    float
        Normal stress in Pascals (N/m²).
    """
    if area_m2 <= 0:
        raise ValueError("Area must be positive.")
    return force_n / area_m2
```

---

## 9. Magic Numbers

Avoid unexplained numeric literals. Assign them to named constants.

```python
# Bad
distance = 0.5 * 9.81 * time ** 2

# Good
GRAVITY = 9.81  # m/s²
distance = 0.5 * GRAVITY * time ** 2
```

---

## 10. Truth Tests

Use Python's natural truthiness; avoid comparing to `True`, `False`, or `None` with `==`.

```python
# Correct
if readings:
    process(readings)

if sensor_active:
    take_measurement()

if result is None:
    handle_missing()

# Incorrect
if len(readings) != 0:
    process(readings)

if sensor_active == True:
    take_measurement()
```

---

## 11. Whitespace Around Operators

Single space on both sides of binary operators; no space before a colon in slices.

```python
# Correct
stress = force / area
readings[1:5]
result = a + b * c

# Incorrect
stress=force/area
readings[1 : 5]
```

---

## 12. Automatic Formatting

The `black` formatter (included in `requirements.txt`) applies most of these rules automatically. To format a file:

```bash
black my_script.py
```

Using `black` before submitting lab work is strongly encouraged.

---

## Summary Checklist

Before submitting any Python file or notebook, verify:

- [ ] 4-space indentation throughout
- [ ] Lines ≤ 88 characters
- [ ] Descriptive, snake_case variable and function names
- [ ] f-strings used for all string formatting
- [ ] Every function has a docstring
- [ ] No magic numbers — constants are named
- [ ] Comments explain reasoning, not mechanics
- [ ] No unused imports or variables
