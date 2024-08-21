+++

title = "Managing a Python Project"
description = "Introduction to managing a Python project"
outputs = ["Reveal"]

+++

# Modules and Packages

---

## Modules

- A _module_ is a file containing Python definitions and statements.
- You can import a module with the `import` keyword.
- You can import a specific function or class from a module with the `from` keyword.
- You can also import a module with an alias with the `as` keyword.

```python
# You can import a module
import math as m
from math import sqrt

# You can use the imported module
x = m.sqrt(25)  # 5
y = sqrt(36)  # 6
```

- `math` is a built-in module in Python.
- You can find the list of built-in modules in the [Python Standard Library](https://docs.python.org/3/library/index.html).

---

## Packages

- A _package_ is a collection of modules.
- A package is a directory containing a file named `__init__.py`.
- You can import a package with the `import` keyword.
- You can import a specific module from a package with the `from` keyword.

```python
# You can import a package
import numpy

# You can import a module from a package
from numpy import random

# You can use the imported package
y = random.randint(1, 10)  # random integer between 1 and 10
```

- `numpy` is a third-party package in Python!

---

## Project Structure

- A Python project typically has the following structure:

```bash
<root directory>
├── <package>/
│   ├── __init__.py
│   └── <module>.py
├── test/
│   └── test_<module>.py
├── .github/
│   └── workflows/
│       └── check.yml
├──.gitignore
├──.gitattributes
├──__main__.py
├── LICENSE
├── pyproject.toml
├── poetry.toml
└── README.md
```

- `<root directory>` is the main directory of the project.
- `<package>` is the main package of the project.
- `<module>` is a module in the package.
- `__main__.py` is the application entry point.
- `pyproject.toml` declares build dependencies.
- `poetry.toml` is the Poetry settings file.
