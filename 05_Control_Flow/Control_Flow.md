# 5. Control Flow

## Definition:
Typically when we talk about control flow, it refers to the overall structure and flow of the program. Control flow is a somewhat abstract term which can refer to multiple topics, such as: conditional statements, loops, and program structure.

## Program Structure
Typically when discussing control flow, many intro to programming courses will break down a simple program into distinct blocks. One task is executed, then the next task is executed, and so on. Albeit unecessary for simple programs, as projects become larger,and the code more intertwined, it may be useful to draw out how the program should execute.

We will not discuss the specifics of block diagrams, the main takeaway is that code should be divided into blocks, each with a specific purpose. By doing so, it becomes easier to determine if a certain chunk of code may be better of abstracted into a function. It also gives you, as the programmer, an opportunity to organize your code into a more readable format.

Take the example from the end of Section 5. The swap function is removed and replaced with its respective code. The variables were also renamed to make the code more readable.

``` python
# Request 5 values from the user
user_input = []    # Initialize empty list
for index in range(5):
  user_input.append(int(input()))

# Traverse through the unsorted list and compares each number with the rest of the list, if current number is smaller than any other in the list, those are swapped
for first_index in range(5):
    second_index = first_index + 1
    for second_index in range (5):
        if (user_input[first_index] < user_input[second_index]):
            temp = user_input[first_index]
            user_input[first_index] = user_input[second_index]
            user_input[second_index] = temp

# Uncessesary, but represents the list is now sorted.
sorted_list = user_input

# Printing out the sorted list
print(sorted_list)
```
A small addition was made to the example, it now requests the user to input 5 numbers to the terminal. Those 5 numbers will be inserted into a list and sorted. If you're running the code, you need to press enter between each value.

The code above may be divided into two sections, requesting the user input and sorting the list. Regardless of the program, breaking down the program into abstract sections is incredibly helpful. If one section of the code is either buggy, or just not working, having each of these blocks helps focus debugging onto a certain section.

Turn your attention to the inner if statement with all the temp, user_input craziness. The purpose of this code is to swap two entries in a list, however, the purpose is not whats important. Since the code here is nested inbetween two for loops, the code will be called many times. The code here would do with abstraction into a function; greatly increasing the readability.

``` python
# Simple function which swaps two entries in a list.
def swap(my_list, index_1, index_2):
    temp = my_list[index_1]
    my_list[index_1] = my_list[index_2]
    my_list[index_2] = temp
    return
    
# Request 5 values from the user
user_input = []    # Initialize empty list
for index in range(5):
  user_input.append(int(input()))

# Traverse through the unsorted list and compares each number with the rest of the list, if current number is smaller than any other in the list, those are swapped
for first_index in range(5):
    second_index = first_index + 1
    for second_index in range (5):
        if (user_input[first_index] < user_input[second_index]):
          swap(user_input, first_index, second_index)

# Uncessesary, but represents the list is now sorted.
sorted_list = user_input

# Printing out the sorted list
print(sorted_list)
```
With only a minor change to the code, the nested for loop becomes much more readable. It becomes crystal clear that each iteration, some kind of swap will be happening in the list. Whats happening with the indicies doesn't need to be known to understand what the overall block of code accomplishes. Overall, the name of the game is readability and programming in a way which the future you will thank the past you.

## Conditional Statements
All of control of flow in programs relies on conditional statements. These statements return boolean values based on what is inside them. They use comparison and logical operators. Comparison operators: `==`, `!=`, `>`, `>=`, `<`, `<=`; these are used to compare values, primarily numeric values. Logical operators: `and`, `or`, `not`; these are used on boolean variables and statement to return boolean values. 
For example:
``` python
# comparison
2 == 2 # returns True
2 != 2 # returns False
3 > 1 # returns True
4 <= 2 # returns False

# logical
a = True
b = False
a and b # returns False
a or b # returns True
a and (not b) # returns True
```

## Booleans (again)
The boolean data type, if you forgot, returns either `True` or `False`. Conditional statements also return `True` or `False`, based on what it evaluates to. 

## If, elif, else
To truly define the structure of your code, if statements can be used.
``` python
if condition:
  code snippet 1
code snippet 2
```
In the above example, _condition_ is a placeholder for a conditional statement. If the conditional statement evaluates to `True`, then the code in the _code snippet 1_ placeholder executes and the code in the _code snippet 2_ executes after. If the conditional statement evaluates to `False`, then only the code in _code snippet 2_ executes.
Multiple if statements can be used as well to structure a program.
```python
grade = 90
if grade >= 90:
  print('letter grade: A')
if grade >= 80:
  print('letter grade: B')
if grade >= 70:
  print('letter grade: C')
if grade >= 60:
  print('letter grade: D')
```
In the above example, each if statement evaluates a conditional statement to see whether the variable is greater or equal to a particular value. You would expect the output to just be `letter grade: A`, right? Turns out, the actual output is:
```
letter grade: A
letter grade: B
letter grade: C
letter grade: D
```
Why is that?
In the example, every if statement evaluates to true, so each code nested within the statement executes. To prevent this, elif and else statements are used. 

## Loops
For and while loops iterate over a block of code as long as the provided condition(s) are satisfied or until it is forced to exit with a `break` statement.

### Iterables
Commonly when working with loops, you may hear the term iterable thrown around. We will discuss what it means in detail later on, but for now it just means that it has loop-like properties, even if it isnt a loop.

For example, a string may be represented as a list of characters. If we wanted to print a string, one way could be to print each character individually, using the keyword __in__. Although somewhat abstract, the word __in__ is synonmous with checking if something is apart of something else. However, the in only applies to objects which are iterable. Note, it is not a boolean operations and cannot be used to compare elements.

```python
string = "Hello World!"
for letter in string:
  print(string, end='')
print('')
```

Luckily for us, python gives us the ability to pass an iterable object into the print statement and it does all the work for us. In other languages like C or Java, this would be the typical syntax. Most of the basic Python data structures allow the use of in to traverse and interact with each of the entries.

```python
# Typing the following command into your interpreter will cause it to throw an error. The error will end with int is not iterable, implying this command does not work on the integer data type.
2 in 2
```
### For loop
A for loop lets us execute a set of code a limited number of times that is controlled by an iterator over a given expression.
We can iterator over any list or any range and execute a set of instructions over each element.
```python
list_of_numbers = [18,2,5,9]

#This iterates over the numbers in the list and prints out the result of the operators performed on the number
for number in list_of_numbers:
  print(number * 2 + 1)

#This iterates over the range 0-9 and prints outs each element but steps out of the loop after the 7th element since we issue a break command when the current element is the number 6
for item in range(10):
  print(item)
  if item == 6:
    break

list_in_list = [['a', 99, "this is it"], [25, 10, "numbers"]]

#The outer for loop iterates over the nested lists in list_in_list and the nested for loop iterates through the nested lists' individual elements and prints them out
for list in list_in_list:
  print("Iterating over this list: ")
  print(list)
  for element in list:
    #isinstance checks whether the given object is of the specified type
    if isinstance(element, str):
      print("This is a string: " + element)
    elif isinstance(element, int):
      print("This is an integer: " + str(element))
  print('\n')
```