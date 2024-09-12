+++

title = "Introduction to the Python programming language"
description = "Introduction to the Python programming language"
outputs = ["Reveal"]

+++

# Introduction to the Python programming language

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
  ```bash
  >>> print("Hello, World!")
  Hello, World!
  ```
- To leave the Python command line, type `exit()` or press `Ctrl+D`.


---

## Python Scripts

- You can also write Python code in a file and run it.
- Create a file with a `.py` extension (e.g. `hello.py`).
- Write your Python code in the file.
  ```python
  # hello.py
  print("Hello, World!")
  ```

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

# Variables, data types, functions

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

One would have expected `//` to be for root extraction, but it is not.

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

# Kwargs are used for named arguments
def greet(**kwargs):
    return "Hello, " + kwargs["name"] + "!"

greeting = greet(name="Andrea")  # "Hello, Andrea!"

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

## Comprehensions

```python
# List comprehensions are a concise way to create lists
numbers = [1, 2, 3, 4, 5]
squared_numbers = [x ** 2 for x in numbers]  # [1, 4, 9, 16, 25]
even_numbers = [x for x in numbers if x % 2 == 0]  # [2, 4]

# Dictionary comprehensions are a concise way to create dictionaries
teachers = ["Andrea Omicini", "Giovanni Ciatto", "Matteo Magnini"]
emails = {teacher: teacher.lower().replace(" ", ".") + "@unibo.it" for teacher in teachers}

# Set comprehensions are a concise way to create sets
numbers = {x for x in range(10) if x % 2 == 0}  # {0, 2, 4, 6, 8}

# Tuple comprehensions are a concise way to create tuples
numbers = tuple(x for x in range(10) if x % 2 == 0)  # (0, 2, 4, 6, 8)

# If you forget the parentheses, you will create a generator
numbers = (x for x in range(10) if x % 2 == 0)  # A generator is a lazy iterable
```

---

## Advanced Comprehensions

```python
# Nested comprehensions
chessboard = [(x, y) for x in range(8) for y in range(8)]

# If statements in comprehensions
black_squares = [(x, y) for x in range(8) for y in range(8) if (x + y) % 2 == 0]
```

---

# Control Structures

---

## If-Else Statements

```python
# You can use the if-else statement
traffic_light = "red"
if traffic_light == "red":
    action = "stop"
elif traffic_light == "yellow":
    action = "slow down"
else:
    action = "go"
    
# You can also use the ternary operator
action = "stop" if traffic_light == "red" else "go"
```

- From Python 3.10, you can use the `match` statement, which is similar to the `switch` statement in other languages.

```python
# You can use the match statement
traffic_light = "red"
action = match traffic_light:
    case "red":
        "stop"
    case "yellow":
        "slow down"
    case _:
        "go"
```

---

## Loops

```python
# You can use the for loop
numbers = [1, 2, 3, 4, 5]
for number in numbers:
    print(number)
    
# You can also use the range function
for number in range(5):
    print(number)
    
# You can also use the enumerate function
for index, number in enumerate(numbers):
    print(index, number)
    
# You can also use the zip function
names = ["Andrea", "Giovanni", "Matteo"]
ages = [59, 31, 29]
for name, age in zip(names, ages):
    print(name, age)

# You can use the while loop
x = 0
while x < 5:
    print(x)
    x += 1
```

---

# Object-Oriented Programming

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

---

## Magic Methods (1)

- Python has many _magic methods_ that you can implement or override.
- You can easily recognize them because they start and end with two underscores `__method__`.
- A good practice is to implement the `__repr__` method for debugging purposes.
- The `__str__` method is used when you want to print the object.
- The `__add__` method is used when you want to add two objects, and you can use the `+` operator.

```python
# Python has many magic methods that you can override

class Euro:
    def __init__(self, amount):
        self.amount = amount

    def __add__(self, other):
        return Euro(self.amount + other.amount)

    def __str__(self):
        return "€" + str(self.amount)
    
    def __repr__(self):
        return "Euro(" + str(self.amount) + ")"

# You can use the magic methods
euro1 = Euro(10)
euro2 = Euro(20)
euro3 = euro1 + euro2  # €30
print(euro3)  # €30
print(repr(euro3))  # Euro(30)
``` 

---

## Magic Methods (2)

