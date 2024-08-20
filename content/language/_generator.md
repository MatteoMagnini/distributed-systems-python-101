+++

title = "The Python Programming Language"
description = "Introduction to the Python programming language"
outputs = ["Reveal"]

+++

# The Python Programming Language

{{% import path="reusable/header.md" %}}

---

## Compiled vs Interpreted Languages

- **Compiled languages** are translated (i.e. compiled) into machine code before they are run.
  + usually _faster_ (can also be optimised by the compiler) to execute than interpreted languages
  + _type checking_ is done during compilation
  + __less portable__ (need to recompile for different platforms)
  + e.g. C, C++, Java
- **Interpreted languages** are the input of the interpreter, which executes the code directly.
  + usually __slower to execute__ than compiled languages
  + but they can be faster if we consider the whole compilation and execution process
  + more _flexible_ (e.g. dynamic typing, reflection)
  + e.g. Python, Ruby, JavaScript 

---

## Python

- _Python_ is an _interpreted_, high-level, general-purpose programming language.
- It is quite old, the first release is in 1991 (currently in version 3).
- Now it is one of the most popular programming languages in the world 
  + especially in the field of _data science_ and _machine learning_.

---


# Getting Started

(a.k.a. run a hello world program)

---

## Python Command Line

- To run Python code interactively, you can use the Python command line.
- Just type `python` in the terminal.

{{<short_code "python">}}
>>> print("Hello, World!")
Hello, World!
{{</short_code>}}

- To leave the Python command line, type `exit()` or press `Ctrl+D`.


---

## Python Scripts

- You can also write Python code in a file and run it.
- Create a file with a `.py` extension (e.g. `hello.py`).
- Write your Python code in the file.

{{<short_code "python">}}
# hello.py
print("Hello, World!")
{{</short_code>}}

- Run the script with `python hello.py`.

---

## Python IDEs

- There are many _Integrated Development Environments_ (IDEs) for Python.
- Some popular ones are:
  + _PyCharm_ (by JetBrains) [/Recommended/]
  + _Visual Studio Code_ (by Microsoft)
- In PyCharm, you can create a new Python file by right-clicking on the project and selecting `New -> Python File`.
- You can run the script by right-clicking on the file and selecting `Run`.

---

# Variables, data types, functions and more

---

## Variables

- In Python, you don't need to declare the type of a variable.

```python
x = 5  # x is an integer  
pi = 3.14159  # pi is a float
number_of_stars_in_the_galaxy = 10E11  # you can use scientific notation
true_value = True  # boolean
special_value = None  # None is a special value (similar to null in other languages)
welcome_message = "Hello, World!"  # string
course_teachers = ["Andrea Omicini", "Giovanni Ciatto", "Matteo Magnini"]  # list (of strings)
you_can_do_this = [47521, "Cesena", True, None]  # list (of mixed types)
one_digits = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}  # set (non-repeating elements)
booleans = (True, False)  # tuple (immutable list)
emails = {
  "Andrea": "andrea.omicini@unibo.it",
  "Giovanni": "giovanni.ciatto@unibo.it",
  "Matteo": "matteo.magnini@unibo.it"
}  # dictionary (key-value pairs, keys must be unique and immutable)
```