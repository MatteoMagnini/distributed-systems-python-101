+++

title = "Managing a Python Project"
description = "Introduction to managing a Python project"
outputs = ["Reveal"]

+++

# Modules and Packages

---

## Modules

- A _module_ is a folder with a file named `__init__.py` and possibly one or more `.py` files.
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