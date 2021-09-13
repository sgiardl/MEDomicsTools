# MEDomicsUdeS Python Coding Standard

This document presents the Python coding standard of the MEDomicsUdeS lab. It also contains cool tips, tricks and links to code efficiently in Python.

## Table of Contents

- [MEDomicsUdeS Python Coding Standard](#medomicsudes-python-coding-standard)
  * [Table of Contents](#table-of-contents)
  * [Changelog](#changelog)
  * [Contributors](#contributors)
  * [To-Do](#to-do)
  * [Standard](#standard)
    + [R000: Recommended Software](#r000--recommended-software)
    + [R001 - Style (PEP 8)](#r001---style--pep-8-)
    + [R002 - Project Repository Structure](#r002---project-repository-structure)
    + [R003: Variables, Functions and Classes Naming](#r003--variables--functions-and-classes-naming)
    + [R004 - f-strings](#r004---f-strings)
    + [R005 - Type Hinting (PEP 484)](#r005---type-hinting--pep-484-)
    + [R006 - Docstring (PEP 257 + Google Style)](#r006---docstring--pep-257---google-style-)
    + [R007 - Comments](#r007---comments)
    + [R008 - String Quotes](#r008---string-quotes)

(To update the Table of Contents, use: https://ecotrust-canada.github.io/markdown-toc/)

## Changelog

Revision | Date       | Description |
---------| -----------| ----------- |
B        | 2021-09-13 | Updated based on team's comments    |
A        | 2021-08-08 | Creation    |

## Contributors

- [Simon Giard-Leroux](https://github.com/sgiardl)

## To-Do

- Table of contents
- Paths
- More details on variable names (ie. equation variable), max chars of variable name
- Enums
- ABC
- What is pythonic? List comprehension, etc.
- Constants (all caps) vs Environment Variables
- Multiprocessing
- Check existing udes code standard & integrate contents
- if __name__ == '__main__'
- Encapsulation : protected vs private
- Class inheritance vs aggregation
- decorators : staticmethod classmethod abstractmethod

## Standard

### R000 - Recommended Software

Operating System:
- Ubuntu: https://ubuntu.com/
- Pop!OS: https://pop.system76.com/
- EndeavourOS: https://endeavouros.com/
- Arch Linux: https://archlinux.org/ (if you like to live dangerously)

Package Suite & Environment Manager:
- Anaconda: https://www.anaconda.com/products/individual

IDE:
- PyCharm Professional (free for students): https://www.jetbrains.com/shop/eform/students
- Visual Studio Code: https://code.visualstudio.com

Deep Learning Framework:
- PyTorch: https://pytorch.org/get-started/locally/

### R001 - Style - PEP 8

Follow all rules of the PEP 8 when coding in Python. The following list presents the most important aspects of PEP 8 to keep in mind when coding in Python. The detailed PEP can be found here: https://www.python.org/dev/peps/pep-0008/

- Indentation
  - Use 4 spaces per indentation level
- Maximum Line Length
  - 120 characters (not 79 characters as specified in PEP8)
- Blank Lines
  - Surround top-level function and class definitions with two blank lines
  - Method definitions inside a class are surrounded by a single blank line
  - Add a blank line at the end of each file
- Imports: 
  - Imports should be in alphabetical order.
  - Imports should usually be on separate lines.
  - Imports are always put at the top of the file, just after any module comments and docstrings, and before module globals and constants.
  - Imports should be grouped in the following order:
    - Standard library imports.
    - Related third party imports.
    - Local application/library specific imports.
    - You should put a blank line between each group of imports.

To help follow the PEP 8, you can use an IDE with a built-in PEP 8 syntax checker, such as PyCharm or Visual Studio Code.

### R002 - Project Repository Structure

Use cookiecutter-datascience when creating a new repository. This utility creates an initial folder and file structure that is well suited for data science / machine learning projects.

To use cookiecutter-datascience, follow the guide on this page: https://github.com/drivendata/cookiecutter-data-science

### R003: Variables - Functions - Classes Naming

- Adopt "snake case" OR "camel case" (but not both) when naming variables, functions, methods and attributes.
- Use descriptive names for variables.
- For functions and methods, start the name with an imperative action verb, (except boolean return value: can be a question).
- For class names, start each word with a capital letter (Pascal case).
- Class names should represent an object or an actor that can execute concrete actions.

Example:

```python
# Variable Names Snake Case
fruits_list = ['apple', 'banana', 'pineapple']
area_under_curve = 34.6

# Variable Names Camel Case
fruitsList = ['apple', 'banana', 'pineapple']
areaUnderCurve = 34.6

# Functions & Methods Snake Case
def calculate_area_under_curve(*args):

# Functions & Methods Camel Case
def calculateAreaUnderCurve(*args):

# Classes Pascal Case
class AreaCalculator:
```

### R004 - f-strings

The most useful way to manage strings in Python is the f-string, which was introduced in Python 3.6. Use f-strings whenever possible to enhance code readability. More details can be found at the following link: https://docs.python.org/3/reference/lexical_analysis.html#f-strings.

Example:

```python
builder_name = "Bob"

print(f'Hi there, my name is {builder_name}')

hourly_wage = 99.91 # Hourly wage in dollars

print(f'I work long hours! The total price for a day is {24 * hourly_wage:.2f}')
```

### R005 - Type Hinting - PEP 484

While Python is a dynamically typed language, PEP 484 was introduced to allow coders to specify argument and return value types for functions and methods. If a type is specified for a function argument, Python will not raise an exception: type hints are merely used to inform. Follow PEP 484 for all functions and methods, more details can be found at the following link: https://www.python.org/dev/peps/pep-0484/.

Example:

```python
def greeting(name: str) -> str:
    return 'Hello ' + name
```

Even for class constructors, specify return type as None. For example:

```python
class BobTheBuilder:
    def __init__(self, has_hammer: bool = True) -> None:
        self.has_hammer = has_hammer
```
### R006 - Docstring - PEP 257 - Google Style

Write a docstring at the beginning of each Python .py file containing the following information:
- File name
- Authors
- Description
- Date of last modification

Write a docstring at the beginning of each class describing the general purpose of the class.

Write a docstring at the beginning of each function or method to describe the function/method purpose, arguments type and expected values and return type and expected values. Place this docstring right after the defintion of the function/method.

Follow PEP 257: https://www.python.org/dev/peps/pep-0257/

Follow the Google docstring style: https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html

### R007 - Comments

Add a textual comment in English before each line or block of lines to help reviewers understand your train of thought or intention.

### R008 - String Quotes

Use either ' OR " for strings delimiters, but not both.
