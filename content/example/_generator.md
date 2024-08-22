
---

# Example (pt. 1)

## The [`calculator` repository](https://github.com/unibo-dtm-se/calculator)

1. Look at the [`pyproject.toml` file](https://github.com/unibo-dtm-se/calculator/blob/master/pyproject.toml)
    ```toml
    [tool.poetry]
    # name of the package to be published
    name = "unibo-dtm-se-calculator"

    # files to be included for publication
    packages = [
        { include = "calculator" },
    ]

    # various metadata for publication
    version = "0.1.1"
    description = "A simple calculator toolkit written in Python, with several UIs. It is part of the Software Engineering course at the University of Bologna."
    authors = ["Giovanni Ciatto <giovanni.ciatto@unibo.it>"]
    license = "Apache 2.0"
    readme = "README.md"

    # dependencies (notice that Python is considered a dependency)
    [tool.poetry.dependencies]
    python = "^3.10.0"
    Kivy = "^2.3.0"

    # development dependencies
    [tool.poetry.group.dev.dependencies]
    poetry = "^1.7.0"
    pytest = "^8.1.0"
    coverage = "^7.4.0"
    mypy = "^1.9.0"

    # executable commands that will be created then installing this package
    [tool.poetry.scripts]
    calculator-gui = "calculator.ui.gui:start_app"
    calculator = "calculator.ui.cli:start_app"

    # where to download the dependencies from
    [[tool.poetry.source]]
    name = "PyPI"
    priority = "primary"

    # packaging dependencies
    [build-system]
    requires = ["poetry-core"]
    build-backend = "poetry.core.masonry.api"

    # mypy configuration
    [tool.mypy]
    ignore_missing_imports = true
    ```

    * learn how to specify dependencies here <https://python-poetry.org/docs/dependency-specification/>

---

# Example (pt. 2)

## The [`calculator` repository](https://github.com/unibo-dtm-se/calculator)

2. Look at the [`poetry.toml` file](https://github.com/unibo-dtm-se/calculator/blob/master/poetry.toml)

    ```toml
    # the project-specific environment will be created in the local .venv folder
    [virtualenvs]
    in-project = true 

    # packages produced by poetry may be published on the pypi-test repository
    [repositories.pypi-test]
    url = "https://test.pypi.org/legacy/"

    # another implicit repository is always available, namely PyPI
    # at https://pypi.org/
    ```

---

# Exercise (pt. 1)

## The [`calculator` repository](https://github.com/unibo-dtm-se/calculator)

1. Ensure you have Poetry installed on your system
    + <https://python-poetry.org/docs/#installing-with-the-official-installer>
    + run `poetry --version` to check

2. _Fork_ the repository  

3. _Clone_ the repository on your system
    + `git clone https://github.com/unibo-dtm-se/calculator.git`
    + then, open the `calculator` folder into VS code

4. Run `poetry install` in the terminal. This shall:
    - create a _virtual environment_ in the `.venv` directory
        + please ensure that a `.venv` directory __exists__ in your project directory, after running this command
    - _install_ the _dependencies_ declared in the `pyproject.toml` file
    - _lock_ the dependencies in the `poetry.lock` file

---

## Dependency ranges and locking

* A project can depend on a specific version of a library or on a *range* of versions
* We want to be able to specify ranges, but *retain the ability to use an exact version*

> This software is compatible with `library` version 2.3. For our examples, we used version 2.3._10_

Expressing something like this is done via **dependency locking**:
* Configure the build file with the range of supported versions
* Use the build tool to *lock* the dependencies (pinpoint their version)
  * In practice, create a lock file where the exact version is explicit
* Locking usually also locks the **transitive dependencies**!
  * Once locked, we have a snapshot of a working environment

[Poetry allows range specifications and locks automatically](https://python-poetry.org/docs/dependency-specification/)

---

# Exercise (pt. 2)

## The [`calculator` repository](https://github.com/unibo-dtm-se/calculator)

5. Let's use a shell in the virtual environment created by Poetry
    + run `poetry shell`
    + if this operation was fine, you should be able to run the command `calculator 1+1` to produce `2` as output
        + if you get an error, please let us know

6. Make sure that _VS Code_ is using the _same_ environment as the one created by Poetry.
    - Open the Command Palette (on <i class="fab fa-linux"></i>/<i class="fab fa-windows"></i> press <kbd>Ctrl</kbd>+<kbd>⇧</kbd>+<kbd>P</kbd>, use <kbd>⌘</kbd> instead of <kbd>Ctrl</kbd> on <i class="fab fa-apple"></i> )
    - Type `Python: Select Interpreter`
    - Choose the local environment, i.e. the one having path `./.venv/bin/python` 

7. This is an ordinary project, where you can operate _as usual_
    - run `python -m unittest discover -v -s tests` in the terminal
    - try to run tests in the UI, too

---

## Useful hints

1. So many Python environments in the shell... how to avoid mistakes?

    > If you want to be 100% you're running commands in the _right_ environment, you can prefix them with `poetry run`:
    > ```bash
    > poetry run python -m unittest discover -v -s tests
    > ```


2. Ok but what about VS Code's environments?
    
    > Get the habit of configuring the VS Code environment _manually_ when working with Python projects
---

# What's the value added of Poetry?

It supports publishing.

> Consider the following Web Page:
> <br> <https://pypi.org/project/unibo-dtm-se-calculator>

- This is the _PyPI_ page of the `unibo-dtm-se-calculator` package
    + which we published by means of Poetry

- After the project is made available on PyPI, it can be installed by anyone 
    + by running `pip install unibo-dtm-se-calculator`

---