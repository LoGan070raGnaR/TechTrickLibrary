# Python Basics

Python is a programming language that is:
- Dynamic
- Interpreted
- Object-oriented
- High-level

It is used for:
- Quick prototyping and scripting across different platforms
- Its relatively simple and easy-to-learn syntax
- Various general-purpose tasks with a mature standard library
- Being extensible, and actively used with a large community

# Why Learn Python for Hacking?

Learning Python helps you:
- Understand how scripts or POCs (proof of concept) work
- Fix and modify scripts or POCs
- Create your own scripts or POCs
- It's an easy first programming language for beginners
- Understand how applications work, making it easier to find and fix issues.

# Python2 vs Python3

- Python2 is not in development, but some people still use it
- Python2 code usually won't run in a Python3 environment
- Python3 stores strings as Unicode by default (not ASCII)
- If you're unsure how to run a script, try both or print
- If you have a choice, use Python3 (Python2 is end of life)

--------------
# Python Interpreter Basics

To access the Python interpreter, you can use the command:
```bash
man python3
```

To print a simple message using the interpreter, run:
```bash
python3 -c 'print("learn python!")'
```
This will output:
```bash
learn python!
```

To spawn a new Bash shell using the interpreter, you can use:
```bash
python3 -c 'import pty; pty.spawn("/bin/bash");'
```

**Note**: While the Python interpreter is useful for testing, it's not practical for larger scripts or more complicated programs.

# How to Run Python Scripts

To run Python scripts, you can use a text editor like Sublime Text. It automatically detects syntax errors.

Try running a script with:
```bash
python3 eg.py
```

Or, make it executable and run it:
```bash
chmod +x calc.py
./eg.py
```

You can use `"\"` to use multiple lines for decoration. For example:

```python
x = 1 + 2 \
    +3
print(x)
```

To get help from the command line, type:

```bash
python3
```
Then, for example, use help followed by function name:

```bash
help(print)
```

or

```bash
dir(print)
```

Include the following code for better script organization:

```python
if __name__ == "__main__":
```

`__name__` and `__main__` are special keywords in Python. Before executing the script, Python reads the source file and defines a few standard variables.

The `if __name__ == "__main__":` statement is crucial in Python scripts for the following reasons:

**Script Execution Control:**
    Ensures that code within the block only runs when the script is the main program, not when it's imported as a module.

**Module Reusability:**
    Allows the script to be reusable as a module without executing certain code on import.

**Script Organization:**
    Promotes cleaner and more organized script structure, with the main logic inside the block.

**Testing:**
    Facilitates easier testing of individual components by preventing unintended execution of main code during imports.

**Avoiding Unintended Execution:**
    Prevents unintended consequences or side effects by controlling when certain code is executed.

In summary, using `if __name__ == "__main__":` enhances code organization, reusability, and maintainability, allowing scripts to function both as modules and independently executable programs.

-----------
# Important Python Functions and Type Handling

## Checking Variable Type
To determine the type of a variable, you can use the `type` function. For example:
```python
name = "eg"
print(type(name))
```

This will output:
```python
<class 'str'>
```

Here, the `type` function helps identify that the variable `name` is of type string (`str`).

## Type Casting in Python

### Implicit Type Casting
Python supports implicit type casting. For instance:
```python
length = 4
length = "4"
```

Here, the variable `length` is initially an integer but is later reassigned as a string without explicitly stating its data type.

### Explicit Type Casting
You can also explicitly cast a variable to a specific data type. For example:
```python
length = int("4")
```

In this case, the `int` function is used to explicitly convert the string "4" to an integer.

## Python Data Types

Python supports various data types, including:

- **List:**
  ```python
  my_list = [1, 2, 3]
  ```
  
- **Tuple:**
  ```python
  my_tuple = (1, 'two', 3.0)
  ```

- **Dictionary:**
  ```python
  my_dict = {'key': 'value', 'num': 42}
  ```
  
- **Boolean:**
  ```python
  is_true = True
  ```

- **Range:**
  ```python
  my_range = range(5)
  ```

- **Bytes:**
  ```python
  my_bytes = b'hello'
  ```

Each data type serves a specific purpose, and Python's flexibility allows for dynamic typing, making it convenient for various programming scenarios.

In summary, Python provides functions like `type` for checking variable types and supports both implicit and explicit type casting. The language accommodates a range of data types, including lists, tuples, dictionaries, booleans, ranges, and bytes, offering versatility in handling different kinds of information.

------------
# Python Number Types and Built-in Functions

## Number Types
In Python, there are several numeric types:

- **int:**
  Represents integer values (e.g., 5, -10).

- **float:**
  Represents floating-point values (e.g., 3.14, -0.5).

- **complex:**
  Represents complex numbers (e.g., 2 + 3j).

### Hexadecimal and Octal Notation
When using hex or octal notation, the type displayed is still 'int,' and the actual value is provided in decimal form. It's important not to confuse the hexadecimal number system with hexadecimal values like shellcode. In Python, defining shell code doesn't necessarily mean treating it as a number.

```python
h1_hex = 0xa
o1_octal = 0o10
print(type(h1_hex)) 
print(type(o1_octal))
```

This code demonstrates defining variables `h1_hex` and `o1_octal` using hex and octal notation, respectively. Despite the notation, both variables are of type `int`.

# Python Built-in Functions

**abs()**

The `abs()` function returns the absolute value of a number, ensuring a positive result.

**round()**

The `round()` function rounds a floating-point number to the nearest integer.

**bin()**

The `bin()` function converts an integer to its binary representation.

