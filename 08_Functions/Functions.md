# 8. Functions

## Hello Function!
Functions are part of the fundamental blocks that power Python as with any other language. In fact, if you are familiar with how functions work in a different language, then you already have a working knowledge of functions in Python!

## Overview
Functions enable the user to modularize parts of their code for reusability and/or to extract some parts of their code into its own entity. Functions are powerful in the sense that they can be invoked from almost anywhere in the code and can take in extra values (parameters) that can be used to change the output of the function.

## A Basic Function
The following is a code snippet showing the definition of a function and calling that function later in the program
```python
# Defining the HelloFunction
def HelloFunction():
  print("The Hello Function function was called")

print("Now the HelloFunction function will be invoked")
HelloFunction()
```
All functions start with the keyword `def` to indicate the start of a function definition and is followed by a unique function name and a list of parameters that will get into later in this section. Then comes the body of the function where code needed to be executed for that function will be defined.

Return statements
  &nbsp;How and where to return
  &nbsp;Multiple return values and how that'll be recieved by the caller
Parameters
  &nbsp;Types of paramters, default values
  &nbsp;How to explicitly specific paramter values of a function when calling it 