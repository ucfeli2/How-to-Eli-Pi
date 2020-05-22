# 1. Interpreter

Before diving into the syntax, we want to take a moment to discuss the Python interpreter. The interpreter will be your home for testing small snippets of code. It is essentialy a private workspace where commands can be executed.

* Note that there are two different interpreters available to the user, _"python2"_ and _"python3"._

We will be using the python3 language and interpreter, since Python 2 had been officially discontinued.

## Opening the Interpreter:
Depending on what platform you are using there are several ways to open the interpreter. The most common way is to open your local terminal and typing _"python3"_ into it.

1. Windows:
Windows 10 ships with two native terminals: _"Windows PowerShell"_ and the _"Command Prompt"._ Either of these terminals are capable of running python. 

2. Mac/Linux:
Depending on your Linux distribution, the name of the terminal may be different. For most cases, including Mac, the local terminal will have the name terminal.


The following should be open on your terminal:
```
Python 3.8.1 (default, <current_date>, <current_time>) 
[GCC 8.3.0] on <your_operating_system>
Type "help", "copyright", "credits" or "license" for more i
nformation.
>>> _
``` 
## Interpreter vs Terminal:
The differences between the Interpreter and terminal and mainly semantic. Terminals typically have access to the operating system, whereas the interpreter does now. However, there are modules that allow the interpreter to access components of the OS. In addition, both are types of text-based interfaces that rely on the user to input commands.

Depending on the platform, each terminal may use a different language. The Window's command prompt uses MS DOS, PowerShell uses a proprietary scripting language, Mac and Linux use variants of Bash. The Python interpreter is just another implenetation of a terminal, in this case using the Python language.


## Python as a basic calculator:
Since we can run Python right on the terminal, we can use it as a basic calculator without having to compile and then run the program to get the answer. Once we have the the interpreter open, we can directly input the calculations we want to do. Only simple calculations (addition, subtraction, division, multiplication, and modulus) can be run in the interpreter without needing to import any additional libraries.
```python
$ python3
Python 3.8.1 (default, <current_date>, <current_time>) 
[GCC 8.3.0] on <Your operating system>
Type "help", "copyright", "credits" or "license" for more information.
>>> 1+2
3
>>> 1.5*2
3.0
>>> 4/4
1.0
>>> 250 % 3
1
>>> 1000000 - 10000
990000
```
You can also complex numbers in your calculations by importing the cmath library.
```python
>>> 1e20 - 1e15
9.9999e+19
>>> 1.25e5 % 3e2
200.0
```
## Simple data types

## Using the Interpreter to Run Programs
 Consider the file main.py
```python
print("hello world")
```
Typically, you could run this one of two ways: either by entering `python3 main.py` into your computer's terminal (method 1) or by going into the Python interpreter by typing `python3` and within the interpreter, enter `import main` (method 2). Both of these methods will yield the same outputs. However, considering the simplicity of this program, you could just enter the code directly into the interpreter (Method 3), and see the results immediately.
#### Method 1
```
$ python3 main.py
hello world
```
#### Method 2
```
$ python3
...
>>> import main
hello world
```
#### Method 3
```
>>> print("hello world")
hello world
```