**hex()**

The `hex()` function converts an integer to its hexadecimal representation.

These functions provide essential operations for working with numeric data in Python.

In summary, Python supports various numeric types, including int, float, and complex. When using hex or octal notation, the type remains 'int.' Additionally, Python offers built-in functions like abs(), round(), bin(), and hex() for common numeric operations.

-------------
# String Formatting in Python

String formatting in Python is a crucial aspect that allows for the manipulation, modification, and presentation of textual data in various ways.

## String Basics

- **Single-Line String:**
  Enclosed within double (`" "`) or single (`' '`) quotes.

- **Multiline String:**
  Enclosed within triple double (`"""`) or single (`'''`) quotes.

- **Escaping Quotes:**
  Use ` \ ` to escape quotes within a string.

- **Printing Special Characters or Hexadecimal Numbers:**
  To print characters like ` \ ` or hexadecimal numbers, use ` \ ` before them.
  ```python
  print("\\ \x41\x42\x43")
  ```
- **Repeating Characters:**
  To print a character multiple times, use the repetition operator `*`.
  ```python
  print("a" * 10)
  ```
  
## Built-in String Functions

- **len():**
  Returns the length of a string.
  ```python
  len("Hello, World!")
  ```
- **in:**
Checks if a certain item is present in the string.
  ```python
  string7 = "I'm a string"
  print("string" in string7)
  ```
  
- **startswith():**
Checks if the string starts with a specific substring.
  ```python
  print(string7.startswith("I"))
  ```
- **index():**
Returns the index of the first occurrence of a substring.
  ```python
  print(string7.index("string"))
  ```
- **upper() and lower():**
  Convert the string to uppercase or lowercase.

- **strip():**
  Removes leading and trailing whitespaces from a string.
  ```python
  messy_string = " Messy String! "
  print(messy_string.strip())
  ```
  **Note:**
  If used as a password or for comparisons in a brute force attack, spaces may cause issues.

  
- **replace(), split():**
  Replace specified substrings or split a string into a list.

## Unicode Representation

In Python 3, all strings are represented in Unicode.

```python
string7 = "I'm a string"
print(string7)
print(string7.encode())
print(string7.encode("utf-8"))
```

## Justification and Padding

- **rjust() and ljust():**
  Right-justify or left-justify a string by padding spaces.

## Concatenation and Formatting

- **str() and Concatenation:**
  Convert non-string data to a string using `str()`. Use `+` to concatenate strings.
  ```python
  print("string7 is " + str(len(string7)) + " characters long")
  ```
- **format():**
  A versatile method for string formatting.
  ```python
  print("string7 is {} characters long".format(len(string7)))
  ```
  
- **f-strings:**
  Introduced in Python 3.6, an elegant way for string formatting.
  ```python
  length = len(string7)
  print(f"string7 is {length} characters long")
  ```
  
- **Formatting Options:**
  Specify formatting options using {} placeholders.
  ```python
  print("string7 is {:.2f} characters long".format(len(string7)))
  ```
  
# Key Takeaway

Python offers a variety of tools for manipulating, modifying, and searching within strings. These functionalities are valuable when writing hacking scripts, scraping data, and normalizing information for repetitive tasks.

-----------
# Tuples and Lists in Python

## Tuples
Tuples allow the storage of multiple items in a single variable. They are immutable and cannot be changed. Tuples are particularly useful when dealing with fixed data.

- **Repeating Items:**
  To repeat the same item multiple times, use the repetition operator.
  ```python
  tuple_repeat = ('Combine!',) * 4
  ```

- **Mixed Types:**
  Tuples can contain elements of multiple types.
  ```python
  tuple_mixed = ("A", 1, ("A", 1))
  ```

## Lists

Lists, like tuples, can store multiple items but are mutable—meaning they can be changed. The primary difference between tuples and lists lies in their mutability.

- **Empty List:**
    Both `[]` and `list()` represent an empty list.

- **Nested Structures:**
    Lists can include tuples, but when printed, they will appear as lists.
  ```python
  list_a = [1, "a", ("a", "b"), [], list(), [1, 2, 3], list("list"), tuple("tuple"), 7]
  ```

- **List Operations:**
  Various useful functions for lists:

  - **del:** Deletes an item at a specific index.
    ```python
    del list_a[1]
    ```
  - **insert():** Inserts an item at a specific index.
    ```python
    list_a.insert(0, "A")
    ```
  - **append():** Appends an item at the end of the list.
    ```python
    list_a.append("G")
    ```
  - **max():** Returns the maximum value in the list.
    ```python
    print(max(list_a))
    ```
  - **min():** Returns the minimum value in the list.
    ```python
    print(min(list_a))
    ```
  - **index():** Returns the index of the first occurrence of an item.
    ```python
    print(list_a.index("7"))
    ```
  - **reverse():** Reverses the order of items.
    ```python
    list_a.reverse()
    ```
  - **count():** Returns the number of occurrences of an item.
    ```python
    print(list_a.count("a"))
    ```
  - **pop():** Removes and returns the last item.
    ```python
    print(list_a.pop())
    ```
  - **extend():** Extends the list by appending elements from another list.
    ```python
    list_b = [1, 2, 7, 4, 8, 6]
    list_a.extend(list_b)
    ```
  - **clear():** Removes all items from the list.
    ```python
    list_a.clear()
    ```
  - **sort():** Sorts the list in ascending order. Use `reverse=True` for descending order.
    ```python
    list_b.sort()
    ```
