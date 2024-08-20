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
  + _PyCharm_ (by JetBrains) \[Recommended\]
  + _Visual Studio Code_ (by Microsoft)
- In PyCharm, you can create a new Python file by right-clicking on the project and selecting `New -> Python File`.
- You can run the script by right-clicking on the file and selecting `Run`.

---

# Variables, data types, functions and more

---

## Variables

```python
# In Python, you don't need to declare the type of a variable.

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

# You can check the type of a variable with the type() function
print(type(x))  # <class 'int'>
print(type(pi))  # <class 'float'>
print(type(welcome_message))  # <class 'str'>
# and so on...
```

---

## Arithmetic Operators

You can add a `print` function call to see the result of the operations after every assignment.

```python
# Python supports the usual arithmetic operators
x = 5
y = 2
z = x + y  # 7
z = x - y  # 3
z = x * y  # 10
z = x / y  # 2.5
z = x % y  # 1 (modulo)
z = x ** y  # 25 (exponentiation)
z = x // y  # 2 (integer division)
```

Why on Earth they decided to use `//` for integer division if `**` is for exponentiation?

One would have expected `//` to be for root extraction, right?

---

## Comparison and Logical Operators

```python
# Python supports the usual comparison operators
x = 5
y = 2
z = x == y  # False
z = x != y  # True
z = x > y  # True
z = x < y  # False
z = x >= y  # True
z = x <= y  # False

# Python supports the usual logical operators
x = True
y = False
z = x and y  # False
z = x or y  # True
z = not x  # False

# Mixing comparison and logical operators
z = x + True  # 2 (True is evaluated as 1)
z = x * False  # 1 (False is evaluated as 0)
z = x and 5  # 5 (5 is evaluated as True)
z = True == 3  # False (True is not equal to 3)
z = True == 1  # True (True is equal to 1)
z = False == None  # False (False is not equal to None)
```

---

## List Operations

```python
# Python supports many operations on lists
numbers = [1, 2, 3, 4, 5]
numbers.append(6)  # [1, 2, 3, 4, 5, 6]
numbers.insert(0, 0)  # [0, 1, 2, 3, 4, 5, 6]
six = numbers.pop()  # [0, 1, 2, 3, 4, 5]
three = numbers.pop(2)  # [0, 1, 3, 4, 5]
numbers.remove(4)  # [0, 1, 3, 5]
numbers.reverse()  # [5, 3, 1, 0]
numbers.sort()  # [0, 1, 3, 5]
length = len(numbers)  # 4
is_in = 3 in numbers  # True

# You can also concatenate lists
numbers = [1, 2, 3]
more_numbers = [4, 5, 6]
all_numbers = numbers + more_numbers  # [1, 2, 3, 4, 5, 6]

# You can also multiply lists
more_numbers = numbers * 3  # [1, 2, 3, 1, 2, 3, 1, 2, 3]
two = more_numbers[1]  # 2
three_two_one = more_numbers[2:5]  # [3, 2, 1]
three_two_one = more_numbers[-3:]  # [3, 2, 1]
```

---

## Functions

```python
# You can define functions with the def keyword
def greet(name):
    return "Hello, " + name + "!"

# You can call the function with the arguments
greeting = greet("World")  # "Hello, World!"

# You can also define functions with default arguments
def greet(name="World"):
    return "Hello, " + name + "!"

greeting = greet()  # "Hello, World!"

# You can also define functions with variable arguments
def greet(*names):
    return "Hello, " + ", ".join(names) + "!"

greeting = greet("Andrea", "Giovanni", "Matteo")  # "Hello, Andrea, Giovanni, Matteo!"
```

---

## Huston, we have a problem!
```python
# we can have also lists as default arguments in functions
def add_to_list(value, lst=[]):
    lst.append(value)
    return lst

# but be careful with mutable default arguments!
print(add_to_list(1))  # [1]
print(add_to_list(2))  # [1, 2]
print(add_to_list(3))  # [1, 2, 3]

# the list is shared between all the calls

# to avoid this, you can use None as default argument
def add_to_list(value, lst=None):
    if lst is None:
        lst = []
    lst.append(value)
    return lst

print(add_to_list(1))  # [1]
print(add_to_list(2))  # [2]
print(add_to_list(3))  # [3]
```

---

## List Comprehensions

```python
# List comprehensions are a concise way to create lists
numbers = [1, 2, 3, 4, 5]
squared_numbers = [x ** 2 for x in numbers]  # [1, 4, 9, 16, 25]
even_numbers = [x for x in numbers if x % 2 == 0]  # [2, 4]

# You can also use list comprehensions with dictionaries
teachers = ["Andrea Omicini", "Giovanni Ciatto", "Matteo Magnini"]
emails = {teacher: teacher.lower().replace(" ", ".") + "@unibo.it" for teacher in teachers}

# You can also use list comprehensions with sets
numbers = {x for x in range(10) if x % 2 == 0}  # {0, 2, 4, 6, 8}

# You can also use list comprehensions with tuples
numbers = (x for x in range(10) if x % 2 == 0)  # (0, 2, 4, 6, 8)
```

---

# Object-Oriented Programming in Python

---

## Classes

```python
# You can define classes with the class keyword
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return "Hello, " + self.name + "!"

# You can create instances of the class
person = Person("Andrea", 30)
greeting = person.greet()  # "Hello, Andrea!"

# You can also define classes with inheritance
class Student(Person):
    def __init__(self, name, age, student_id):
        super().__init__(name, age)
        self.student_id = student_id

    def study(self):
        return self.name + " is studying!"

# You can create instances of the subclass
student = Student("Giovanni", 25, 12345)
study = student.study()  # "Giovanni is studying!"
```

