# Advanced Python Tutorial

Hello and welcome to another Tutorial. This time on Advanced Python concepts. In this tutorial we will cover the following topics:

- [Advanced Python Tutorial](#advanced-python-tutorial)
  - [Object Oriented Programming](#object-oriented-programming)
    - [Classes, Instances and More](#classes-instances-and-more)
    - [How to Define a Class](#how-to-define-a-class)
    - [How to Create an Instance](#how-to-create-an-instance)
    - [The __init__() Function](#the-init-function)
    - [How to Access Object Attributes](#how-to-access-object-attributes)
      - [The self Parameter](#the-self-parameter)
    - [How to Modify Object Attributes](#how-to-modify-object-attributes)
    - [The __str__() Function](#the-str-function)
    - [Object Methods](#object-methods)
    - [Encapsulation](#encapsulation)
      - [Getters and Setters](#getters-and-setters)
    - [Inheritance](#inheritance)
      - [Multi-Level inheritance](#multi-level-inheritance)
      - [Multiple inheritance](#multiple-inheritance)
      - [The issubclass(sub, sup) method](#the-issubclasssub-sup-method)
      - [The isinstance(obj, class) method](#the-isinstanceobj-class-method)
      - [Method overriding](#method-overriding)
      - [Abstraction](#abstraction)
  - [List Comprehensions](#list-comprehensions)
    - [Using _for_ Loops](#using-for-loops)
    - [Using _map()_ Objects](#using-map-objects)
    - [Using List Comprehensions](#using-list-comprehensions)
      - [Using Conditional Logic](#using-conditional-logic)
  - [Lambda Functions](#lambda-functions)
    - [Syntax](#syntax)
  - [Map, Filter, and Reduce Functions](#map-filter-and-reduce-functions)
    - [Map](#map)
    - [Filter](#filter)
    - [Reduce](#reduce)
  - [Decorators](#decorators)
    - [Fist-Class Objects](#fist-class-objects)
    - [Inner Functions](#inner-functions)
    - [Returning Functions From Functions](#returning-functions-from-functions)
    - [Simple Decorator](#simple-decorator)
    - [The "pie" syntax](#the-pie-syntax)
    - [Decorating Function With Arguments](#decorating-function-with-arguments)
    - [Returning Values From Decorated Functions](#returning-values-from-decorated-functions)
    - [Function and Wrapper Identity](#function-and-wrapper-identity)
  - [Context Managers and the 'with' Statement](#context-managers-and-the-with-statement)
  - [Iterators and Generators](#iterators-and-generators)
    - [Iterators](#iterators)
      - [Custom Iterators](#custom-iterators)
    - [Generator](#generator)
      - [Creating Custom Generators](#creating-custom-generators)
  - [Regular Expressions](#regular-expressions)
    - [RegEx Functions](#regex-functions)
    - [Meta-Characters](#meta-characters)
  - [Multi-Threading and Multi-Processing](#multi-threading-and-multi-processing)
    - [Concurrency and Parallelism](#concurrency-and-parallelism)
    - [Multithreading in Python](#multithreading-in-python)
    - [Multiprocessing in Python](#multiprocessing-in-python)
      - [Process](#process)
      - [Queue Class](#queue-class)
      - [Lock Class](#lock-class)
      - [MultiProcessing Example](#multiprocessing-example)
      - [Python multiprocessing Pool](#python-multiprocessing-pool)
  - [Data Access and SQL](#data-access-and-sql)
  - [Web Scraping and APIs](#web-scraping-and-apis)
    - [Web Scraping](#web-scraping)
    - [APIs](#apis)
  - [Numpy, Pandas, and Matplotlib](#numpy-pandas-and-matplotlib)
    - [Numpy](#numpy)
      - [Numpy Arrays](#numpy-arrays)
        - [Creating Arrays](#creating-arrays)
        - [Aray attributes](#aray-attributes)
        - [Array indexing and slicing](#array-indexing-and-slicing)
      - [Array operations](#array-operations)
        - [Element-wise operations](#element-wise-operations)
        - [Matrix Operations](#matrix-operations)
      - [Broadcasting](#broadcasting)
      - [Universal functions (Ufuncts)](#universal-functions-ufuncts)
      - [Random numbers](#random-numbers)
      - [Array manipulation](#array-manipulation)
        - [Reshaping](#reshaping)
        - [Concatenation](#concatenation)
        - [Splitting](#splitting)
      - [Masking and boolean operations](#masking-and-boolean-operations)
      - [Advanced indexing and slicing](#advanced-indexing-and-slicing)
        - [Integer indexing](#integer-indexing)
        - [Slicing with steps](#slicing-with-steps)
    - [Pandas](#pandas)
      - [Pandas Data Structures](#pandas-data-structures)
        - [Series](#series)
        - [DataFrame](#dataframe)
      - [Input/Output](#inputoutput)
        - [Reading CSV](#reading-csv)
        - [Writing CSV](#writing-csv)
      - [Data Inspection and Selection](#data-inspection-and-selection)
        - [Inspecting Data](#inspecting-data)
        - [Selecting Data](#selecting-data)
      - [Data Manipulation](#data-manipulation)
        - [Renaming Columns](#renaming-columns)
        - [Adding Columns](#adding-columns)
        - [Removing Columns](#removing-columns)
        - [Sorting](#sorting)
      - [Missing Data Handling](#missing-data-handling)
        - [Drop Missing Data](#drop-missing-data)
        - [Fill Missing Data](#fill-missing-data)
      - [Grouping and Aggregation](#grouping-and-aggregation)
        - [Grouping](#grouping)
        - [Aggregation](#aggregation)
      - [Merging and Concatenation](#merging-and-concatenation)
        - [Merging](#merging)
        - [DF Concatenation](#df-concatenation)
      - [Time Series Functionality](#time-series-functionality)
        - [Convert to datetime object](#convert-to-datetime-object)
        - [Set index to datetime](#set-index-to-datetime)
        - [Resampling](#resampling)
        - [Rolling Window](#rolling-window)
        - [Shifting Data](#shifting-data)
        - [Time Zone Handling](#time-zone-handling)
      - [Apply and Map Functions](#apply-and-map-functions)
        - [Apply function to each element in a DataFrame or Series](#apply-function-to-each-element-in-a-dataframe-or-series)
        - [Apply function element-wise using the 'map' function](#apply-function-element-wise-using-the-map-function)
        - [Apply a function to each column or row using __apply__](#apply-a-function-to-each-column-or-row-using-apply)
    - [Matplotlib](#matplotlib)
      - [Basic Plots](#basic-plots)
        - [Line Plot](#line-plot)
        - [Scatter Plot](#scatter-plot)
        - [Bar Plot](#bar-plot)
        - [Histogram](#histogram)
      - [Customizing Plots](#customizing-plots)
        - [Adding title and labels](#adding-title-and-labels)
        - [Changing line style and adding markers](#changing-line-style-and-adding-markers)
        - [Adding Legend](#adding-legend)
        - [Setting axis limits](#setting-axis-limits)
      - [Multiple Plots](#multiple-plots)
        - [Subplots](#subplots)
        - [Overlaying plots](#overlaying-plots)
      - [Advanced Plots](#advanced-plots)
        - [3D plots](#3d-plots)
        - [Contour plots](#contour-plots)
        - [Heatmaps](#heatmaps)
        - [Box plots](#box-plots)
        - [Violin plots](#violin-plots)
      - [Customizing plot styles and colors](#customizing-plot-styles-and-colors)
        - [Available plot styles](#available-plot-styles)
        - [Using plot styles](#using-plot-styles)
        - [Customizing colormaps](#customizing-colormaps)
      - [Saving plots](#saving-plots)
  - [Logging](#logging)
    - [Importing the logging module](#importing-the-logging-module)
    - [Basic Loggins](#basic-loggins)
      - [Default logging configuration (root logger)](#default-logging-configuration-root-logger)
      - [Log messages with different severity levels](#log-messages-with-different-severity-levels)
    - [Configuration Loggers, Handlers, and Formatters](#configuration-loggers-handlers-and-formatters)
      - [Create a logger](#create-a-logger)
      - [Create a file handler](#create-a-file-handler)
      - [Create a stream formatter](#create-a-stream-formatter)
      - [Create a formatter](#create-a-formatter)
      - [Add formatter to handlers](#add-formatter-to-handlers)
      - [Add handlers to logger](#add-handlers-to-logger)
    - [Using the configured logger](#using-the-configured-logger)
    - [Logging exceptions](#logging-exceptions)
      - [Log exceptions with traceback](#log-exceptions-with-traceback)
    - [Logging with custom context information](#logging-with-custom-context-information)
      - [Using LogRecord attributes](#using-logrecord-attributes)
      - [Add custom information to the log records](#add-custom-information-to-the-log-records)
    - [Configuring logging with a configuration file or dictionary](#configuring-logging-with-a-configuration-file-or-dictionary)
      - [Configuration file (INI-style)](#configuration-file-ini-style)
      - [Load configuration from a file](#load-configuration-from-a-file)
      - [Dictionary-based configuration](#dictionary-based-configuration)
    - [Using log filters](#using-log-filters)
      - [Create a custom log filter](#create-a-custom-log-filter)
      - [Add filter to a handler](#add-filter-to-a-handler)
  - [Farewell](#farewell)

## Object Oriented Programming

Let us start with the most important subject in programming: Object-oriented programming

Object-oriented programming is used for modeling real-world things such as cars or people and relations such as the relations between companies and employees.

Before we get to examples we have to learn a few other concepts in object-oriented programming. Starting with:

### Classes, Instances and More

Classes the main tool in object-oriented programming. A class is a blueprint for how something should be defined. Classes don't contain data.

An instance is an object that is built from a class and contains real data.

For example, let's say we have a "dog" class that defines the behaviors of dogs. The instance of this dog class would be an actual dog with a name.

Classes also define functions which are called methods. Methods identify the behaviors and actions that an instance (object) can perform.

### How to Define a Class

All class definitions start with the _class_ keyword and followed the class name and a colon. Any code indented below the class definition is considered part of the class's body.

Here is an example:

``` Python
class Dog:
  pass
```

Class names follow the _PascalCase_ convention: Start with a capital letter and capitalize every different word.

### How to Create an Instance

To create an instance of of a class we simply assign the class name followed by parenthesis to a variable. For example:

``` Python
class Dog:
  pass

rex = Dog()

```

Here, we have created the class object _rex_ of the _Dog_ class.

### The __init__() Function

The above classes are not very useful. To unlock the power of classes we have to learn about the *\__init__()* function.

All classes have a function called _init()_ built into them. The _init()_ function is always executed when the class is being initiated. Meaning an instance of the class is created. Use the _init()_ function to assign values to properties of the class object, or perform necessary operations when an object is being created.

For example:

``` Python
class Dog:
  def __init__(self, name, age):
    self.name = name
    self.age = age

rex = Dog('rex', 10)
```

Here we have created a _Dog_ class that asks the user to provide a name and an age for the class instance (object). Then, we have created a class object called _rex_ and gave it a name and an age.

### How to Access Object Attributes

In order to see and access object attributes we can simply write the object name, a dot followed by the attribute name. For example:

``` Python
class Dog:
  def __init__(self, name, age):
    self.name = name
    self.age = age

rex = Dog('rex', 10)

print(rex.name)
print(rex.age)
```

Here, after creating a class and an object of the class we have printed the object's two attributes, which results:

```console
>>> rex
>>> 10
```

#### The self Parameter

The ==self== parameter is a reference to the current instance of the class, and is used to access variables that belongs to the class.

### How to Modify Object Attributes

To modify the value of object attributes you can simply assign a new value:

``` Python
class Dog:
  def __init__(self, name, age):
    self.name = name
    self.age = age

rex = Dog('rex', 10)

rex.age = 11

print(rex.name)
print(rex.age)
```

```console
>>> rex
>>> 11
```

### The __str__() Function

If you create a class object and print it, the string representation of the object is returned. For example:

``` Python
class Dog:
  def __init__(self, name, age):
    self.name = name
    self.age = age

rex = Dog('rex', 10)

print(rex)
```

```console
>>> <__main__.Dog object at 0x15039e602100>
```

This is not very useful. To help us control what should be returned we can use \___str___() function.

``` Python
class Dog:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def __str__(self):
    return f'{self.name} is {self.age} years old!'

rex = Dog('rex', 10)

print(rex)
```

```console
>>> rex is 10 years old!
```

### Object Methods

Objects can also contain methods. Let us create create a class with a method:

``` Python
class Dog:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def __str__(self):
    return f'{self.name} is {self.age} years old!'

  def take_nap():
    print(f'{self.name} is taking a nap.')

rex = Dog('rex', 10)

rex.take_nap()
```

```console
>>> rex is taking a nap.
```

### Encapsulation

Encapsulation means hiding unnecessary details to make it easier to manage the program structure. One way of achieving this is with what are called _Access Modifiers_. In Python there are no public, private, or protected modifier keywords like other programming languages. Here, we use __single underscore__ or __double underscore__.

Access modifiers limit access to the variables and methods of a class. There are three types of access modifiers:

- Public Member: Accessible anywhere from outside of the class.
- Private Member: Accessible within the class.
- Protected Member: Accessible within the class and its sub-classes

``` Python
class Dog:
  def __init__(self, name, age, color):
    self.name = name      # -----> public member
    self._age = age       # -----> protected member
    self.__color = color  # -----> private member
```

If we try to access a private attribute of an object we'll get an error:

``` Python
class Dog:
  def __init__(self, name, age, color):
    self.name = name
    self._age = age
    self.__color = color

rex = Dog('rex', 10, 'golden')
print(rex.color)
```

```console
>>> AttributeError: 'Dog' object has no attribute 'color'
```

The same access modifiers can be applied to methods as well.

We can directly access private and protected variables from outside of a class through name mangling. The name mangling is created on an identifier by adding two leading underscores and one trailing underscore, like this _classname__dataMember, where classname is the current class, and data member is the private variable name.

for Example:

``` Python
class Dog:
  def __init__(self, name, age, color):
    self.name = name
    self._age = age
    self.__color = color

rex = Dog('rex', 10, 'golden')
print(rex._Dog__color)
```

```console
>>> golden
```

#### Getters and Setters

To implement proper encapsulation in Python, we need to use setters and getters. The primary purpose of using getters and setters in object-oriented programs is to ensure data encapsulation. Use the getter method to access data members and the setter methods to modify the data members.

In Python, private variables are not hidden fields like in other programming languages. The getters and setters methods are often used when:

- When we want to avoid direct access to private variables
- To add validation logic for setting a value

``` Python
class Dog:
  def __init__(self, name, age, color):
    self.name = name
    self.age = age
    self.__color = color
  
  def get_color(self):
    return self.__color
  
  def set_color(self, color):
    self.__color = color

rex = Dog('rex', 10, 'golden')

print(rex.get_color())

rex.set_color('brown')

print(rex.get_color())

```

```console
>>> golden
>>> brown
```

### Inheritance

The two most important concepts in OOP (Object-Oriented Programming) are: Inheritance and Polymorphism.

Polymorphism is built into inheritance and simply means when an object takes multiple forms.

Inheritance allows us to create a general class or a base class and then extend it to more specialized classes.

For example, with inheritance you can use all the data fields and methods of a base class and add your own methods or data fields. This way you can organize your code better and you won't need to rewrite your code from scratch.

In OOP, when the class __X__ Extends the class __Y__, __Y__ is called the _super/parent/base_ class and __X__ is called the _subclass/child/derived_ class.

Although you have to remember, only non-private data fields and methods are accessible by child classes and private data fields and methods are accessible only inside the parent class.

For example:

``` python
class Animal:
  def speak(self):
    print('The animal is speaking')

class Ape(Animal):
  def roar(self):
    print('The ape is roaring')

coco = Ape()

coco.speak()
coco.roar()
```

``` console
>>> The animal is speaking
>>> The ape is roaring
```

#### Multi-Level inheritance

Multi-Level inheritance is possible in python like other object-oriented languages. Multi-level inheritance is archived when a derived class inherits another derived class. There is no limit on the number of levels up to which, the multi-level inheritance is archived in python.

``` python
class Animal:
  def speak(self):
    print('The animal is speaking')

class Ape(Animal):
  def roar(self):
    print('The ape is roaring')

class Gorilla(Ape):
  def swing(self):
    print('The gorilla is swinging')

coco = Gorilla()

coco.speak()
coco.roar()
coco.swing()
```

``` console
>>> The animal is speaking
>>> The ape is roaring
>>> The gorilla is swinging
```

#### Multiple inheritance

Python classes also can inherit from multiple classes.

``` python
class Albino(self):
  def condition(self):
    print('This animal has albinoism')

class Animal:
  def speak(self):
    print('The animal is speaking')

class Ape(Animal):
  def roar(self):
    print('The ape is roaring')

class Gorilla(Ape, Albino):
  def swing(self):
    print('The gorilla is swinging')

coco = Gorilla()

coco.speak()
coco.roar()
coco.swing()
coco.condition
```

``` console
>>> The animal is speaking
>>> The ape is roaring
>>> The gorilla is swinging
>>> This animal has albinoism
```

#### The issubclass(sub, sup) method

The issubclass(sub, sup) method is used to check the relations between two classes. It either returns True or False depending if the first class is the subclass of the second class.

For Example:

``` python
class Albino(self):
  def condition(self):
    print('This animal has albinoism')

class Animal:
  def speak(self):
    print('The animal is speaking')

class Ape(Animal):
  def roar(self):
    print('The ape is roaring')

print(issubclass(Ape, Animal))
print(issubclass(Animal, Albino))
```

``` console
>>> TTrue
>>> False
```

#### The isinstance(obj, class) method

The isinstance() method is used to check the relation between an object and a class. It either returns True or False if the first parameter, the object is an instance of the second parameter, the class.

``` python
class Animal:
  def speak(self):
    print('The animal is speaking')

coco = Animal()

print (isinstance(coco, Animal))
```

``` console
>>> True
```

#### Method overriding

Child classes can override parents' classes when inheriting the parent class. For example:

``` python
class Animal:
  def speak(self):
    print('The animal is speaking')

class Ape(Animal):
  def speak(self):
    print('The ape is speaking')

coco = Ape()

coco.speak()
```

``` console
>>> The ape is speaking
```

#### Abstraction

In Python, an abstraction is used to hide the irrelevant data/class in order to reduce the complexity. It also enhances the application efficiency.

A class that consists of one or more abstract method is called the abstract class. Abstract methods do not contain their implementation. Abstract class can be inherited by the subclass and abstract method gets its definition in the subclass. Abstraction classes are meant to be the blueprint of the other class. An abstract class can be useful when we are designing large functions.

``` Python
from abc import ABC  
class ClassName(ABC):  
```

Unlike the other high-level language, Python doesn't provide the abstract class itself. We need to import the abc module, which provides the base for defining Abstract Base classes (ABC). The ABC works by decorating methods of the base class as abstract. It registers concrete classes as the implementation of the abstract base. We use the __@abstractmethod__ decorator to define an abstract method or if we don't provide the definition to the method, it automatically becomes the abstract method.

``` python
from abc import ABC

class Polygon(ABC):
  def sides(self):
    pass

class Triangle(Polygon):
  def sides(self):
    print('Triangle has 3 sides')

class Pentagon(Polygon):
  def sides(self):
    print('Pentagon has 5 sides')
```

``` console
>>> Triangle has 3 sides
>>> Pentagon has 5 sides
```

## List Comprehensions

List comprehension is one the most unique features in Python, allowing us to write powerful functionalities within a single line of code.

Let's first review how to create lists.

### Using _for_ Loops

For loops are the most common and easy way to create lists of elements.

``` Python
squares = []

for i in range(1, 11):
  squares.append(i*i)

print(squares)
```

``` console
>>> [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

### Using _map()_ Objects

The _map()_ function is an alternative approach. You pass in a function and a iterable, and map() will create an object. This object contains the output you would get from running each iterable element through the supplied function.

``` Python
squares = [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

negative = -1

def turn_negative(number):
  return number * negative

negative_squares = map(turn_negative, squares)

negative_squares = list(negative_squares)

print(negative_squares)
```

``` console
>>> [-1, -4, -9, -16, -25, -36, -49, -64, -81, -100]
```

### Using List Comprehensions

List comprehensions are another way of making lists. This this approach, you could rewrite the _for_ loop from our first example in just a single line of code:

``` Python
squares = [i * i for i in range(1, 10)]

print(squares)
```

``` console
>>> [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

Rather than creating an empty list and adding each element to the end, you simply define the list and its contents at the same time by following this format:

``` Python
new_list = [expression for member in iterable]
```

Every list comprehension in Python includes three elements:

1. __expression__ is a call to a method, or any other valid expression that returns a value. In the example above, the expression _i * i_ is the square of the member value.
2. __member__ is the object or value in the list of iterable. In the example above, the member value is i.
3. __iterable__ is a list, set, sequence, generator, or any other object that can return its elements one at a time. In the example above, the iterable is _range(1, 10)_.

Because the __expression__ requirement is very flexible, a list of comprehension in Python works well in many places where you would use map(). You can rewrite the map() example like below:

``` Python
squares = [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

negative = -1

def turn_negative(number):
  return number * negative

negative_squares = [turn_negative(i) for i in squares]

print(negative_squares)
```

``` console
>>> [-1, -4, -9, -16, -25, -36, -49, -64, -81, -100]
```

#### Using Conditional Logic

A more description of the comprehension formula adds support for optional __conditionals__.

``` python
new_list = [expression for member in iterable (if conditional)]
```

One benefit of using conditionals is to filter out unwanted values, which otherwise would require a call to _filter()_.

``` Python
even_squares = [i * i for i in range(1, 11) if i % 2 == 0]

print(even_squares)
```

``` console
>>> [2, 4, 6, 8, 10]
```

More complex conditionals can also be used in the form of custom conditionals:

``` Python
def if_even(num):
  return num % 2 == 0

even_squares = [i * i for i in range(1, 11) if if_even(i)]

print(even_squares)
```

``` console
>>> [2, 4, 6, 8, 10]
```

Ifyou want to change a member value instead of filtering it out? In this case, it's useful to place the conditional near the beginning of the expression:

``` Python
numbers = [-1, 2, 3, -4, -5, 6, 7, -8, 9, -10]

positive_numbers = [i if i > 0 else i * -1 for i in numbers]
```

``` console
>>> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

Again, more complex conditionals can be added instead:

``` Python
def get_positive(num):
  return num if num > 0 else num * -1

numbers = [-1, 2, 3, -4, -5, 6, 7, -8, 9, -10]

positive_numbers = [get_positive(i) for i in numbers]
```

``` console
>>> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

## Lambda Functions

A lambda function is a small anonymous function. A lambda function can take any number of arguments, but can only have one expression.

### Syntax

``` python
lambda arguments : expression
```

For example:

``` Python
def hello_world():
  print('Hello World!')

hello_world()
```

``` console
>>> Hello World!
```

Can be written as:

``` Python
hello_world = lambda : print('Hello World!')

hello_world()
```

``` console
>>> Hello World!
```

Lambda arguments can take any number of arguments:

``` Python
add_two = lambda a, b : return a + b 

print(add_two(10, 5))
```

``` console
>>> 15
```

## Map, Filter, and Reduce Functions

Map, Filter, and Reduce are parts of Python functional programming and allow you to write shorter and simpler codes without using loops, conditionals and more.

### Map

The _map()_ function in Python has the following syntax:

``` python
map(func, *iterables)
```

Where func is the function on which each element in iterables (as many as they are) would be applied on. There can be as many iterables as possible. The number of arguments to func must be the number of iterables listed.

Let's say we have a list of names, some of which are in lowercase, some are uppercase, some are camel-case and some pascal-case. We want them all to be in lower case. We can use a for loop to loop through each element in the list and apply the _.lower()_ function and save the results in a new list. Or we can:

``` Python
def to_lower(word):
  return word.lower()

names = ['john', 'Doe', 'camelCase', 'PascalCase']

lower_names = list(map(to_lower, names))

print(lower_names)
```

``` console
>>> ['john', 'doe', 'camelcase', 'pascalcase']
```

We can also use lambda functions:

``` Python
names = ['john', 'Doe', 'camelCase', 'PascalCase']

lower_names = list(map(lambda x : x.lower(), names))

print(lower_names)
```

``` console
>>> ['john', 'doe', 'camelcase', 'pascalcase']
```

### Filter

While _map()_ passes each element in the iterable through a function and returns the result of all elements having passed through the function, filter, first of all, requires the function to return boolean values (True or False) and then passes each element in the iterable through the function, "filter" away those that are false. It has the following syntax:

``` python
filter(func, iterable)
```

Unlike map, filter takes only one iterable and the func must only take one argument.

Let's say we have a list of numbers and we want to filter out evens from odds:

``` Python
def if_even(number):
  return number % 2 == 0

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

even_numbers = list(filter(if_even, numbers))

print(even_numbers)
```

``` console
>>> [2, 4, 6, 8, 10]
```

We can also use lambda functions:

``` Python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

even_numbers = list(filter(lambda x : x % 2 == 0, numbers))

print(even_numbers)
```

``` console
>>> [2, 4, 6, 8, 10]
```

### Reduce

reduce applies a function of two arguments cumulatively to the elements of an iterable, optionally starting with an initial argument. It has the following syntax:

``` python
reduce(func, iterable[, initial])
```

Where func is the function on which each element in the iterable gets cumulatively applied to, and initial is the optional value that gets placed before the elements of the iterable in the calculation, and serves as a default when the iterable is empty. The following should be noted:

1. func requires two arguments, the first of which is the first element in iterable (if initial is not supplied) and the second element in iterable. If initial is supplied, then it becomes the first argument to func and the first element in iterable becomes the second element.
2. reduce "reduces" iterable into a single value.

Let's say we have a list of numbers and we want to know their cumulative sum:

``` Python
from functools import reduce 

def add_two(number1, number2):
  return number1 + number2

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

cumulative_sum = reduce(add_two, numbers)

print(cumulative_sum)
```

``` console
>>> 55
```

Here, reduce takes the first and second elements in numbers and passes them to add_to respectively. add_two computes their sum and returns it to reduce. reduce then takes that result and applies it as the first element to add_two and takes the next element (which is the third element) in numbers as the second element to add_two. It does this continuously (cumulatively) until numbers is exhausted.

We can also use lambda functions:

``` Python
from functools import reduce 

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

cumulative_sum = reduce(lambda x, y : x + y, numbers)

print(cumulative_sum)
```

``` console
>>> 55
```

If we use an initial argument:

``` Python
from functools import reduce 

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

cumulative_sum = reduce(lambda x, y : x + y, numbers, -55)

print(cumulative_sum)
```

``` console
>>> 0
```

Here, the result is 0 because reduce, initially uses -55 as the first argument to add_two.

## Decorators

Decorators provide a simple syntax for calling high-order functions. High-order functions are functions that either take one or more functions as arguments, or return a function. By definition, a decorator is a function that takes another function and extends the behavior of the latter function without explicitly modifying it.

Before we delve deep into decorators, we must first understand how functions work. Basically, a function returns a value based on the given arguments. Hewre is a very simple example:

``` Python
def add_two(number1, number2):
  return number1 + number2

sum_two = add_two(1, 2)

print(sum_two)
```

``` console
>>> 3
```

### Fist-Class Objects

Some functions return 'None'. Like the _print()_ function. In Python, functions are first-class objects. This means that __functions can be passed around and used as arguments__, just like any other object such as string, int, list, and so on. Consider the example below:

``` Python
def hello(name):
  return f'Hello {name}!'

def greetings(name):
  return f'Greetings {name}!'

def john_function(func):
  return func('John')

print(john_function(hello))

print(john_function(greetings))
```

``` console
>>> Hello John!
>>> Greetings John!
```

Here, _hello()_ and _greetings()_ are regular functions that expect a value and return another value. However, _john_function()_ expects a function as input (note that the function passed as an argument does not have parethesis). In the case of functions passed as arguments: Only the reference to the functions are passed, in contrast, when we call a function with parenthesis, we're calling the function and not passing a reference to be called later.

### Inner Functions

It's possible to define functions inside other functions. Such functions are called inner functions. Here's an example:

``` Python
def parent():
  print('Printing from parent() function!')

  def first_child():
    print('Printing from first_child() function!')
  
  def second_child():
    print('Printing from second_child() function!')
  
  first_child()

  second_child()

parent()
```

``` console
>>> Printing from parent() function!
>>> Printing from first_child() function!
>>> Printing from second_child() function!
```

Two things you have to note:

1. The order in which the inner functions are defined does not matter.
2. The inner functions are not defined until the parent function is called. They are locally scoped to the _parent()_ and cannot be called out of the _parent()_ function.

### Returning Functions From Functions

Python also allows you to use functions as return values. The following example returns one of the inner functions from the outer _parent()_ function:

``` Python
def parent(num):

  def even_child():
    print('First inner function')
  
  def odd_child():
    print('Second inner function')
  
  if num % 2 == 0:
    return even_child
  else:
    return odd_child

even = parent(2)

odd = parent(3)

even()
odd()
```

``` console
>>> First inner function
>>> Second inner function
```

Since _parent()_ returns a function without parenthesis, the returned value is a reference and has to be explicitly called.

### Simple Decorator

Now that we have seen that functions are just like any other object in Python, it's time to learn about Python decorators. Let's start with an example:

``` Python
def my_decorator(func):
  def wrapper():
    print('Before the function call....')
    func()
    print('After the function call....')
  
  return wrapper

def hello_world():
  print('Hello world!')

hello_world = my_decorator(hello_world)

hello_world()
```

``` console
>>> Before the function call....
>>> Hello world!
>>> After the function call....
```

Here, the name _hello\_world_ now points to the _wrapper()_ inner function. And, the _wrapper()_ has a reference to the original _hello\_world()_  and calls the function between the two _print()_ functions.

Simply put: __Decorators wrap a function, modifying its behavior__.

### The "pie" syntax

In python we can use __@__ symbol to make things simpler. For example:

``` Python
def my_decorator(func):
  def wrapper():
    print('Before the function call....')
    func()
    print('After the function call....')
  
  return wrapper

@my_decorator
def hello_world():
  print('Hello world!')

hello_world()
```

``` console
>>> Before the function call....
>>> Hello world!
>>> After the function call....
```

So, _@my\_decorator_ is an easier way of saying: _hello\_world = my\_decorator(hello\_world)_

### Decorating Function With Arguments

Because decorators are usually used with a variety of different functions, some of which take arguments and some don't, we use __*args and **kwargs__ in the wrapper function. Then it will accept an arbitrary number of positional and keyword arguments. For Example:

``` Python
def my_decorator(func):
  def wrapper(*args, **kwargs):
    print('Before the function call....')
    func(*args, **kwargs)
    print('After the function call....')
  
  return wrapper

@my_decorator
def hello_world(name='world'):
  print(f'Hello {name}!')

hello_world()
print()
hello_world('John')
```

``` console
>>> Before the function call....
>>> Hello world!
>>> After the function call....
>>>
>>> Before the function call....
>>> Hello John!
>>> After the function call....
```

### Returning Values From Decorated Functions

To return values, simply add a _return_ statement in the _wrapper()_ function.

``` Python
def my_decorator(func):
  def wrapper(*args, **kwargs):
    print('Before the function call....')
    return func(*args, **kwargs)
  
  return wrapper

@my_decorator
def hello_world(name='world'):
  return f'Hello {name}!'

hello = hello_world()
print(hello)
```

``` console
>>> Before the function call....
>>> Hello world!
```

### Function and Wrapper Identity

One of Python's greatest features is __Introspection__. __Introspection__ is the ability of an object to know about its own attributes at runtime. For instance, functions knows its own name and documentation:

``` console
# Python Console

>>> print
<build-in function print>

>>> print.__name__
'print'

>>> help(print)
Help on build-in function print in module builtins:

print(...)
  <full help message>
```

This introspection works for functions you define as well. However, after being decorated functions lose their introspection and to remedy this we have to use __@functools.wraps__ decorator, which will preserve information about the original function. For example:

``` Python
import functools

def my_decorator(func):
  @functools.wraps(func)
  def wrapper(*args, **kwargs):
    print('Before the function call....')
    value = func(*args, **kwargs)
    print('After the function call....')
    return value
  
  return wrapper

@my_decorator
def hello_world(name='world'):
  return f'Hello {name}!'

print(hello_world)
print(hello_world.__name__)
print(help(hello_world))
```

``` console
>>> <function hello_world at 0x7ff79a60f2f0>
>>> 'hello_world'
>>> Help on function hello_world in module decorator_tutorial
  hello_world()
```

The __@functools.wraps__ decorators uses the function functools.update_wraper() to update special attributes like \__name__ and \__doc__ that are used in the introspection.

It's common to save decorators in a module and reuse them on multiple functions, especially inside classes. Also it is possible to use multiple decorators on a single function.

## Context Managers and the 'with' Statement

The _with_ statement in Python is a quite useful tool for properly managing external resources. One common problem you'll face in programming is how to properly __external resources__, such as files, locks, and network connections. Besides, the __context management protocol__ allows you to create your own context managers so you can customize the way you deal with system resources. Managing resources requires both a setup phase and a teardown phase. and the latter phase requires performing cleanup actions, such as closing a file, releasing a lock, or closing a network connection.

The Python __with statement__ creates a __runtime context__ that allows you to run a group of statements under the control of a __context manager__. To write a _with_ statement, you need to use the following general syntax:

``` Python
with expression as target_var:
  do_something(target_var)
```

The context manager object results from evaluating the _expression_ after _with_ In other words, _expression_ must return an object that implements the __context management protocol__. This protocol consists of two special methods:

1. __.\__enter\__()__  is called by the _with_ statement to enter the runtime context.
2. __.\__exit\__()__  is called when the execution leaves the _with_ code block.

The _as_ specifier is optional. If you provide a _target\_var_ with _as_, then the __return__ value of calling __.\__enter\__()__ on the context manager object is bound to that variable.

For example:

``` Python
with open('hello.txt', mode='w') as file:
  file.write('hello world')
```

When you run this _with_ statement, _open()_ returns an __io.TextIOBase__ object. This object is also a context manager, so the_with_statement calls __.\__enter\__()__ and assigns its return value to_file_. Then you can manipulate the file inside the_with_ code block. When the block ends, __.\__enter\__()__ automatically gets called and closes the file for you, even if an exception is raised inside the _with_ block.

You can supply any number of context managers separated by commas which works like a _nested with_ statement. For example:

``` Python
with open('input.txt') as in_file, open('output.txt', 'w') as ou_file:
  # Read
  # Transform
  # Write
  pass
```

The better way of opening file is using __pathlib.Path.open()__:

``` python
import pathlib

file_path = pathlib.Path('hello.txt')

with file_path.open('w') as o_file:
  file.write('hello world')
```

__Path__ is a class that represents concrete paths to physical files in your computer. Calling _.open()_ on a _Path_ object that points to a physical file opens it just like open() would do. So, _Path.open()_ works similarly to _open()_, but the file path is automatically provided by the _Path_ object you call the method on. This is the recommended way of opening files.

Finally, whenever you load an external file, your program should check for possible issues, such as a missing file, writing and reading access, and so on. Here's a general pattern that you should consider using when you're working with files:

``` python
import pathlib
import logging

file_path = pathlib.Path('hello.txt')

try:
  with file_path.open(mode='w') as o_file:
    file.write('hello world')
except OSError as error:
  logging.error('Writing to file %s failed due to: %s', file_path, error)
```

## Iterators and Generators

### Iterators

Iterators are objects that can be iterated (looped) upon. An object which will return data, one element at a time represents a data stream and implements the iterator protocol, which consists of the method __iter()__ and __next()__. The __iter()__ method returns the iterator object itself, and the __next()__ method returns the following items from the iterator. If there are no more items to return, the __next()__ method should raise _StopIteration_ exception.

#### Custom Iterators

Creating custom iterators in Python allows you to define the behavior of an iterator for a specific use case. For example:

``` Python
class MyIterator:
  def __init__(self, start, end):
    self.start = start
    self.end = end
    self.current = start

  def __iter__(self):
    return self

  def __next__(self):
    if self.current > self.end:
      raise StopIteration
    else:
      self.current += 1
      return self.current
```

This iterator class takes a start and an end value as arguments and returns the numbers in the range when iterated over.

Implementing the above class and creating an instance of it, we can use it as an iterator, for example:

``` python
for i in MyIterator(1, 5):
  print(i)
```

This will print the numbers from 1 to 5.

Creating custom iterators for large data sets is an efficient way of processing them. By creating a custom iterator, you can control how the data is accessed and limit the amount of data loaded into memory at any given time.

### Generator

A generator is a type of iterator in Python that allows you to declare a function that behaves like an iterator. They use the yield statement to return data and are a more memory-efficient way of working with large data sets.

A generator function is defined like a regular function, but instead of using the __return__ statement, it uses the __yield__. When the generator function is called, it returns a generator object but does not execute the function body immediately. The function body is executed only when its __next()__ method is called.

Generators are a more efficient way of working with big data because the entire data set is not stored in memory. Instead, it generates the data one item at a time each time __next()__ is called.

#### Creating Custom Generators

Creating custom generators in Python allows you to define the behavior of a generator for a specific use case. For example:

``` python
def  fibonacci(n):
  a, b = 0, 1
  for i in range(n):
    yield a
    a, b = b, a + b
```

This generator function takes an argument __n__, and generates the first _n_ numbers of the Fibonacci sequence when iterated over.

``` python
for i in fibonacci(5):
  print(i)
```

Iterators and generators also allow you to completely decouple iteration from processing individual items. They let you connect multiple data processing stages to create memory-efficient data processing pipelines.

## Regular Expressions

A _regular expression_ is a special sequence of characters that help you match or find other strings or sets of strings.

The Python module rre is used to work with Regular Expressions.

### RegEx Functions

the __re__ module offers a set of functions that allows us to search a string for a match:

1. _findall_: Returns a list containing all matches
2. _search_: Returns a __Match object__ if there is a match anywhere in the string
3. _split_: Returns a list where the string has been split at each match
4. _sub_: Replaces one or many matches with a string

### Meta-Characters

Meta-characters are character with a special meaning:

1. []   A set of characters         "[a-m]"
2. \    Signals a special sequence  "\d"
3. .    Any character               "he..o"
4. ^   Any character               "he..o"
5. $    Any character               "he..o"
6. \*    Any character               "he..o"
7. \+    Any character               "he..o"
8. ?    Any character               "he..o"
9. {}    Any character               "he..o"
10. |    Any character               "he..o"
11. ()    Any character               "he..o"

## Multi-Threading and Multi-Processing

Threading and multi-processing are two of the most fundamental concepts in programming.

### Concurrency and Parallelism

In many occasions we may need to speed up a few operations in our code base in order to boost the performance of the execution. This can normally be achieved by executing multiple tasks in parallel or concurrently (i.e. by interleaving between multiple tasks). Whether you could take advantage of concurrency or parallelism really depends on your code but on the machine that is running it, too.

In __concurrent execution__, two or more tasks can start, execute and complete in overlapping time periods. Therefore, these tasks don't necessarily have to run simultaneously - they just need to make progress in an overlapping manner.

__Concurrency__ is a condition that exists when at least two threads are making progress. A more generalized form of parallelism that can include time-slicing as a form of virtual parallelism.

One of the main goals of concurrency is to prevent tasks from blocking each other by switching back and forth, when one of the tasks is forced to wait (say for a response from an external resource). For example, Task A progresses till a certain point, the the CPU stops working on Task A, switches to Task B and starts working on it for a while and then it could switch back to Task A to finish it, and finally return back to Task B till it finishes this task, too.

On the other hand, in __parallelism__ multiple tasks (or even several components) can __literally run at the same time__ (e.g. on a multi-core processor or on a machine with multiple CPUs). Therefore, it is not possible to have parallelism on machines with a single processor and single core.

__Parallelism__ is a condition that arises when at least two threads are executing simultaneously.

To recap, concurrency can be seen as a property of a system or program and refers to how a single CPU cn make progress on multiple tasks seemingly at the same time (i.e. concurrently) while parallelism is the actual run-time behavior of executing at least two tasks literally at the same time, in parallel. Additionally, it is important to highlight that both concurrency and parallelism could be combined during task execution. In fact, we could have all sort of combinations:

- __Neither concurrent, nor parallel__: This is also known as _sequential execution_ where tasks are executed strictly one after the other.
- __Concurrent, but not parallel__: This means that the tasks make progress seemingly at the same time, but in fact the system switches between various tasks that are concurrently in progress, until all of them are executed. There fore, there is no true parallelism and thus no two tasks are being executed at exactly the same time.
- __Parallel, but not concurrent__: This is fairly rare scenario where only one task is being executed at any given time, but the task itself is broken down into sub-tasks that are being processed in parallel. Every task though, must be completed before the next task is picked up and executed.
- __Concurrent and Parallel__: This could happen basically in two ways; The first is the simple parallel and concurrent execution where the application fires up multiple threads that are being executed on multiple CPUs and/or cores. The second way that this can be achieved is when the application is able to work on multiple tasks concurrently but at the same time it also breaks down each individual task into sub-tasks so these sub-tasks can be eventually executed in parallel.

### Multithreading in Python

A thread is a sequence of instructions that are being executed within the context of a process. One process can spawn multiple threads but all of them will be sharing the same memory.

A Python process cannot run threads in parallel but it can run them concurrently through context switching during I/O operations. The Python __Global Interpreter Lock__ (GIL) prevents threads within the same process to be executed at the same time.

In Python, threads can be implemented with the use of _threading_ module. Let's examine the code below:

``` python
import time

def calc_square(numbers):
    for n in numbers:
        print(f'\n{n} ^ 2 = {n*n}')
        time.sleep(0.2)

def calc_cube(numbers):
    for n in numbers:
        print(f'\n{n} ^ 3 = {n*n*n}')
        time.sleep(0.2) 

numbers = [2, 3, 5, 8]

start = time.time()

calc_square(numbers)
calc_cube(numbers)

end = time.time()

print('Execution Time: {}'.format(end-start))
```

Let's assume the __calc_square__ and __calc_cube__ are I/O functions that take a while to finish. As you can see in the traditional/sequential programming, the program has to wait for each task to finish. But, now let's look at an example utilizing _threading_:

``` python
import threading
import time

def calc_square(numbers):
    for n in numbers:
        print(f'\n{n} ^ 2 = {n*n}')
        time.sleep(0.2)

def calc_cube(numbers):
    for n in numbers:
        print(f'\n{n} ^ 3 = {n*n*n}')
        time.sleep(0.2) 

numbers = [2, 3, 5, 8]

start = time.time()

square_thread = threading.Thread(target=calc_square, args=(numbers,))
cube_thread = threading.Thread(target=calc_cube, args=(numbers,))

square_thread.start()
cube_thread.start()

square_thread.join()
cube_thread.join()

end = time.time()

print('Execution Time: {}'.format(end-start))
```

Here, we use the Thread constructive method to create a thread instance. The _Thread_ method takes two inputs, the function name and its arguments. This function is what will be executed when a thread begins execution. When we instantiate the Thread class, the Thread constructive method will be invoked automatically, and it will create a new thread.

But the new thread won't begin execution immediately, which is a valuable synchronization feature that lets us start the threads once all of them have been allocated. To begin the thread execution, we need to call each thread instance's start method separately.

The last thing we need to do is call the join method, which tells one thread to wait until the other thread's execution.

While the sleep method suspends the execution of the calc_square() function for 0.2 seconds, the calc_cube() function is executed and prints out the cube of a value in the list, then it goes into a sleep, and the calc_square() function will be executed. In other words, the operating system switches back and forth between the threads, running each one a little bit at a time, which leads to an improvement in the runtime of the entire process.

### Multiprocessing in Python

There are three main classes in Python multiprocessing module for building parallel programming also known as multiprocessing. These three classes are: __Process__, __Queue__, and __Lock__.

#### Process

The Python multiprocessing __Process__ class allows us to set up control the execution of parallel processes. There are two important functions we need to know about: __start()__ and __join()__. The process class requires a function to instantiate, we then have to start the process and finally complete the process. For example:

``` python
from multiprocessing import Process

def print_func(continent='Asia'):
  print('The name of continent is: ', continent)

names = ['America', 'Europe', 'Africa']

procs = []

proc = Process(target=print_func)
procs.append(proc)
proc.start()

for name in names:
  proc = Process(target=print_func, args=(name,))
  procs.append(proc)
  proc.start()

for proc in procs:
  proc.join()
```

``` console
>>> The name of continent is:  Asia
>>> The name of continent is:  America
>>> The name of continent is:  Africa
>>> The name of continent is:  Europe
```

#### Queue Class

The __Queue__ class is a __First_In_First_Out__ data structure. They can store any pickle Python object. Queues are specially useful when passed as a parameter to __Process__'s target function to enable the _Process_ to consume data. By using __put()__ function we can insert data to the queue and using __get()__ we get items from the queue. For example:

``` python
from multiprocessing import Queue

colors = ['red', 'green', 'blue', 'black']

queue = Queue()

print('Pushing items to queue:')
for i in range(len(colors)):
  print('Item no: ', i+1, ' ', colors[i])
  queue.put(colors[i])

i = 1
print('\npopping items from queue: ')
while not queue.empty():
  print('Item no: ', i, ' ', queue.get())
  i += 1
```

``` console
Pushing items to queue:
Item no:  1   red
Item no:  2   green
Item no:  3   blue
Item no:  4   black
popping items from queue: 
Item no:  1   red
Item no:  2   green
Item no:  3   blue
Item no:  4   black
```

#### Lock Class

The __Lock__ class is quite simple. It allows code to claim lock so that no other process can execute the similar code until the lock has been released. So the task of Lock class is mainly two: One is to claim lock using __acquite()__, abd the other is to release lock using __release()__.

#### MultiProcessing Example

The Python __Queue__ class is already synchronized. Which means, we don't need to use the Lock class to block multiple processes to access the same queue objet.

Example:

``` python
from multiprocessing import Lock, Process, Queue, current_process
import time
import queue

def do_job(tasks_to_accomplish, tasks_that_are_done):
  while True:
    try:
      '''
        try to get task from the queue. get_nowait() function will raise
        queue.Empty exception if the queue is empty.
        queue(False) function would do the same task also.
      '''
      task = tasks_to_accomplish.get_nowait()
    except queue.Empty:
      break
    else:
      '''
        if no exception has been raised, add the task completion 
        message to tasks_that_are_done que  
      '''
      print(task)
      tasks_that_are_done.put(task + ' is done by ' + current_process().name)
      time.sleep(50)
  return True

def main():
  number_of_tasks = 10
  number_of_processes = 4
  tasks_to_accomplish = Queue()
  tasks_that_are_done = Queue()
  processes = []

  for i in range(number_of_tasks):
    tasks_to_accomplish.put('Task no ' + str(i+1))
  
  for w in range(number_of_processes):
    p = Process(target=do_job, args=(tasks_to_accomplish, tasks_that_are_done))
    processes.append(p)
    p.start()
  
  for p in processes:
    p.join()
  
  while not tasks_that_are_done.empty():
    print(tasks_that_are_done.get())
  
  return True

main()
```

#### Python multiprocessing Pool

The multiprocessing.Pool class provides a simple way to parallelize the execution of a function across multiple input values. The Pool class creates a pool of worker processes, and each worker process can execute the same function with different input values. The input values are distributed across the worker processes by the Pool class, and the results are collected and returned to the main process.

``` python
from multiprocessing import Pool

def square(number):
    return number ** 2

if __name__ == '__main__':
    numbers = [1, 2, 3, 4, 5]
    pool = Pool(processes=2)
    result = pool.map(square, numbers)
    print(result)
```

In this example, we define a function square that takes a number as input and returns its square. We then create a list of numbers and a Pool object with two worker processes. We use the map() method of the Pool object to apply the square function to each number in the list. The map() method distributes the input values across the worker processes and returns the results as a list. Finally, we print the result.

When you run this script, you should see the squares of the numbers printed out as a list:

``` console
[1, 4, 9, 16, 25]
```

## Data Access and SQL

Python provides several libraries and modules for accessing and working with databases using SQL. The most commonly used Python libraries for working with databases are:

- __sqlite3__: This is a built-in module in Python that provides a lightweight, serverless database engine that can be used for small-scale data storage.
- __MySQL Connector__: This is a library that provides a Python interface for connecting to MySQL database.
- __psycopg2__: This is a library that provides a Python interface for connecting to _postgreSQL_ databases.
- __pyodbc__: This is a library that provides a Python interface for connecting to databases using the ODBC API.

To work with these libraries, you first need to install them using pip. Once you have installed the required library, you can establish a connection to the database using the library's connection object. For example, to connect to a MySQL database, you can use the following code:

``` python
import mysql.connector

db = mysql.connector.connect(
  host = 'localhost',
  user='username',
  password='password,
  database='database_name
)

cursor = db.cursor()
```

In this example, we use the __msql.connector__ library to connect to a MySQL database running on the localhost. We provide the username, password, and database name to the __connect()__ method of the library's connection object, we then create a cursor object to execute SQL queries.

Once you have established a connection to the database, you can execute SQL queries using the cursor object. For example, to create a table in the database, you can use the following code:

``` python
cursor.execute("CREATE TABLE users (id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(255), email VARCHAR(255))")
```

In this example, we use the __execute()__ method of the cursor object to execute an SQL query to create a table named __users__. The table has three columns: __id__, __name__, and __email__.

You can also execute SQL queries that retrieve data from the database. For example, to retrieve all the rows from __users__ table, you can use the following code:

``` python
cursor.execute("SELECT * FROM users")

rows = cursor.fetchall()

for row in rows:
  print(row)
```

In this example, we use the __execute()__ method of the cursor object to execute an SQL query to select all the rows from the __users__ table. We then use the __fetchall()__ method of the cursor object to retrieve all the rows returned by the query, and print them out.

The most common methods for executing queries with a cursor object are:

- __execute(query)__: Executes a single SQL query and returns no results
- __executemany(query, data)__: Executes a single SQL query with multiple sets of data and returns no results
- __fetchone(query)__: Retrieves the next row of a query result set as a tuple or None if no more rows are available.
- __fetchmany(size=None)__: Retrieves the next set of rows of a query result set as a list of tuples, or an empty list if no more rows are available.
- __fetchall()__: Retrieves all remaining rows of a query result set as a list of tuples, or an empty list if no rows are available.

## Web Scraping and APIs

Web scraping and API are two very important topics that any Python programmer or a data analyst or anyone that works in this field will have to deal with.

### Web Scraping

Web scraping is the process of extracting data from websites using code. Here are the basic steps involved in web scraping using Python:

1. __Inspect the website__: Before you can scrape data from a website, you need to inspect the website's HTML structure and identify the elements that contain the data you want to extract. You can use your browser's developer tools to inspect the HTML.
2. __Install and import the necessary libraries__: You can use several libraries for web scraping in Python, such as Beautiful Soup and Scrapy.
3. __Send a request to the website__: To access the website's HTML content, you need to send a request to the website's server using Python's __request__ library. Here is an example:

``` python
import requests

url = 'https://www.example.com'
response = requests.get(url)
html_content = response.content
```

in this example, we send a GET request to the URL __https://www.example.com__ using the __requests.get()__ method. We then store the HTML content of the response in the variable __html_content__.

4. __Parse the HTML content__: Once you have retrieved the website's HTML content, you need to parse the content using a parsing library like Beautiful Soup.

``` python
soup = BeautifulSoup(html_content, 'tml.parser')
```

5. __Extract the data__: Using the parsing library, you can extract the data from the HTML content and store it in a data structure like a list or a dictionary. Here's an example of extracting all the links from a website:

``` python
links = []

for link in soup.find_all('a'):
  href = link.get('href')
  links.append(href)
```

In this example, we use the __find_all()__ method of the __soup__ object to find all the __a__ tags in the HTML content. We then extract the __href__ atribute of each tag using the __get()__ method, and append it to the __links__ list.

### APIs

Application Programming Interfaces or APIs are a way for different applications to communicate and share data with each other. Here are the basic steps involved in working with APIs using Python:

1. __Identify the API endpoint__: The first step in working with an API is to identify the endpoint that provides the data you want to access. API documentation usually provides the data you want to access. API documentation usually provides information about available endpoints and how to use them.
2. __Install and import the necessary libraries__: To work with APIs in Python, you can use libraries such as __requets__, __json__, and __pandas__.
3. __Send a request to the API endpoint__: To access the API endpoint, you need to send a request to the endpoint's URL using the __requests__ library. Here's an example of sending a request to an API endpoint:
  
``` python
import requests

url = 'https://api.example.com/data'
response = requests.get(url)
```

In this example, we send a GET request to the API endpoint URL __https://api.example.com/data__ using the __requests.get()__ method. We then store the response in the __response__ variable.

4. __Parse the response__: Once you have recieved the API response, you need to parse the response data using the appropriate data format, such as JSON or XML. Here's an example of parsing a JSON API response:

``` python
import json

json_data = response.text
data = json.loads(json_data)
```

In this example, we parse the JSON response using the __kson.loads()__ method, which converts the JSON data into a Python object.

5. __Extract the data__: Using the parsing library and the appropriate data format, you can extract the data from the API response and store it in a data structure like a list or dictionary. Here's an example of extracting data from JSON API response:

``` python
import requests
import json

url = 'https://api.example.com/data'

response = requests.get(url)
json_data = response.text
data = json.loads(json_data)

results = data['results']
for result in results:
  print(result['name'], result['age'])
```

In this example, we extract data from a JSON API response by accessing the __results__ key of the __data__ dictionary, and then iterating through the list of results and printing out the __name__ and __age__ keys of each result.

## Numpy, Pandas, and Matplotlib

### Numpy

Numpy (Numerical Python) is designed for scientific computing. It provides tools for working with arrays, linear algebra, random numbers, and various mathematical functions.

#### Numpy Arrays

Numpy arrays are the foundation of the library. They can have any number of dimensions, and they are more efficient than python lists for numerical operations.

##### Creating Arrays

``` python
# 1D array
arr1 = np.array([1, 2, 3])

# 2D array
arr2 = np.array([[1, 2], [3, 4]])

# Array of zeros
arr_zeros = np.zeros((2, 2))

# Array of ones
arr_ones = np.ones((3,3))

# Identity matrix
identity_matrix = np.eye(3)

# Linearly spaced array
lin_space = np.linspace(0, 1, 5)
```

##### Aray attributes

``` Python
# shape
shape = arr1.shape

# Dimensions
dims = arr1.ndim

# Data type
dtype = arr1.dtype
```

##### Array indexing and slicing

``` Python
# Accessing elements
element = arr1[0]

# Slicing 1D array
sliced_arr = arr1[1:3]

# Slicing 2D array
sliced_arr_2D = arr2[0:2, 1]
```

#### Array operations

NumPy allows element-wise and matrix operations, including addition, subtraction, multiplication, division, and more.

##### Element-wise operations

``` Python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])

# Addition, Subtraction, Multiplication, Division
add_result = arr1 + arr2
sub_result = arr1 - arr2
mul_result = arr1 * arr2
div_result = arr1 / arr2
```

##### Matrix Operations

``` Python
A = np.array([1, 2], [3, 4])
B = np.array([5, 6], [7, 8])

# Matrix multiplication
matmul_result = np.dot(A, B)

# Transpose
transpose_A = A.T

# Inverse
inverse_A = np.linalg.inv(A)

# Determinant
det_A = np.linlang.det(A)

# Eigenvalues and eigenvectors
eigenvalues, eigenvectors = np.linalg.eig(A)
```

#### Broadcasting

Numpy allows operations on arrays with different shapes, following specific broadcasting rules.

``` Python
arr1 = np.array([1, 2, 3])
arr2 = np.array([1, 2, 3], [4, 5, 6])

# Broadcasting
broadcast_result = arr1 + arr2
```

#### Universal functions (Ufuncts)

Numpy provides various mathematical functions for element-wise operations

``` Python
arr = np.array([1, 2, 3])

# Square root
sqrt_arr = np.sqrt(arr)

# Exponent
exp_arr = np.exp(arr)

# Logarithm
log_arr = np.log(arr)
```

#### Random numbers

Numpy offers tools to generate random numbers from various distributions.

``` Python
# Generate a random float between 0 and 1
random_float = np.random.random()

# Generate a random integer between a range
random_int = np.random.randint(1, 10)

# Generate an array of random floats
random_floats = np.random.rand(3, 3)

# Generate an array of random integers
random_integers = np.random.randint(1, 10, size=(3,3))

# Generate an array from a normal distribution
normal_distribution = np.random.normal(0, 1, size=(3, 3))
```

#### Array manipulation

NumPy provides various functions to manipulate arrays, such as resha[ing, concatenation, and splitting.]

##### Reshaping

``` Python
arr = np.array([1, 2, 3, 4, 5, 6])

# Reshape to 2x3 array
reshaped_arr = arr.reshape(2, 3)
```

##### Concatenation

``` Python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])

# Concatenate along an axis
concatenated_arr = np/concatenate((arr1, arr2), axis=0)
```

##### Splitting

``` Python
arr = np.array([1, 2, 3, 4, 5, 6])

# Split array into equal parts
split_arr = np.split(arr, 3)
```

#### Masking and boolean operations

NumPy enables filtering arrays using boolean arrays and comparisons.

``` Python
arr = np.array([1, 2, 3, 4, 5, 6])

# Create a boolean array using a comparison
bool_arr = arr > 3

# Filter elements using the boolean array
filtered_arr = arr[bool_arr]
```

#### Advanced indexing and slicing

NumPy allows for more advanced indexing using arrays, integers, or slices.

##### Integer indexing

``` Python
arr = np.array([1, 2], [3, 4], [5, 6])

# Select specific elements using integer arrays
indexed_arr = arr[[0, 1, 2], [0, 1, 0]]
```

##### Slicing with steps

``` Python
arr = np.array([1, 2, 3, 4, 5, 6])

# Slice array with a step of 2
sliced_arr = arr[0:6:2]
```

### Pandas

Pandas is used for data manipulation and analysis. It provides powerful data structures such as Series and DataFrames for handling various data types, including time series data.

#### Pandas Data Structures

##### Series

A Pandas Series is a one-dimensional labeled array capable of holding any data type.

```Python
data = [1, 2, 3, 4]
series = pd.Series(data, index=['a', 'b', 'c', 'd'])
```

##### DataFrame

A Pandas DataFrame is a two-dimensional labeled data structure with columns of potentially different types.

```Python
data = {'A': [1, 2, 3], 'B': [4, 5, 6], 'c': [7, 8, 9]}
df = pd.DataFrame(data)
```

#### Input/Output

##### Reading CSV

```Python
csv_file = 'file.csv'
df = pd.read_csv(csv_file)
```

##### Writing CSV

```Python
csv_file = 'output.csv'
df.to_csv(csv_output, index=False)
```

#### Data Inspection and Selection

##### Inspecting Data

```Python
# View the first n rows (default 5)
df.head(n=3)

# Vie the last n rows (default 5)
df.tail(n=3)

# Display summary statistics
df.describe()
```

##### Selecting Data

```Python
# Select column(s)
column_A = df['A']
column_A_B = df[['A', 'B']]

# Select row(s) by index
row_1 = df.loc[1]

# Select row(s) by condition
row_condition = df[df['A'] > 2]

# Select value(s) by index and column
value = df.at[1, 'A']
```

#### Data Manipulation

##### Renaming Columns

``` Python
df.rename(columns={'A': 'Col_A', 'B': 'Col_B'}, inplace=True)
```

##### Adding Columns

``` Python
df['D'] = [10, 11, 12]
```

##### Removing Columns

``` Python
df.drop('C', axis=1, inplace=True)
```

##### Sorting

``` Python
df.sort_values(by=['col_A'], ascending=False, inplace-True)
```

#### Missing Data Handling

##### Drop Missing Data

``` Python
df.dropna(axis=0, inplace=True)
```

##### Fill Missing Data

``` Python
df.fillna(value=0, inplace=True)
```

#### Grouping and Aggregation

##### Grouping

``` Python
grouped = df.groupby('A')
```

##### Aggregation

``` Python
aggregated = df.groupby('A').agg({'B': 'sum', 'C': 'mean'})
```

#### Merging and Concatenation

##### Merging

``` Python
merged = pd.merge(df1, df2, on='key', how='left')
```

##### DF Concatenation

``` Python
concatenated = pd.concat([df1, df2], axis=0, ignore_index=True)
```

#### Time Series Functionality

##### Convert to datetime object

``` Python
df['date'] = pd.to_datetime(df['date'])
```

##### Set index to datetime

``` Python
df.set_index('date', inplace=True)
```

##### Resampling

``` Python
# Resample to monthly frequency
monthly = df.resample('M').mean()

# Resample to daily frequency
daily = df.resample('D').interpolate()
```

##### Rolling Window

``` Python
# Compute the rolling mean with a 3-day window
rolling_mean = df['A'].rolling(window=3).mean()
```

##### Shifting Data

``` Python
# Shift data forward by 1 step
shifted_forward = df.shift(1)

# Shift data backward by 1 step
shifted_backwards = df.shift(-1)
```

##### Time Zone Handling

``` Python
# Convert to a specific time zone
df_tz = df.tz_localize('UTC').tz_convert('US/Eastern')
```

#### Apply and Map Functions

##### Apply function to each element in a DataFrame or Series

``` Python
def example_function(x):
  return x * 2

df['A'] = df['A'].apply(example_function)
```

##### Apply function element-wise using the 'map' function

``` Python
df['A'] = df['A'].map(example_function)
```

##### Apply a function to each column or row using __apply__

``` Python
df['sum'] = df.apply(lambda row: row['A'] + row['B'])
```

### Matplotlib

Matplotlib is used for creating static, animated, and interactive visualizations. It provides a high-level interface for drawing attractive and information statistical graphics.

#### Basic Plots

##### Line Plot

``` Python
x = [0, 1, 2, 3, 4]
y = [0, 2, 4, 6, 8]

plt.plot(x, y)
plt.show()
```

##### Scatter Plot

``` Python
plt.scatter(x, y)
plt.show()
```

##### Bar Plot

``` Python
categories = ['A', 'B', 'C', 'D', 'E']
values = [3, 7, 2, 5, 8]

plt.bar(categories, values)
plt.show()
```

##### Histogram

``` Python
data = [1, 1, 2, 3, 3, 3, 4, 4, 5]

plt.hist(data, bins=5)
plt.show()
```

#### Customizing Plots

##### Adding title and labels

``` Python
plt.plot(x, y)
plt.title('Line Plot')
plt.xlabel('X-Axis Label')
plt.ylabel('Y-Axis Label')
plt.show()
```

##### Changing line style and adding markers

``` Python
plt.plot(x, y, linestyle='--', marker='o', color='r')
plt.show()
```

##### Adding Legend

``` Python
plt.plot(x, y, label='Line 1')
plt.legend()
plt.show()
```

##### Setting axis limits

``` Python
plt.plot(x, y)
plt.xlim(0, 6)
plt.ylim(-2, 10)
plt.show()
```

#### Multiple Plots

##### Subplots

``` Python
fig, axes = plt.subplots(1, 2, figsize=(10, 5))
axes[0].plot(x, y)
axes[1].scatter(x, y)
plt.show()
```

##### Overlaying plots

``` Python
plt.plot(x, y)
plt.scatter(x, y)
plt.sow()
```

#### Advanced Plots

##### 3D plots

``` Python
from mpl_toolkits.mplot3d import Axes3D

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

x = [1, 2, 3, 4, 5]
y = [5, 6, 7, 8, 9]
z = [9, 8, 7, 6, 5]

ax.scatter(x, y, z)
plt.show()
```

##### Contour plots

``` Python
import numpy as np

x = np.linspace(-5, 5, 100)
y = np.linspace(-5, 5, 100)

X, Y = np.meshgrid(x, y)
Z = np.sin(np.sqrt(X**2 + Y**2))

plt.contour(X, Y, Z, 20)
plt.show()
```

##### Heatmaps

``` Python
data = np.random.rand(10, 10)

plt.imshow(data, cmap='hot', interpolation='nearest')
plt.colorbar()
plt.show()
```

##### Box plots

``` Python
data = [np.random.normal(0, std, 100) for std in range(1, 5)]

plt.boxplot(data)
plt.show()
```

##### Violin plots

``` Python
plt.violinplot(data)
plt.show()
```

#### Customizing plot styles and colors

##### Available plot styles

``` Python
print(plt.style.available)
```

##### Using plot styles

``` Python
plt.style.use('ggplot')
```

##### Customizing colormaps

``` Python
from matplotlib.colors import ListedColormap

# Define a custom color
custom_cmap = ListedColormap(['red', 'green', 'blue'])

# Use the custom colormap in a plot
plt.scatter(x, y, c=z, cmap=custom_cmap)
plt.colorbar()
plt.show()
```

#### Saving plots

``` Python
plt.plot(x, y)
plt.savefig('line_plot.png', dpi=300, bbox_inches='tight')
```

## Logging

Python's logging module provides a flexible framework for emitting log messages from applications. It is a built-in library that offers a robust and versatile way to track events, errors, and other information during program execution.

### Importing the logging module

``` Python
import logging
```

### Basic Loggins

#### Default logging configuration (root logger)

``` Python
logging.basicConfig(level=logging.DEBUG)
```

#### Log messages with different severity levels

``` Python
logging.debug("This is a debug message.")
logging.info("This is a info message.")
logging.warning("This is a warning message.")
logging.error("This is a error message.")
logging.critical("This is a critical message.")
```

### Configuration Loggers, Handlers, and Formatters

#### Create a logger

``` Python
logger = logging.getLogger("my_logger")
logger.setLEvel(logging.DEBUG)
```

#### Create a file handler

``` Python
file_handler = logging.FileHandler("my_log_file.log")
file_handler.setLevel(logging.DEBUG)
```

#### Create a stream formatter

``` Python
stream_handler = logging.StreamHandler()
stream_handler.setLevel(logging.ERROR)
```

#### Create a formatter

``` Python
formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
```

#### Add formatter to handlers

``` Python
file_handler.setFormatter(formatter)
stream_handler.setFormatter(formatter)
```

#### Add handlers to logger

``` Python
logger.addHandler(file_handler)
logger.addHandler(stream_handler)
```

### Using the configured logger

``` Python
logger.debug("This is a debug message.")
logger.info("This is a info message.")
logger.warning("This is a warning message.")
logger.error("This is a error message.")
logger.critical("This is a critical message.")
```

### Logging exceptions

#### Log exceptions with traceback

``` Python
try:
  1 / 0
except ZeroDivisionError:
  logger.exception("Division by zero.")
```

### Logging with custom context information

#### Using LogRecord attributes

``` Python
formatter = logging.Formatter('%(asctime)s - %(name)s [%(filename)s:%(lineno)d] - %(levelname)s - %(message)s')
```

#### Add custom information to the log records

``` Python
extra = {'username': 'John Doe'}

logger.info("User logged in.", extra=extra)
```

### Configuring logging with a configuration file or dictionary

#### Configuration file (INI-style)

``` ini
[loggers]
keys=root,sampleLogger

[handlers]
keys=consoleHandler

[formatters]
keys=simpleFormatter

[logger_root]
level=DEBUG
handlers=consoleHandler

[logger_sampleLogger]
level=DEBUG
handlers=consoleHandler
qualname=sampleLogger

[handler_consoleHandler]
class=StreamHandler
level=DEBUG
formatter=simpleFormatter
args=(sys.stdout,)

[formatter_simpleFormatter]
format=%(asctime)s - %(name)s - %(levelname)s - %(message)s

```

#### Load configuration from a file

``` Python
import logging.config

logging.config.fileConfig('logging.conf')
logger = logging.getLogger("sampleLogger")
```

#### Dictionary-based configuration

``` Python
import logging.config

config_dict = {
    'version': 1,
    'formatters': {
        'simple': {
            'format': '%(asctime)s - %(name)s - %(levelname)s - %(message)s'
        }
    },
    'handlers': {
                'console': {
            'class': 'logging.StreamHandler',
            'level': 'DEBUG',
            'formatter': 'simple',
            'stream': 'ext://sys.stdout',
        }
    },
    'loggers': {
        'sampleLogger': {
            'level': 'DEBUG',
            'handlers': ['console'],
            'propagate': False
        }
    },
    'root': {
        'level': 'DEBUG',
        'handlers': ['console']
    }
}

logging.config.dictConfig(config_dict)
logger = logging.getLogger("sampleLogger")


```

### Using log filters

#### Create a custom log filter

``` Python
class InfoFilter(logging.Filter):
  def filter(self, record):
    return record.levelno == logging.INFO
```

#### Add filter to a handler

``` Python
info_filter = InfoFilter()
file_handler.addFilter(info_filter)
```

## Farewell

Thank you for reading this Github article on Advanced Python Concepts. Creating this tutorial project was very fun and I hope you enjoyed reading it as much as I enjoyed creating it.

You can visit our website for more tutorials, guides, case studies, and more by [clicking here](https://www.analysistutorial.com/).

Farewell.