- **Note:**
  
  - Copying a list using `list_b = list_a` creates a reference, changing one reflects in the other.
    ```python
    list_c = list_b
    list_c[2] = "x"
    ```
  - To avoid changes in the original list, use `copy()`.
    ```python
    list_d = list_b.copy()
    list_d[2] = "a"
    ```
  - **Map Function:**
    The `map()` function applies a specified function to all items in the list.
    ```python
    list_e = [1, 4, 8, 7, 2, "9"]
    list_f = list(map(float, list_b))
    ```
    
These features in Python provide flexibility and convenience for managing data structures and performing various operations.

------------
# Dictionary in Python

A dictionary in Python is a collection of key-value pairs, allowing for efficient and quick lookups.

```python
dict_a = {"a": 1, "b": 2, "c": 3}
print(dict_a["a"])
```

Unlike tuples and lists, dictionaries do not use indices to access items; instead, they use keys for retrieval.

## Useful Dictionary Functions

- **get():**
  The get() function retrieves the value associated with a given key.
  ```python
  print(dict_a.get("a"))
  ```
- **keys():**
  The keys() function returns a list of all keys in the dictionary.
  ```python
  print(dict_a.keys())
  ```
- **values():**
  The values() function returns a list of all values in the dictionary.
  ```python
  print(dict_a.values())
  ```
- **items():**
  The items() function returns a list of key-value pairs in the dictionary.
  ```python
  print(dict_a.items())
  ```
- **Note:** Key and value pairs in a dictionary must be unique; duplicates are not allowed.

## Updating and Modifying Dictionaries

- **Updating Values:**
  To update the value associated with a key:
  ```python
  dict_a["a"] = 0
  ```
- **update():**
  The update() function updates the dictionary with key-value pairs from another dictionary.
  ```python
  dict_a.update({"a": 1})
  ```
- **pop():**
  The pop() function removes the key-value pair associated with a specified key.
  ```python
  dict_a.pop("c")
  ```
- **del:**
  The del keyword can be used to delete a key-value pair.
  ```python
  del dict_a["b"]
  ```
## Nested Dictionaries

Dictionaries can be nested, allowing for the creation of more complex structures.
```python
dict_a["b"] = {"a": 1, "b": 2}
print(dict_a)
 ```

## Creating Empty Dictionaries

If you anticipate using a dictionary in your program but are unsure of its contents initially, you can create an empty dictionary.
```python
dict_b = {}
# or
dict_c = dict()
```

This is particularly useful when iterating over a structure and needing to look up data based on some defined key.

----------
# Sets in Python

Sets in Python are unordered collections that do not allow duplicates, making them efficient for membership tests and eliminating redundancy.

```python
set_a = {"a", 0, True}
# or using set()
set_b = set(("b", 1, False))
```
Because sets are unordered, they do not support indexing.

## Useful Set Functions

- **add():**
  The `add()` function adds an element to the set.
  ```python
  set_a.add("d")
  ```
- **update():**
  The `update()` function adds elements from another set or iterable to the set.
  ```python
  set_a.update(set_b)
  print(set_a)
  ```
  We can also update sets with different iterables, like lists.
  ```python
  list_a = ["a", "b", "c"]
  set_c = {4, 5, 6}
  set_c.update(list_a)
  ```
## Sets as Mathematical Constructs

Sets in Python reflect mathematical constructs and support operations like union.

- **union():**
  The `union()` function combines two sets into a new set.
  ```python
  set_d = {4, 5, 6}
  set_e = set_c.union(set_d)
  ```
  
- **remove():**
  The `remove()` function removes a specified element from the set.
  ```python
  set_d.remove(4)
  ```
To avoid errors when attempting to remove an item not present in the set or when not concerned about item presence, use `discard()`.

- **discard():**
  The `discard()` function removes a specified element if present.
  ```python
  set_d.discard(4)
  ```
- **pop():**
  The `pop()` function removes and returns a random item from the set. However, since sets are unordered, it may yield unexpected results.
  ```python
  set_d.pop()
  ```
  
Use `pop()` when the order of data does not matter.

Sets in Python offer a powerful and efficient way to handle collections, especially when order and duplicates are not crucial considerations.

------------
# Conditionals and Ternary Operators in Python

Conditionals in Python, including `if`, `elif`, and `else`, are fundamental structures that allow for decision-making in code execution.

```python
# Basic Conditional Structure
if condition:
    # Code block to execute when the condition is True
    pass
elif another_condition:
    # Code block to execute when the first condition is False and this condition is True
    pass
else:
    # Code block to execute when all previous conditions are False
    pass
```

## Ternary Operators

Ternary operators provide a concise way to express conditional statements in a single line. They are particularly useful when the actions are simple and can be expressed in a single line of code.

```python
# Inline Ternary Example
print("1 >= 1") if 1 >= 1 else print("not possible")
```

### Complicated Ternaries

- **Example 1**:
```python
x = 10

result = "Condition 1" if x == 0 else "Condition 2" if x == 1 else "Condition 3" if x == 2 else "Condition 4" if x == 3 else "Condition 5"

print(result)
```

**To understand:**
```python
# Understanding Ternaries with Line Continuation
x = 10

result = "Condition 1" if x == 0 else \
         "Condition 2" if x == 1 else \
         "Condition 3" if x == 2 else \
         "Condition 4" if x == 3 else \
         "Condition 5"

print(result)
```

