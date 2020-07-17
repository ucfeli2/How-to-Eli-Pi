# 4. Comments and Documentation

## Preface:
There is no single, or unified, way to comment and document your code. Depending on the language, type of programmer, and experience different techniques will be used. Some people opt for no comments as a means to force the programmer to make the code more readable. Whereas others may prefer heavy descriptions so any other programers do not need to break down every line of code. While there is no one correct style, we will present some guidelines that many, if not all, programmers abide by.

## Commenting
There are three main types of commenting present across nearly every language: single-line, multi-line, and end of line comments. In Python, comments are denoted with a #. Anything following the # symbol will not be read by the interpreter; or compiler in other languages. The number one rule with comments is to keep them short and sweet. 

### 1. Single-line:
Single line comments are usually placed above a line they refer too.
``` python
# The line below will print "Hello World" to the console.
print("Hello world")
```  
### 2. Mult-line:
Multiple single-line comments may be used to make multi-line comments. Some languages have a dedicated multi-line comment, however, Python does not. For example:
``` C19
// Here is a single line comment in C.
printf("%s", "Hello World");

/*
Anything included in between the astericks will be a comment.
Multi-line comments are usually used to describe the behavior of a function or a block of code.
Take the say_hello function below, a multi-line comment may be used to describe the inputs and outputs
as well as the behavior and assumptions the function uses.
*/

/*
Simple function which prints hello to the console.
Params: None
Return Value: None
*/
void say_hello()
{
  printf("%s", "Hello user :)");
}
```

To use multiline comments in python, a # symbol must start every line.
``` Python
# Here is my single line comment from before.
print("Hello World")

# If I were to write a large body of text, describing the behavior of a function,
# I would need to preface each additional line with another hash. Besides that,
# there is not a huge difference between single and multi-line comments in Python.
```
#### DocStrings
The closest thing to a "traditional" multi-line comment in python are called DocStrings and and denoted by three double quotes; """. All of the text between two sets of tripple quotes will be treated similar to a multi-line comment, however, they are not the same. DocStrings should be reserved for function documentation and descriptions. There is software which will convert raw python files to readable documentation; similar to the JavaDocs. Any text included within the DocStrings would be included in the documentation, which might not be desired.

``` python
"""
Simple wrapper function to find the maximum of three numbers. 

Params: Three comma separated integers.
Return Value: A single integer value.
Assumptions: Unsure if passing different data types provide correct behavior.
"""
def find_max(a, b, c):
  return max(max(a, b), c)
``` 
### 3. End of line (EOL):
Simply enough, and end of line comments are placed at the end of a line of code. In general, the comment must be short; a few words at max. EOL comments should be thought of like semicolons; appending a bit more information. 

EOL comments are the most diversive comment style across programmers. Attempting to come up with examples is somewhat difficult, many of the occasions the tech team uses them is for reminders. Say we are searching for a certain value within a list.

``` python
# Linear search function which checks if an integer is in a list.
# Runtime: O(n)
# Params: A list and an integer.
# Asssumptions: A list and integer are passed into the function.
#               Unknown behavior will occur otherwise.
def linear_search(my_list, target):
  for entry in my_list:
    if (my_list == target)
      return true;
      
  return false;
  
  x = 3 # Target variable
  list_1 = [1, 2, 3, 4, 5]
  in_list = linear_search() # O(n) runtime
  
  # Print to the console if x is in the list.
  if (in_list):
    print(x + "is in the list!")  
  else:
    print("Try again, " + x + " is not in the list)
```
Some of the concepts used in the above code have not been discussed yet. Regardless, notice single line comments are used to describe blocks of code, the end of line comments serving as reminders, and the multilines providing ample information.

## Variable Naming:
Variables are values with names attached to them so they can be easily referred to and found when necessary. They can be used to store values instead of "hard coding" values; often called "magic numbers". Since variables will often be referred to several times in a function, block of code, or file, they should be given names that are concise and describe their purpose. 

For example, if you wanted to make a variable that stored the maximum length of a name, you could use `maxnamelength` or `maxnamelen`. However, if all of your variables are in this condensed text format, they not only become harder to read but can become lost in code; which is bad for countless reasons. To solve this, there are different types of naming conventions that allow variables to be more legible and easier to find. Two of the most commmon naming conventions are camelCase and snake_case.

### camelCase:
This one got its name because it resembles a camel's humps; each hump represents a capital letter. A variable in camel case would begin lowercase and each word following it would begin with a capital letter. Using the above example, the variables in camelCase would be `maxNameLength` and `maxNameLen`, respectively.

### snake_case:
Like camelCase, snake_case got its name because it resembles a snake, long and low to the ground. Each word is lowercase and separated by underscores. Using the same example, the variables in snake_case would be `max_name_length` and `max_name_len`, respectively.

Using naming conventions allows for code to be easy to read. It is very important to be consistent with your naming convention; choose a convention and stick with it throughout the remainder of the source code, don't use both camelCase and snake_case for variables. 

## Examples:
The code below is an implementation of the bubble sort sotring algorithm. In short, the algorithm takes a list of integer, assumed to be unsorted, and sorts them. After running the code, a list with the values [-3, 0, 0, 1, 5] should be printed to the console. Take a look at the code and see if you can spot issues regarding variable naming and commenting style.

``` python
list_1 = [1, -3, 5, 0, 0]

def swap(mylist, index1, index2):
    temp = mylist[index1]
    mylist[index1] = mylist[index2]
    mylist[index2] = temp
    return

for i in range(5):
    j = i + 1

    for j in range(i+1, 5):
        if (list_1[i] < list_1[j]):
            swap(list_1, i, j)

list_2 = list_1
print(list_2)
```

The first thing you might notice is the lack of commenting. Bubble sort is an extremely well known algorithm. Sometimes for well known, or commonly used, algorithms commenting can feel like a chore. Regardless, at least some high level description and documentation should be included.

Some other observations are:
1. Inconsistencies in naming convention; camel case and snake case used.
2. Nondescript variable names; what could i and j represent?
3. What is the difference between list_1 and list_2?
 
Some of these questions are inteded to be rhetorical, but they are good ones to ask yourself while programming. Now let's take another stab at this function, keeping the future you in mind. A good practice is to imaging yourself 6 months from now, would you be able to go through your code and understand it?

``` python
#Initial list of unsorted numbers
unsorted_list = [1, -3, 5, 0, 0]

# Takes in a list and two indicies and swaps the numbers at those indicies
def swap(my_list, index_1, index_2):
    temp = my_list[index_1]
    my_list[index_1] = my_list[index_2]
    my_list[index_2] = temp
    return

# Traverse through the unsorted list and compares each number with the rest of the list, if current number is smaller than any other in the list, those are swapped
for index_1 in range(5):
  index_2 = index_1 + 1
    for index_2 in range (5):
        if (unsorted_list[index_1] < unsorted_list[index_2]):
            swap(unsorted_list, index_1, index_2)

sorted_list = unsorted_list

# Printing out the sorted list
print(sorted_list)
```