- It is also good to implement the `__eq__` method (and `__hash__`) to compare two objects.
- Of course, there are many other magic methods that you can implement (see the [official documentation](https://docs.python.org/3/reference/datamodel.html#special-method-names)).

```python
# Here an example of the __eq__ with the Car class

class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model
        
    def __hash__(self):
        return hash((self.brand, self.model))

    def __eq__(self, other):
        return self.brand == other.brand and self.model == other.model

# You can use the magic methods
car1 = Car("Fiat", "500")
car2 = Car("Fiat", "500")
car3 = Car("Fiat", "Panda")
print(car1 == car2)  # True
print(car1 == car3)  # False
``` 

---

## Magic Methods (3)

- Data classes are a new feature in Python 3.7.
- They are used to create classes that are mostly used to store data.
- They automatically implement the `__init__`, `__repr__`, `__eq__`, and `__hash__` methods.

```python
# Here an example of a data class

class Number:
    @classmethod
    def parse(cls, s):
        return cls(s)
    
    def __repr__(self):
        return str(self.value)

class Integer(Number):
    def __init__(self, value):
        self.value = int(value)

class Float(Number):
    def __init__(self, value):
        self.value = float(value)


---

## Decorators

- _Decorators_ are a way to modify or extend the behavior of functions or methods.
- They are prefixed with the `@` symbol and are placed above the function definition.
- They can be used for logging, timing, caching, etc.

```python
# Here an example of a simple decorator

def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
```

---

## Decorators for getters and setters

- You can also use decorators for getters and setters.
- You can use the `@property` decorator for getters.
- You can use the `@property_name.setter` decorator for setters.

```python
# Here an example of a property decorator

class Person:
    def __init__(self, name):
        self._name = name

    @property
    def name(self):
        return self._name

    @name.setter
    def name(self, value):
        self._name = value
        
# You can use the property
person = Person("Andrea")
name = person.name  # "Andrea"
person.name = "Giovanni"
name = person.name  # "Giovanni"
```

---

## Decorators with Arguments

- You can also define decorators with arguments.
- You need to define a function that returns the decorator.

```python
# Here an example of a decorator with arguments

def my_decorator_with_args(number):
    def decorator(func):
        def wrapper():
            print("Something is happening before the function is called.")
            func()
            print("Something is happening after the function is called.")
            print("The number is:", number)
        return wrapper
    return decorator

@my_decorator_with_args(42)
def say_hello():
    print("Hello!")

say_hello()
```

---

## Static Methods and Class Methods

- You can define _static methods_ with the `@staticmethod` decorator. Static methods do not have access to the class or instance.
- You can define _class methods_ with the `@classmethod` decorator. Class methods have access to the class.

```python
# Here an example of static and class methods

class Math:
    @staticmethod
    def add(x, y):
        return x + y
    
    @staticmethod
    def multiply(x, y):
        return x * y
    
class Number:
    @classmethod
    def parse(cls, s):
        return cls(s)
    
    def __repr__(self):
        return str(self.value)

class Integer(Number):
    def __init__(self, value):
        self.value = int(value)

class Float(Number):
    def __init__(self, value):
        self.value = float(value)
    
sum = Math.add(5, 2)
product = Math.multiply(5, 2)

integer = Integer.parse("5")
float = Float.parse("5.5")
```

---

## Multiple Inheritance

- Python supports multiple inheritance.
- You can define a class that inherits from multiple classes.
- You can use the `super()` function to call the methods of the parent classes.

```python 
# Here an example of multiple inheritance

class Rectangle:
    def __init__(self, length, width, **kwargs):
        self.length = length
        self.width = width
        super().__init__(**kwargs)

    def area(self):
        return self.length * self.width

    def perimeter(self):
        return 2 * self.length + 2 * self.width

class Square(Rectangle):
    def __init__(self, length, **kwargs):
        super().__init__(length=length, width=length, **kwargs)

class Triangle:
    def __init__(self, base, height, **kwargs):
        self.base = base
        self.height = height
        super().__init__(**kwargs)

    def tri_area(self):
        return 0.5 * self.base * self.height

class RightPyramid(Square, Triangle):
    def __init__(self, base, slant_height, **kwargs):
        self.base = base
        self.slant_height = slant_height
        kwargs["height"] = slant_height
        kwargs["length"] = base
        super().__init__(base=base, **kwargs)

    def area(self):
        base_area = super().area()
        perimeter = super().perimeter()
        return 0.5 * perimeter * self.slant_height + base_area

    def area_2(self):
        base_area = super().area()
        triangle_area = super().tri_area()
        return triangle_area * 4 + base_area
```


# Final Notes

---

## Exceptions

- _Exceptions_ are a way to handle errors in Python.
- You can use the `try`, `except`, `else`, and `finally` statements.
- You can also raise exceptions with the `raise` statement.

```python
# Here an example of an exception
try:
    raise Exception("Something went wrong!")  # use the keyword raise to raise an exception
except Exception as e:
    print(e)  # "Something went wrong!"
else:
    print("Everything is fine!")
finally:
    print("This is always executed!")
```

---

## Cyclic Imports

- Python does not allow cyclic imports.
- So, organize your code in a way that avoids cyclic imports.

```python
# Here an example of cyclic imports
# file1.py
from file2 import function2
def function1():
    return function2()
    
# file2.py
from file1 import function1
def function2():
    return function1()
```

---

## Recursion Limit

- Python has a default recursion limit of 1000.

```python
# Here an example of recursion that will raise an exception
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

fibonacci(10)  # This will work
fibonacci(1000)  # This will raise a RecursionError
```

- You can change the recursion limit with the `sys` module.

```python
# Here an example of recursion limit
import sys
sys.setrecursionlimit(10000)

fibonacci(1000)  # This will work but it will take a lot of time
# Do not run it, or just halt the execution
```

---

# Introduction to the Python programming language

{{% import path="reusable/footer.md" %}}