- **Example 2**:
```python
x = 10

print("Condition 1") if x == 0 else print("Condition 2") if x == 1 else print("Condition 3") if x == 2 else print("Condition 4") if x == 3 else print("Condition 5")
```
**To understand:**
```python
x = 10

print("Condition 1") if x == 0 else \
      print("Condition 2") if x == 1 else \
      print("Condition 3") if x == 2 else \
      print("Condition 4") if x == 3 else \
      print("Condition 5")
```

Ternary operators are a powerful tool for simplifying conditional expressions, but their usage should be balanced with readability to ensure the code remains understandable.

Understanding and using ternary operators effectively can lead to more concise and expressive code in specific scenarios.

---------------
# Loops in Python

Loops in Python, including `while` and `for`, are essential for iterating through sequences and performing actions on each element.

## while Loop

The `while` loop repeats a block of code as long as a specified condition is true.

```python
# Example of a while loop
while condition:
    # Code block to execute while the condition is True
    pass
```

## for Loop

The `for` loop is used to iterate over a sequence (such as a list, tuple, or string) or other iterable objects.

```python
# Example of a for loop
for variable in iterable:
    # Code block to execute for each iteration
    pass
```

### Useful Control Statements

- **break:**
  The `break` statement is used to exit a loop prematurely based on a specified condition.

  ```python
  # Example using break
  for i in range(5):
      print(i)
      if i == 2:
          break
      print(i)
  ```
  
- **continue:**
  The `continue` statement skips the rest of the code inside a loop for the current iteration and moves to the next one.

  ```python
  # Example using continue
  for i in range(5):
      print(i)
      if i == 2:
          continue
      print(i)
  ```

- **pass:**
  The `pass` statement is a no-operation statement, used when a statement is syntactically required but no action is desired.

  ```python
  # Example using pass
  for i in range(5):
      print(i)
      if i == 2:
          pass
      print(i)
  ```
  
### Note on Iteration

In Python, you can loop over any iterable object. Examples include iterating over each character in a string or iterating over key-value pairs in a dictionary.

```python
# Loop over each character in a string
for c in "string":
    print(c)
```

```python
# Iterate over dictionary items
for key, value in {"a": 1, "b": 2, "c": 3}.items():
    print(key, value)
```
- Here, instead of extracting each value based on its key, we can iterate over each item in the sequence.

Loops are invaluable when you want to iterate over data and perform a specific function on each element in the iterable. They offer a powerful mechanism for automating repetitive tasks and processing data efficiently.

------------
# Reading and Writing Files in Python

Reading and writing files in Python is a fundamental operation that allows manipulation of file content for various purposes. Let's explore the essential concepts and operations involved.

## Opening a File

To work with a file, we first need to open it using the `open()` function. The default mode is "`r`" (read).

```python
# Example of opening a file
f = open('top-100.txt')
print(f)
```

### Modes of Operation
When working with files, different modes can be specified to determine the type of operation intended:

- `a` (append)
- `w` (write)
- Create mode

We can also specify whether a file is text or binary.

```python
# Example specifying mode and text
f = open('top-100.txt', 'rt')
print(f)
```

### Reading Operations

- **read():**
  To read the entire content of a file, use the `read()` method.
  ```python
  # Example using read()
  f = open('top-100.txt', 'rt')
  print(f.read())
  ```
  
- **readlines():**
  If we want to perform actions on each line of the file, we use `readlines()`.
  ```python
  # Example using readlines()
  f = open('top-100.txt', 'rt')
  print(f.readlines())
  ```
  
- **seek():**
  To reset the file position back to the start, use `seek()`.
  ```python
  # Example using seek()
  f.seek(0)
  print(f.readlines())
  ```
  
### Iterating Over Lines

We can use file objects as iterators to iterate over each line in the file.

```python
# Example iterating over lines
f.seek(0)
for line in f:
    print(line.strip())
```

### Closing the File

Once finished with the file, it's essential to close it using the `close()` method.

```python
# Example closing the file
f.close()
```

### Writing Operations

- **Creating a File:**
  To create a file and write content to it:

  ```python
  # Example creating a file
  f = open("test.txt", "w")
  f.write("test line!")
  f.close()
  ```
  
- **Appending to a File:**
  To append to the end of a file:

  ```python
  # Example appending to a file
  f = open("test.txt", "a")
  f.write("test line!")
  f.close()
  ```
  
### File Handling Functions

Some useful file handle functions include:

- `name`
- `closed`
- `mode`

```python
# Example file handling functions
print(f.name)
print(f.closed)
print(f.mode)
```

### Note on Efficiency

For larger files, using a file object as an iterator is more efficient.
```python
# Example using a file object as an iterator
with open('rockyou.txt', encoding='latin-1') as f:
    for line in f:
        pass
```

Keep in mind the file's encoding, as specifying it can prevent decoding errors (e.g., `UnicodeDecodeError`)

--------------
# User Input and Exception Handling in Python

## User Input

User input is a crucial aspect of interactive programs. Python provides the `input()` function to receive user input.

```python
# Example of user input
test = input("Enter the IP:")
print(test)
```
A more interactive example using a `while` loop:

```python
# Example of continuous user input
while True:
    test = input("Enter the IP: ")
    print(f">>> {test}")
    if test == "exit":
        break
    else:
        print("exploiting...")
```

## Exceptions and Error Handling

Exceptions are errors that occur during execution and can disrupt normal program flow. Python offers a `try`-`except` block for handling exceptions.

```python
# Example of handling file not found exception
try:
    f = open("adaada.txt")
except FileNotFoundError:
    print("The file doesn't exist!")
except Exception as e:
    print(e)
finally:
    print("Always print this message!")
```

Here, the `try` block tests the specified code, the `except` block handles errors, and the `finally` block executes regardless of the try-except results.

