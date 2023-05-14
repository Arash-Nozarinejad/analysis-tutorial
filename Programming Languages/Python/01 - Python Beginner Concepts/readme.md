# Python Beginner to Intermediate Tutorial

## Introduction

In this Python tutorial we will start at the most basic level and concepts and move on to intermediate concepts and get you ready for the most advanced and mastery level concepts.

- [Python Beginner to Intermediate Tutorial](#python-beginner-to-intermediate-tutorial)
  - [Introduction](#introduction)
  - [Python Basic Concepts](#python-basic-concepts)
    - [Running a Python Script](#running-a-python-script)
    - [Syntax and structure](#syntax-and-structure)
    - [Variables and data types](#variables-and-data-types)
    - [Basic Operators](#basic-operators)
    - [Conditional statements (if, elif, else)](#conditional-statements-if-elif-else)
    - [Loops (for, while)](#loops-for-while)
    - [Functions](#functions)
    - [Basic error handling (try, except, finally)](#basic-error-handling-try-except-finally)
    - [Importing and using libraries](#importing-and-using-libraries)
  - [Python Intermediate Concepts](#python-intermediate-concepts)
    - [Data Structures](#data-structures)
      - [Lists](#lists)
      - [Tuples](#tuples)
      - [Sets](#sets)
      - [Dictionaries](#dictionaries)
    - [File I/O](#file-io)
      - [File Modes](#file-modes)
      - [CSV and JSON Parsing](#csv-and-json-parsing)
      - [Pickling](#pickling)
    - [Modules and packages](#modules-and-packages)
      - [Creating and importing modules](#creating-and-importing-modules)
      - [Creating and using packages](#creating-and-using-packages)
      - [Standard library modules (os, sys, shutil, datetime, etc)](#standard-library-modules-os-sys-shutil-datetime-etc)
  - [END](#end)
  - [Farewell](#farewell)

## Python Basic Concepts

### Running a Python Script

Python scripts have a .py extension. You can create a new file in a text editor, write your Python code, and save the .py extension. To run the script, open a terminal or command prompt, navigate to the directory where the script is saved and enter __python script_name.py__.

### Syntax and structure

Python uses indentation to define blocks of code. It uses a colon ( : ) at the end of a line to start a new block. For example:

``` python
if condition:
    # Indented code block
    statement1
    statement2
else:
    # Another indented code block
    statement3
    statement4
```

### Variables and data types

In Python, variables are used to store values. They are created by assigning a value to a name. Python is dynamically typed, so you don't need to declare the variable type explicitly. Common data types include integers, floats, strings, booleans, and lists.

``` python
# Variable assignment
x = 10
name = 'john'
is_valid = True

# Data types
a = 10 # Integer
b - 3.14 # Float
c = "hello" # String
d = True # Boolean
e = [1, 2, 3, 4] # List 
```

### Basic Operators

Python provides various operators for performing mathematical, logical, and comparison operators. Examples include arithmetic operators (+, -, *, /), assignment operators (=, +=, -=), comparison operators (==, !=, <, >), and logical operators (and, or, not)

### Conditional statements (if, elif, else)

Conditional statements allow you to execute different blocks of code based on certain conditions. the _if_ statement checks a condition and executes the indented block if it is True. The _elif_ and _else_ statements provide alternative conditions to be evaluated.

``` python
if condition1:
    # Code block executed if condition1 is true
    statement1
elif condition2:
    # Code block executed if condition1 is false and condition2 is true
    statement2
else:
    # Code block executed if both condition1 and condition2 are false
    statement3
```

### Loops (for, while)

Loops are used to repeat a block of code multiple times. The _for_ loop iterates over a sequence (such as a list of string) or a range of numbers. The _while_ loop repeats as long as a condition is true.

``` python
# for loop
for item in sequence:
    # code block executed for each item in the sequence
    statement

# while loop
while condition:
    # Code block executed as long as the condition is trie
    statement
```

### Functions

Functions are blocks of reusable code that perform a specific task. They help organize code and promote code reusability. Functions can accept arguments, perform computations, and return values.

``` python
def function_name(parameter1, parameter2):
    # code block of the function
    statement1
    statement2
    return result

# function call

result = function_name(arg1, arg2)
```

### Basic error handling (try, except, finally)

Error handling allows you to gracefully handle and recover from runtime errors. The _try_ block contains the code that might raise an exception. The _except_ block catches and handles the exception if it occurs. The finally block is optional and is executed regardless of whether an exception occurred or not.

### Importing and using libraries

Python provides a vast ecosystem of libraries and module that extend its functionality. You can import these libraries into your code using the _import_ statement. Once imported, you can use the functions, classes and variables provided by the library.

``` python
import library_name

# Using library functions
library_name.function_name(arguments)
```

## Python Intermediate Concepts

### Data Structures

#### Lists

Lists are ordered collections of elements. They can store elements of different types and are mutable, allowing modification of elements.

``` python
# List initialization
my_list = [1, 2, 3, 'hello', True]

# Accessing elements
print(my_list[0]) # output: 1

# Modifying lists
my_list[0] = 10
print(my_list[0]) # output: 10
```

#### Tuples

Tuples are similar to lists but are immutable, meaning their elements cannot be modified once created. They are often used to group related values together.

``` python
# Tuple initialization
my_tuple = (1, 2, 3, 'hello', True)

# Accessing elements
print(my_tuple[0]) # output: 1
```

#### Sets

Sets unordered collection of unique elements. They do not allow duplicate values and provide operations like union, intersection, and different.

``` python
# Set initialization
my_set = {1, 2, 3, 4}

# Basic set operations
my_set.add(5)
my_set.remove(3)
union_set = my.set.union({6, 7})
intersection_set = my_set.intersection({2, 4})
difference_set = my_set.difference({1, 2, 5})
```

#### Dictionaries

Dictionaries store data as key-value pairs. Each value is associated with a unique key, allowing efficient retrieval and modification of value.

``` python
# Dictionary initialization
my_dict = {'name': 'john', 'age': 25, 'city': 'new york'}

# Accessing elements
print(my_dict['name']) # output: john

# Modifying dictionaries
my_dict['age'] = 26
my_dict['country'] = 'USA'
del my_dict['city']
```

### File I/O

Python provides functions for reading and writing data from/to files. You can use the _open()_ function to open a file and specify the mode ('r' for reading, 'w' for writing, and 'a' for appending) along with the file name.

``` python
# Reading a file
with open('file.txt' , 'r') as file:
    content = file.read()
    print(content)

# Writing to a file
with open('file.txt', 'w') as file:
    file.write('hello world')
```

#### File Modes

File modes determine the file's behavior when opened. Common modes include:

- r: Read mode (default)
- w: Write mode (overwrite existing file or create a new file)
- a: Append mode (append to an existing file or create a new file)
- x: Exclusive creation mode (create a new file, but raise an error if it already exists)

#### CSV and JSON Parsing

Python provides libraries for parsing and manipulating CSV and JSON data. The csv module allows reading from and writing to CSV files, while the json module enables JSON serialization and deserialization.

``` python
import csv
import json

# CSV parsing
with open("data.csv", "r") as file:
    csv_reader = csv.reader(file)
for row in csv_reader:
print(row)

# JSON parsing
with open("data.json", "r") as file:
    json_data = json.load(file)
print(json_data)

```

#### Pickling

Pickling is a way to serialize Python objects into a binary format, allowing them to be stored or transmitted. The _pickle_ module provides functions for pickling and unpickling objects.

``` python
import pickle

# Pickling an object
data = {"name": "John", "age": 25}
with open("data.pkl", "wb") as file:
    pickle.dump(data, file)

# Unpickling an object
with open("data.pkl", "rb") as file:
    data = pickle.load(file)
    print(data)
```

### Modules and packages

#### Creating and importing modules

A module is a file containing Python definitions and statements. You can create your own modules by creating a .py file and writing your code in it. To import a module, use the import statement followed by the module name.

``` python
# module.py
def say_hello():
    print("Hello!")

# main.py
import module

module.say_hello()  # Output: Hello!
```

#### Creating and using packages

A package is a way to organize related modules into a directory hierarchy. It typically includes an __init__.py file that initializes the package. To import modules from a package, use the import statement followed by the package name and module name.

``` python
# package/
#     __init__.py
#     module1.py
#     module2.py

# module1.py
def func1():
    print("Function 1")

# module2.py
def func2():
    print("Function 2")

# main.py
from package import module1, module2

module1.func1()  # Output: Function 1
module2.func2()  # Output: Function 2
```

#### Standard library modules (os, sys, shutil, datetime, etc)

Standard library modules (os, sys, shutil, datetime, etc.):
Python provides a comprehensive standard library with many useful modules for various purposes. Some commonly used standard library modules include:

- os: Operating system interfaces
- sys: System-specific parameters and functions
- shutil: File and directory operations
- datetime: Date and time manipulation
- math: Mathematical functions

``` python
import os
import datetime

print(os.getcwd())  # Output: Current working directory
print(datetime.datetime.now())  # Output: Current date and time
```

## END

In this tutorial we learned all the basic and most important starting concepts of Python. You are now ready for the advanced and mastery level Python concepts.

## Farewell

Thank you for reading this Github article on Advanced Python Concepts. Creating this tutorial project was very fun and I hope you enjoyed reading it as much as I enjoyed creating it.

You can visit our website for more tutorials, guides, case studies, and more by [clicking here](https://www.analysistutorial.com/).

Farewell.
