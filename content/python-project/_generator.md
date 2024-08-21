+++

title = "How to manage a Python Project"
description = "How to manage a Python Project"
outputs = ["Reveal"]

+++

# How to manage a Python Project

{{% import path="reusable/header.md" %}}

---

# Software Organization

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

## Dependency Management

In the package example we used `numpy`, but because it is a third-party package, we need to install it first.
In general, there could be many dependencies in a project, and it is hard to manage them manually.
The need for build systems in Python emerged with more complex use cases.
* Since there were none, now there are several tools that do build-related jobs:

|  |   |   |   |
|---|---|---|---|
| [Anaconda](https://www.anaconda.com/)  | [Conda](https://docs.conda.io/en/latest/index.html) | [Miniconda](https://docs.conda.io/en/latest/miniconda.html) | [pip](https://pypi.org/project/pip/) |
| [Poetry](https://python-poetry.org/) | [PyBuilder](https://pybuilder.io/) | [PyEnv](https://github.com/pyenv/pyenv) | [virtualenv](https://virtualenv.pypa.io/en/latest/#) |
|  |   |   |   |

* The feature set varies wildly
* They are meant to solve different problems!

---

## Python's conflicting standards

![xkcd](https://imgs.xkcd.com/comics/python_environment.png)

Since there were no standard management systems originally,
multiple tools *proliferated*

* The Python Packaging Authority (PyPA) is inconsistent in its suggestions:
    * Recommends [`venv`](https://docs.python.org/3/library/venv.html)
    * Also recommends [Pipenv](https://pipenv.pypa.io/en/latest/) , which uses [`virtualenv`](https://virtualenv.pypa.io/en/latest/)
    * Also endorses [Poetry](https://python-poetry.org/)

* Many Python developers also exploit [PyEnv](https://github.com/pyenv/pyenv)

* Many data scientists use [Anaconda](https://www.anaconda.com/)

---

## What are all these tools? (pt. 1)

1. By default, Python is installed _system-wide_
    + i.e. there should be _one_ (and __only__ one) Python interpreter on the system

2. All Python installations come with `pip`, the _package installer_ for Python

3. So, one may __install__ Python packages _system-wide_ with `pip install PACKAGE_NAME`

> __One problem, many implications__: the same package can be installed _only once_ on the same Python installation
> + __(a)__ what if two projects on the same system require _different versions_ of the _same package_ as dependencies?
>     - say, __project A__ requires `Kivy==2.3` and __project B__ requires `Kivy==1.4`
> + __(b)__ what if two projects on the same system require _different versions of Python_?
>     - say, __project A__ requires Python `3.8` and __project B__ requires Python `3.10`

---

## What are all these tools? (pt. 2)

(consider reading this page for further details <https://stackoverflow.com/a/41573588>)

4. `virtualenv` and `venv` are tools to create _virtual_ Python installations _on the same system_
    + `virtualenv` is a _third-party_ tool, `venv` is _built-in_ in Python 3.3 and later
    + let's say you have Python `v. XXX` installed on your system... 
        - ... these tools let you create other _lightweight_ __copies__ of Python `v. XXX` in other folders
            * the copies are __fresh__, i.e. they _no package_ installed
            * but one may install _different_ packages in _each_ copy, via `pip`
    + now you can solve problem __(a)__

5. `PyEnv` is a tool to manage _multiple_ Python __installations__ _on the same system_
    + each installation may use a _different version_ of Python
    + now you can solve problem __(b)__


> __New problem__: many Python installations on the same system, 
> <br> each one with a different version of Python, and different packages installed 

recall all the issues we had in previous lectures?

--- 

## What are all these tools? (pt. 3)

6. Smart and adequate __convention__ to work with Python projects: __1-project-1-Python-env__
    + each Python project has its _own_ Python environment ...
        - be it virtual or not, as far as it uses the _same_ Python version required by that project
    + ... the environment _only_ contains the packages required by that project

7. Achieving this requires developers to be _disciplined_ and _meticulous_
    + other than being proficient with the tools above

8. `Poetry` is a tool that aims to _automate_ this process

---

## From now on, let's use Poetry

> Poetry is a _declarative_ tool for __dependency management__, __packaging__, and __release__ in Python

- It handles both *dependencies* and *dev-dependencies* 
    * _replacing_ `requirements.txt` and `requirements-dev.txt`

- It _automates_ the __1-project-1-Python-env__ convention

- It simplifies the _packaging_ process for the project

- It simplifies the _publication_ process on PyPI (or other software repositories)

---

## Getting started with Poetry

- `Poetry` is a modern dependency management tool for Python.
- You can install `Poetry` with the following command:

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

- You can create a new project with the following command:

```bash
poetry new my_project 
```

- You can add a dependency with the following command:

```bash
poetry add numpy
```

- You can install all dependencies with the following command:

```bash
poetry install
```

- You can run a script with the following command:

```bash
poetry run python my_script.py
```

---

## (Poetry's canonical) Project Structure

- A Python project typically has the following structure:

```bash
<root directory>  # main directory of the project
├── <package>/  # main package of the project (there can be multiple packages)
│   ├── __init__.py  # python package marker
│   └── <module>.py  # module in the package (there can be multiple modules)
├── test/
│   └── test_<module>.py  # test module for the module
├── .github/
│   └── workflows/
│       └── check.yml  # some github action
├──.gitignore  # git ignore file
├──.gitattributes  # git attributes file (e.g., for line endings in different OS)
├──__main__.py  # application entry point
├── LICENSE  # license file (e.g., Apache 2.0)
├── pyproject.toml  # build dependencies
├── poetry.toml  # Poetry settings (we will see Poetry for dependency management)
└── README.md  # don't forget to write a README file
```