### Standard Exceptions

Common exceptions include arithmetic errors, syntax errors, and indentation errors.

```python
# Example of raising exceptions with assertions
n = 100
if n == 0:
    raise Exception("n can't be 0!")
if type(n) is not int:
    raise Exception("n must be an int!")
print(1/n)
```

### Assertions

Assertions are sanity checks similar to raising exceptions. If the assertion expression fails, an exception is raised, and the program stops executing.

```python
# Example of using assertions
n = 1
assert(n != 0)
print(1/n)
```

####  Difference between Exceptions and Assertions:

- **Exceptions:** Used for handling runtime errors and exceptional conditions that may occur during execution. Typically handled using try-except blocks.

- **Assertions:** Used for sanity checks to ensure that certain conditions hold true at specific points in the code. If the condition is false, an AssertionError is raised, and the program stops executing.

### Note: 
`Exceptions` and `assertions` are valuable Python constructs for error handling and data verification, ensuring a more robust and reliable program.

---------------
# List Comprehensions in Python

List comprehensions provide a concise way to create lists based on some iterables, offering a shorter syntax compared to traditional loops.

### Syntax:
```python
[expression for item in iterable if condition]
```

### Examples:
```python
# Basic List Comprehensions
list_a = ["a", "b", "c"]
list_b = [x for x in list_a]
list_c = [x for x in list_a if x == "a"]
list_d = [x for x in range(5)]
list_e = [hex(x) for x in range(5)]
list_f = [hex(x) if x > 0 else "X" for x in range(5)]
list_g = [x * x for x in range(5)]
list_h = [x for x in range(5) if x == 0 or x == 1]

# Nested List Comprehensions
list_i = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
list_j = [y for x in list_i for y in x]
list_k = [y for x in list_i for y in list_e]
print(list_j, list_k)

# Set Comprehension
set_a = {x + x for x in range(5)}

# String Comprehension
list_l = [c for c in "string"]

# Using Join Method with List Comprehension
string_result = "-".join([c for c in "string"])

# Alternative way without List Comprehension
list_l = []
for c in "string":
  list_l.append(c)
string_result_alternative = "-".join(list_l)

print(string_result)
print(string_result_alternative)
```

#### Note:
When working with hacking scripts or proof-of-concepts (POCs), list comprehensions are often used in conjunction with the `join` method to efficiently combine items in an iterable into a single string.

These concise expressions enhance code readability and are widely employed in Python for creating and manipulating lists.

-------------
# Functions and Code Reuse in Python

## Function Basics

Functions in Python allow for organized and reusable code. They can perform various tasks, and here are some fundamental concepts:

### Printing from Functions

```python
# Example of a function printing a message
def function_a():
    print("Hello from function_a!")
```

### Returning Values

Functions can also return values, useful for further utilization:

```python
# Example of a function returning a value
def function_b():
    return "Hello from function_b!"

# Using the returned value
return_from_function_b = function_b()
print(return_from_function_b)
```

### Accepting and Handling Parameters

Functions can receive parameters, making them more versatile:

```python
# Example of a function with parameters
def function_c(s1, s2):
    print("{} {}".format(s1, s2))

# Calling the function with arguments
function_c("parameter1", "parameter2")

# Using keyword arguments to change the parameter order
function_c(s1="parameter1", s2="parameter2")
```

### Default Arguments and Variable Parameters

Default arguments and variable parameters enhance function flexibility:

```python
# Example of a function with default argument
def function_d(s1="default"):
    print("{}".format(s1))

# Using the function with and without specifying the argument
function_d()
function_d("anything")

# Function with variable arguments using asterisks
def function_e(s1, *more):
    print("{} {}".format(s1, " ".join([s for s in more])))

# Using the function with multiple arguments
function_e("parameter1", "a", "b", "etc")
```

### Handling Dictionary of Arguments

Functions can also receive a dictionary of arguments:

```python
# Example of a function with a dictionary of arguments
def function_f(**sdict):
    for i in sdict:
        print(i, sdict[i])

# Using the function with a dictionary
function_f(a="1", b="2", c="3")
```

### Accepting Any Data Type

Functions in Python can handle different data types:

```python
# Example of a function handling various data types
def function_g(s, i, f, l):
    print(type(s))
    print(type(i))
    print(type(f))
    print(type(l))

function_g("string", 1, 1.0, ["l", "i", "s", "t"])
```

### Global and Local Variables

Understanding global and local variable scope in functions:

```python
# Example of global and local variables
v = 100
print(v)

# Function with a local variable
def function_h():
    v = 5
    v += 1
    print(v)

function_h()
print(v)

# Modifying a global variable inside a function
v = 100
print(v)

def function_h():
    global v
    v += 1
    print(v)

function_h()
print(v)
```

### Calling Functions Inside Functions

Functions can call other functions, creating modular and reusable code:

```python
# Example of calling functions inside other functions
def function_i():
    print("Hello from function_i")

def function_j():
    function_i()
    print("Hello from function_j")

function_j()
```

### Recursion in Functions

Functions can call themselves, known as recursion. It is crucial to include a termination condition:

```python
# Example of recursion (not recommended)
def function_k(x):
    print(x)
    function_k(x - 1)

# Improved recursive example with a termination condition
def function_k(x):
    print(x)
    if x > 0:
        function_k(x - 1)
```

Recursion, while powerful, should be used carefully, ensuring a proper termination condition. In many cases, iterative solutions may be preferred for simplicity and efficiency.

