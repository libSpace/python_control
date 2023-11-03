# Python-Control-Flow

## Table of Contents

- [Control Flow](#Control-Flow)
- [Python Functions](#Python-Functions)
- [Introduction to modules](#Introduction-to-Modules)
- [Regular Expressions](#Regular-Expressions)


## Control-Flow
Conditional Statements (if, elif, else):

The if statement is used to execute a block of code only if a specified condition is true.
elif stands for "else if" and is used to specify multiple alternative conditions to be checked if the previous conditions are false.
else is used to specify the block of code that should be executed if none of the conditions are true.
Example:

python
Copy code
if condition1:
    # code block if condition1 is true
elif condition2:
    # code block if condition2 is true
else:
    # code block if no conditions are true
Loops:

For Loop:

Used for iterating over a sequence (like a list, tuple, or string) or other iterable objects.
range() function is often used in conjunction with for loops to generate a sequence of numbers.
Example:

python
Copy code
for i in range(5):
    print(i)
While Loop:

Continues executing a block of code as long as a specified condition is true.
Example:

python
Copy code
while condition:
    # code block
Break and Continue:

break statement is used to exit a loop prematurely based on a certain condition.
continue statement is used to skip the rest of the loop and start the next iteration.
Example:

python
Copy code
for i in range(10):
    if i == 5:
        break
    print(i)
Pass Statement:

Used when a statement is syntactically required but you don't want to execute any code.
Example:

python
Copy code
if condition:
    pass
else:
    # code block
Try-Except Blocks:

Used for handling exceptions (errors) in Python.
try block contains the code that might raise an exception, and except block contains the code to handle that exception.
Example:

python
Copy code
try:
    # code that might raise an exception
except ExceptionType as e:
    # code to handle the exception
Else with Loops:

You can use an else block after a loop. The code in the else block will execute if the loop completes without encountering a break statement.
Example:

python
Copy code
for i in range(5):
    print(i)
else:
    print("Loop completed without break")
Nested Loops and Conditional Statements:

You can have loops and conditional statements inside other loops or conditional statements.
Example:

python
Copy code
for i in range(3):
    for j in range(2):
        print(i, j)

## Python-Functions

Defining a Function:

You can define a function using the def keyword, followed by the function name, a pair of parentheses (), and a colon :.
Example:

python
Copy code
def greet():
    print("Hello!")
Function Parameters (Arguments):

Functions can take zero or more parameters (inputs) enclosed in the parentheses. These parameters are used as variables within the function.
Example:

python
Copy code
def greet(name):
    print(f"Hello, {name}!")
Function Call:

To execute a function, you need to "call" it by using its name followed by a pair of parentheses.
Example:

python
Copy code
greet("Alice")
Return Statement:

Functions can return a value using the return statement. This allows you to pass information back to the code that called the function.
Example:

python
Copy code
def add(a, b):
    return a + b
Default Arguments:

You can provide default values for function parameters. If a value is not provided when calling the function, the default value will be used.
Example:

python
Copy code
def greet(name="User"):
    print(f"Hello, {name}!")
Keyword Arguments:

When calling a function, you can specify the arguments by using the parameter names. This allows you to pass arguments in any order.
Example:

python
Copy code
greet(name="Bob")
Variable-Length Argument Lists:

You can use *args and **kwargs to pass a variable number of arguments to a function. *args collects extra positional arguments into a tuple, and **kwargs collects extra keyword arguments into a dictionary.
Example:

python
Copy code
def my_function(*args, **kwargs):
    # code that uses args and kwargs
Scope of Variables:

Variables defined inside a function have local scope and are not accessible outside the function. Variables defined outside the function have global scope.
Lambda Functions (Anonymous Functions):

Lambda functions are small, anonymous functions defined using the lambda keyword. They can take any number of arguments, but can only have one expression.
Example:

python
Copy code
add = lambda x, y: x + y
Recursion:

A function can call itself. This is known as recursion. It's a powerful technique, but it should be used with caution to avoid infinite loops.
Example:

python
Copy code
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)
Docstrings:
You can provide documentation for your functions using docstrings (triple-quoted strings at the beginning of a function).
Example:

python
Copy code
def my_function():
    """
    This is the docstring. It provides information about the function.
    """
    # function code here


## Introduction-to-Modules
Creating a Module:

To create a module, you simply save a Python file with a .py extension. For example, if you create a file named my_module.py, it becomes a module named my_module.
Example content of my_module.py:

python
Copy code
def greet(name):
    print(f"Hello, {name}!")

def add(a, b):
    return a + b
Using a Module:

To use functions or variables defined in a module, you need to import it into your Python script or another module.
Example:

python
Copy code
import my_module

my_module.greet("Alice")
result = my_module.add(2, 3)
You can also import specific functions or variables from a module:

python
Copy code
from my_module import greet, add

greet("Bob")
result = add(5, 7)
Namespace:

When you import a module, you create a namespace for its contents. This means you need to prefix function names with the module name (e.g., my_module.greet("Alice")) or use the from ... import ... syntax to bring specific names into the current namespace.
Module Search Path:

When you try to import a module, Python searches for it in certain directories. These directories are defined in the sys.path list. The current directory and the standard library directories are included in this list by default.
Example:

python
Copy code
import sys
print(sys.path)
Packages:

A package is a way of organizing related modules into a single directory hierarchy. A package is a directory that contains an __init__.py file, which can be empty or can contain initialization code for the package.
Example:

markdown
Copy code
my_package/
├── __init__.py
├── module1.py
└── module2.py
To use modules within a package, you can import them using dot notation, like my_package.module1.

Standard Library:

Python comes with a rich set of modules and packages as part of its standard library. These modules provide a wide range of functionalities, from working with files and networking to mathematical operations and more.
Third-Party Modules:

In addition to the standard library, there is a vast ecosystem of third-party modules available through the Python Package Index (PyPI). These modules cover a wide range of domains and can be installed using package managers like pip.
Example:

bash
Copy code
pip install requests
python
Copy code
import requests
response = requests.get("https://www.example.com")
Special Variables in a Module:

A module can have a special variable called __name__. When a module is imported, __name__ is set to the module's name. If the module is run directly as a script, __name__ is set to "__main__". This can be useful for including code that should only run when the module is executed directly.
Example:

python
Copy code
if __name__ == "__main__":
    # Code to execute if the module is run directly

## Regular-Expressions

Importing the re Module:

The re module in Python provides functions and methods to work with regular expressions. You need to import this module before using regular expressions in your code.
Example:

python
Copy code
import re
Basic Patterns:

Regular expressions are composed of characters that represent patterns to match in a string. For example, a will match the character 'a' in a string.
Example:

python
Copy code
pattern = r"a"
result = re.search(pattern, "apple")
Metacharacters:

Metacharacters are special characters that have a special meaning in regular expressions. Some commonly used metacharacters include . (matches any character), ^ (matches the start of a string), $ (matches the end of a string), * (matches 0 or more occurrences), + (matches 1 or more occurrences), ? (matches 0 or 1 occurrence), and more.
Example:

python
Copy code
pattern = r"b..t"
result = re.search(pattern, "beet")
Character Classes:

Character classes are enclosed in square brackets [] and are used to match any one of the characters inside the brackets. For example, [aeiou] will match any vowel.
Example:

python
Copy code
pattern = r"[aeiou]"
result = re.search(pattern, "apple")
Quantifiers:

Quantifiers specify the number of occurrences a pattern should match. For example, {n} matches exactly n occurrences, {n,} matches n or more occurrences, and {n,m} matches between n and m occurrences.
Example:

python
Copy code
pattern = r"\d{3}"
result = re.search(pattern, "12345")
Special Sequences:

Special sequences begin with a backslash \ and have a special meaning. Some examples include \d (matches any digit), \w (matches any word character), \s (matches any whitespace character), and more.
Example:

python
Copy code
pattern = r"\d\s\w"
result = re.search(pattern, "1 a")
Grouping and Alternation:

Parentheses () are used to group patterns together. The pipe | is used for alternation, allowing you to match either one pattern or another.
Example:

python
Copy code
pattern = r"(apple|banana)"
result = re.search(pattern, "banana")
Anchors:

Anchors are used to specify the position in a string where a match should occur. ^ matches the start of a string, and $ matches the end of a string.
Example:

python
Copy code
pattern = r"^hello"
result = re.search(pattern, "hello world")
Search and Match Functions:

The re.search() function searches for a pattern in a string and returns a match object if found. The re.match() function only matches at the beginning of a string.
Example:

python
Copy code
result = re.search(r"world", "Hello, world!")
Substitution:

The re.sub() function is used to substitute occurrences of a pattern in a string with another string.
Example:

python
Copy code
result = re.sub(r"apple", "orange", "I have an apple")
