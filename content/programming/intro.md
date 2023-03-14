---
title: Programming Intro
---

Programming is a vast field, and there are many different languages and tools that can be used to solve challenges. In this section, we will learn about the basics of programming, and how to use the programming tools that are used in CTFs. 

## Python

Python is typically used to solve challenges in CTFs because it is easy to learn, and it is very powerful. Python is an interpreted language, meaning that it is not compiled into machine code. Instead, it is interpreted by a Python interpreter. Python is also an object-oriented language, meaning that it uses objects to represent data. Python is also a high-level language, meaning that it is easy to read and write.

Programming can be both easy to learn, but also very challenging. Like learning another spoken language, it takes time to pick up the vocabulary and learn the grammar. Fortunately there's a wealth of resources to help you learn and once you've cracked it the results are phenomenal. Just remember: you'll need to be persistent.

Developing solid programming skills isn't going to happen overnight or by reading a book (or this Field Manual!) and watching a few videos. You need to get your hands dirty! You need to write code to learn code. You'll write code that doesn't work, debug it, fix it, and break it again many times. It's through these problems and interesting bugs you'll encounter that you gain a better understanding and your skills improve. Plus, finally fixing that error you've been struggling with for the last hour can be super satisfying!

So what kind of things could you do with these new programming skills? Well, let's say you have a zip file secured with a password, but you can't quite remember what it is. You could write a simple program to iterate and try a bunch of passwords instead of doing it manually. You could create a program to scrape content from websites to gather open source intelligence for a pentest you're working on. Or perhaps you need to be able to encrypt data and transmit it between two systems using sound! Programming opens up a world of creativity and possibilities.

## Running Python Programs

To run a python program, you need to have Python installed on your computer. You can download Python from the [Python website](https://www.python.org/downloads/). Once you have Python installed, you can run a Python program by opening a terminal and running the command `python3 <filename>`. For example, if you have a file called `hello.py`, you can run it by running the command `python3 hello.py`.

## Python Syntax

The syntax of a programming language is the set of rules that defines how a program is written. The syntax of Python is very simple, and it is similar to English. For example, the following code prints the text "Hello, World!" to the terminal:

```python
print("Hello, World!")
```

## Variables

Variables are used to store data. For example, the following code stores the text "Hello, World!" in a variable called `message`:

```python
message = "Hello, World!"
```

Variables can store many different types of data. For example, the following code stores the number `42` in a variable called `number`:

```python
number = 42
```

## Data Types

There are many different types of data that can be stored in variables. The most common data types are strings, integers, and floats. Strings are used to store text. Integers are used to store whole numbers. Floats are used to store decimal numbers. For example, the following code stores the text "Hello, World!" in a variable called `message`, the number `42` in a variable called `number`, and the decimal number `3.14` in a variable called `pi`:

```python
message = "Hello, World!"
number = 42
pi = 3.14
```

## Lists

Lists are used to store multiple values in a single variable. For example, the following code stores the numbers `1`, `2`, and `3` in a variable called `numbers`:

```python
numbers = [1, 2, 3]
```

## Dictionaries

Dictionaries are used to store key-value pairs. For example, the following code stores the key-value pairs `name: John` and `age: 42` in a variable called `person`:

```python
person = {
    "name": "John",
    "age": 42
}
```

## Tuples 

Tuples are used to store multiple values in a single variable, just like lists. However, tuples are immutable, meaning that they cannot be changed. For example, the following code stores the numbers `1`, `2`, and `3` in a variable called `numbers`:

```python
numbers = (1, 2, 3)
```

## Functions

Functions are used to perform a specific task. For example, the following code defines a function called `hello` that prints the text "Hello, World!" to the terminal:

```python
def hello():
    print("Hello, World!")
```

## Conditionals

Conditionals are used to perform different actions based on different conditions. For example, the following code prints the text "Hello, World!" to the terminal if the variable `message` is equal to "Hello, World!":

```python
if message == "Hello, World!":
    print("Hello, World!")
```

## Loops

Loops are used to repeat a block of code a certain number of times. For example, the following code prints the numbers `1`, `2`, and `3` to the terminal:

```python
for number in [1, 2, 3]:
    print(number)
```

## Reading and Writing Files

Python can be used to read and write files. For example, the following code reads the contents of a file called `message.txt` and stores it in a variable called `message`:

```python
with open("message.txt", "r") as f:
    message = f.read()
```

The following code writes the text "Hello, World!" to a file called `message.txt`:

```python
with open("message.txt", "w") as f:
    f.write("Hello, World!")
```

## Learning More
Programming takes practice, and there is no substitute for actually writing code. However, there are many resources available to help you learn. The following resources are a good place to start for learning Python:
* [Python Documentation](https://docs.python.org/3/)
* [Python Tutorial](https://docs.python.org/3/tutorial/index.html)
* [Python for Beginners](https://www.python.org/about/gettingstarted/)
* [Automate the Boring Stuff with Python](https://automatetheboringstuff.com/)
* [Codecademy](https://www.codecademy.com/learn/learn-python)
* [Learn Python](https://www.learnpython.org/)