```python
# Equivalent iterative solution without recursion
def function_k(x):
    while x >= 0:
        print(x)
        x -= 1

# Calling the iterative function
function_k(5)
```

#### Note:
It's important to note that recursion is not always necessary, and for cases where it may lead to complex or inefficient solutions, an iterative approach can be a suitable alternative.

----------------
# Lambdas in Python

Lambdas, also known as anonymous functions, are concise, one-line functions in Python. They lack a formal name and can take any number of arguments but are restricted to a single expression. Lambdas are particularly useful for short, simple function expressions.

```python
# Example of a lambda adding 4 to a number
add_4 = lambda x: x + 4
print(add_4(4))

# Example of a lambda adding two numbers
add = lambda x, y: x + y
print(add(10, 7))
```

In the first example, `add_4` is a lambda function that adds 4 to its input. In the second example, `add` takes two arguments and returns their sum. Note that lambdas cannot extend across multiple lines.

If you find lambdas confusing, you can express the same functionality using regular named functions:

```python
# Equivalent function for adding two numbers
def addf(x, y):
    return x + y

print(addf(10, 7))
```

Lambdas can also be used directly within expressions:

```python
# Using a lambda directly in an expression
print((lambda x, y: x + y)(10, 7))
```

Here, the lambda function is defined and evaluated in a single line.

## Practical Uses in Hacking Scripts:

### Checking Even or Odd:

```python
is_even = lambda x: x % 2 == 0
print(is_even(2))
print(is_even(3))
```

### Breaking a String into Blocks:

```python
blocks = lambda x, y: [x[i: i+y] for i in range(0, len(x), y)]
print(blocks("string", 2))
```

### Using Lambda Instead of Map:

```python
to_ord = lambda x: [ord(i) for i in x]
print(to_ord("ABCD"))
```

In this example, the `ord` function returns the integer representation of each character, and the lambda provides a concise way to achieve this in a single line. For those less comfortable with lambdas, equivalent functions with regular loops can be created.

```python
# Equivalent function using a regular loop
def to_ord(x):
    ret = []
    for i in x:
        ret.append(ord(i))
    return ret

print(to_ord("ABCD"))
```
Depending on complexity, lambdas may be harder to understand, maintain, or modify, making the use of regular loops a more suitable option for those less comfortable with lambdas.

--------------
# Python Package Manager: Pip and Modules

## Python Package Manager: Overview

The `Python Package Manager (pip)` is a vital tool for managing external Python `packages`, which are collections of files containing reusable code modules. These `modules` offer predefined functions that can be utilized to extend the capabilities of your Python programs. Unlike built-in Python libraries, packages are not part of the standard library but can be easily integrated into your projects.


### Modules: Building Blocks of Packages

`Modules` are prewritten Python functions grouped together in a library, serving as the building blocks of packages. By importing these modules, you can incorporate existing functionality into your scripts, enhancing efficiency and reducing the need for extensive coding.

```python
# Example of importing a module
import random
random_number = random.randint(1, 10)
```

### Leveraging Python Packages for Hacking Tasks

Python packages offer a wide range of functionalities, making them valuable for various hacking tasks. Some applications include:

- Making HTTP requests to websites
- Generating random numbers
- Parsing HTML for web scraping

These capabilities prove beneficial for tasks such as web scraping or implementing brute-force attacks.

### Using Pip: Installation and Management

To access and manage Python packages, Python employs `pip`, a package manager accessible through the command line. Similar tools exist for other programming languages, such as `npm` for JavaScript, `jem` for Ruby, and `NuGet` for .NET.

```bash
# Installing a Python package using pip
pip install pwntools
```

### Version Management with Pip

Pip allows for precise control over package versions, ensuring compatibility with specific script requirements.

```bash
# Installing a specific version of a package
pip install pwntools==4.5.1
```

### Requirements.txt: Simplifying Package Management

Project dependencies, including specific package versions, can be defined in a `requirements.txt` file. This file facilitates the installation of all required modules with a single command.

```subl
# Example of a requirements.txt file
# requirements.txt
pwntools==4.5.0
# Some other modules
```

```bash
# Installing modules from a requirements.txt file
pip install -r requirements.txt
```

### Troubleshooting Imports and Dependencies

In case of import errors or missing dependencies when running a script, check for specified requirements or try manually importing the modules. Some scripts may come with a bundled requirements.txt file, ensuring seamless installation of required packages. Properly managing dependencies enhances script portability and execution reliability.

------------------
# Python Virtual Environments

### Introduction to Virtual Environments

When working on Python projects, managing dependencies becomes crucial. Situations may arise where different scripts require specific package versions, making constant installation and uninstallation tedious. The solution to this problem lies in **Python Virtual Environments**.

### Setting Up a Virtual Environment

To utilize virtual environments, you first need to install the `virtualenv` package.

```bash
# Installing virtualenv
pip install virtualenv
```

Create a new directory for your project and navigate into it:

```bash
# Creating a new directory
mkdir virtual-demo
cd virtual-demo
```

Initiate a new virtual environment within this directory:

```bash
# Starting a new virtual environment
python -m venv env
```

Activate the virtual environment:

```bash
# Activating the virtual environment
source env/bin/activate
```

By default, a virtual environment does not include any existing packages from the host system.

### Exploring the Virtual Environment

Inspect the `env` directory to see the files necessary for interacting with the Python environment, including libraries and C headers needed for compilation.

```bash
# Viewing the virtual environment contents
ls -laR | less
```

Utilize the `which` command to identify the Python binary being used within the virtual environment:

```bash
# Checking the Python binary path in the virtual environment
which python3
```

In a virtual environment, it will be located at `~/virtual-demo/env/bin/python3`, while on the host system, it is typically at `/usr/bin/python3`.

To view installed utilities with version numbers:

```bash
# Viewing installed utilities with version numbers
pip freeze | less
```

### Benefits of Virtual Environments

One of the significant advantages of virtual environments is the ability to run multiple isolated environments simultaneously. Each environment can contain different modules and associated versions, proving valuable for testing and running scripts with specific dependencies.

### Deactivating the Virtual Environment

When you're done working in a virtual environment, deactivate it:

```bash
# Deactivating the virtual environment
deactivate
```

To verify if the environment is active or not:

```bash
# Checking the Python binary path after deactivation
which python3
```

This approach ensures a clean and modular setup for Python projects, enhancing flexibility and avoiding conflicts between package versions.

-------------------
# Introduction to sys Module

### Overview:
The `sys` module in Python serves as a powerful tool, providing various functions and variables related to the Python runtime environment. It facilitates interaction with command-line arguments, standard input/output streams, and more.

### Accessing Python Runtime Information:
To utilize the functionalities of `sys`, it must first be imported.

```python
import sys
print(sys.version)
print(sys.executable)
print(sys.platform)
```

These commands provide information about the Python version, executable path, and platform.

### Interacting with stdin, stdout, and stderr:

The `sys` module allows interaction with standard input, output, and error streams. This can be leveraged to read from stdin and write to stdout directly.

```python
for line in sys.stdin:
    if line.strip() == "exit":
        break
    sys.stdout.write(">> {}".format(line))
```

### Low-Level Functions:

`sys` provides access to low-level functions, enabling operations that may be challenging with standard Python functions. For instance, forcing Python to flush a buffer:

```python
for i in range(1, 5):
    sys.stdout.write(str(i))
    sys.stdout.flush()
```

This ensures that data is immediately written to the terminal.

#### Progress Bar Example:

Creating a progress bar using `sys` for a visual representation of a task's progress:

```python
import time

for i in range(0, 51):
    time.sleep(0.1)
    sys.stdout.write("{} [{}{}]\r".format(i, "#"*i, "."*(50-i)))
    sys.stdout.flush()
sys.stdout.write("\n")
```

### Accessing Command-Line Arguments:

`sys.argv` allows access to command-line arguments passed to the script.

```python
print(sys.argv)
```

When running the script with arguments:
```bash
python3 sys-demo.py 1 2 3
```

This would print:

```subl
['sys-demo.py', '1', '2', '3']
```

### Handling Exit Codes:

The `sys` module enables scripts to exit with specific codes, indicating success or failure.

```python
print(sys.argv)
if len(sys.argv) != 3:
    print("[X] To run {} enter a username and password".format(sys.argv[0]))
    sys.exit(5)

username = sys.argv[1]
password = sys.argv[2]
print("{} {}".format(username, password))

sys.exit(0)
```

### Additional Features:

#### Accessing Module Search Paths:
```python
print(sys.path)
```

#### Accessing Available Modules:
```python
print(sys.modules)
```

### Utilizing Exit Codes:

The exit code can be examined using:
```bash
echo $?
```

### Official Documentation:

Explore the official [documentation](https://docs.python.org/3/library/sys.html) for comprehensive details on using the `sys` library.

Always refer to official documentation when unsure about a function or module's capabilities, ensuring accurate and reliable information.

------------
# Introduction to requests Module

### Overview:
The `requests` library is a powerful tool for interfacing with web applications, facilitating the sending of various HTTP requests (GET, HEAD, POST, OPTIONS) and parsing response times and data. This module simplifies the process of making and processing HTTP requests in Python.

### Installation:
To begin using the `requests` library, it needs to be installed using the following command:
```bash
pip install requests
```

### Basic Usage:
For effective demonstration, the script will leverage http://httpbin.org, a service reflecting data back to users, allowing verification of request functionality.

#### Example Script (requests-demo.py):
```python
import requests

x = requests.get("http://httpbin.org/get")
print(x.headers)
print(x.headers['Server'])
print(x.status_code)

if x.status_code == 200:
    print("Success!")
elif x.status_code == 404:
    print("Not found!")

print(x.elapsed)
print(x.cookies)
print(x.content)  # Response in bytes
print(x.text)     # Response in unicode
```

#### Understanding Responses:

- **Status Codes:** The HTTP status code, accessible through `x.status_code`, provides information about the success or failure of the request.
- **Headers:** Response headers, such as server details, are accessible via `x.headers`.
- **Content:** The response content is available in both bytes (`x.content`) and Unicode (`x.text`).
- **Elapsed Time:** `x.elapsed` reveals the time taken for the request.

### Sending Requests with Parameters:

Parameters can be included in the request URL, either as part of the URL itself or as a separate dictionary.

```python
x = requests.get("http://httpbin.org/get", params={'id': '1'})
print(x.url)
x = requests.get("http://httpbin.org/get?id=2")
print(x.url)
```

### Handling Additional Information:

Additional information, such as headers, can be specified in the request.

```python
x = requests.get("http://httpbin.org/get", params={'id': '3'}, headers={'Accept': 'application/json', 'test_header': 'test'})
print(x.text)
```

### Other HTTP Verbs:

Various HTTP verbs like DELETE, HEAD, or POST can be used with the `requests` module.

```python
x = requests.delete("http://httpbin.org/delete")
x = requests.post("http://httpbin.org/post", data={'a': 1, 'b': 2, 'c': 3})
```

### File Uploads:

Uploading files in multipart-encoded format is supported.
```bash
wget https://www.google.com/images/branding/googlelogo/1x/googlelogo_light_color_272x92dp.png -O google.png 
```

```python
files = {'file': open('google.png', 'rb')}
x = requests.post('http://httpbin.org/post', files=files)
print(x.text)
```
### Handling Basic Authentication:

Basic authentication can be performed using the `auth` parameter.
```python
x = requests.get("http://httpbin.org/get", auth=('username', 'password'))
print(x.text)
```

To see this:
```bash
echo -ne dXNlcm5hbWU6cGFzc3dvcmQ= | base64 -d
```

### SSL Certificate Verification:

Requests can handle SSL certificate verification, and warnings can be ignored if needed.

```python
x = requests.get("https://expired.badssl.com", verify=False)
```
This will warn us about a potential man-in-the-middle attack (`InsecureRequestWarning`). Even though we get the warning, we still have control over our actions.

### Handling Redirection:

Control over redirection can be specified with the `allow_redirects` parameter.

By default, `requests` will follow redirects. We can control this behavior.
```python
x = requests.get("http://github.com", allow_redirects=False)
```

#### Use `curl` to see the redirection:
```bash
curl -I http://github.com
```

#### Output:
```subl
HTTP/1.1 301 Moved Permanently
Content-Length: 0
Location: https://github.com/
```
Here we can see a 301 redirect to the HTTPS version of the site.

### Timeouts:

A timeout for waiting for the response can be set.

```python
x = requests.get("http://httpbin.org/get", timeout=0.01)
print(x.content)
```

### Session Management:

Sessions can be used to persist data across requests.

```python
x = requests.Session()
x.cookies.update({"a": "b"})
print(x.get("http://httpbin.org/cookies").text)
print(x.get("http://httpbin.org/cookies").text)
```

### Handling Different Response Formats:

Responses can be processed in various formats, such as JSON or images.

```python
print(x.json())
x = requests.get("https://www.google.com/images/branding/googlelogo/1x/googlelogo_light_color_272x92dp.png")
with open("google.png", 'wb') as f:
  f.write(x.content)
```

#### Note:

For further capabilities and details, always refer to the official documentation of the module: [requests - PyPI](https://pypi.org/project/requests/)

--------------
# Introduction to pwntools

## Overview:
`pwntools` stands out as a comprehensive and indispensable CTF framework and exploit development library in the realm of hacking scripts. Renowned for its robust capabilities, this Python module offers a plethora of features essential for the penetration tester and exploit developer. From interacting with processes, both local and remote, to packing and unpacking data, working with various contexts and architectures, creating assembly, debugging, and beyond, `pwntools` streamlines the process of developing sophisticated hacking scripts.

## Installation:
To harness the power of `pwntools`, initiate the installation process using the following command:
```bash
pip install pwntools
```

## Example Usages:

1. **Cyclic Pattern for Buffer Overflow:**
   - Generate a cyclic pattern of a specified size and determine the offset for a given substring.
   ```python
   from pwn import *
   print(cyclic(50))
   print(cyclic_find("laaa"))
   ```

2. **Working with Shellcode and Assembly:**
   - Directly manipulate shellcode or assembly for specific purposes.
   ```python
   from pwn import *
   print(shellcraft.sh())
   print(hexdump(asm(shellcraft.sh())))
   ```

3. **Interacting with Processes:**
   - Initiate a local process and interact with it, sending commands.
   ```python
   from pwn import *
   p = process("/bin/sh")
   p.sendline("echo hello;")
   p.interactive()
   ```

4. **Interacting with Remote Processes:**
   - Interact with a remote process, streamlining the process of sending and receiving data.
   ```python
   from pwn import *
   r = remote("127.0.0.1", 1234)
   r.sendline("hello!")
   r.interactive()
   r.close()
   ```
   - Before executing, set up a netcat listener with `nc -lp 1234`.

5. **Packing and Unpacking Numbers:**
   - Facilitate exploits and data parsing over the network with numerical packing and unpacking.
   ```python
   from pwn import *
   print(p32(0x13371337))
   print(hex(u32(p32(0x13371337))))
   ```

6. **Binary Analysis:**
   - Load and analyze binary files, extract information, and search for specific symbols.
   ```python
   from pwn import *
   l = ELF('/bin/bash')
   print(hex(l.address))
   print(hex(l.entry))
   print(hex(l.got['write']))
   print(hex(l.plt['write']))
   for address in l.search(b'/bin/sh\x00'):
       print(hex(address))
   ```

7. **ROP (Return-Oriented Programming):**
   - Simplify exploitation with ROP functions.
   ```python
   from pwn import *
   r = ROP(l)
   print(r.rbx)
   ```

8. **Encryption, Encoding, and Hashing Functions:**
   - Leverage essential functions for encryption, encoding, and hashing purposes.
   ```python
   from pwn import *
   print(xor("A", "B"))
   print(xor(xor("A", "B"), "A"))
   print(b64e(b"test"))
   print(b64d(b"dGVzdA=="))
   print(md5sumhex(b"hello"))
   print(shalsumhex(b"hello"))
   print(bits(b'a'))
   print(unbits([0, 1, 1, 0, 0, 0, 0, 1]))
   ```

## Official Documentation:
For a comprehensive reference guide, delve into the [Official Documentation](https://docs.pwntools.com/en/stable/globals.html) of `pwntools`. This documentation encompasses an extensive array of functionalities, providing in-depth insights for creating and modifying hacking scripts.

