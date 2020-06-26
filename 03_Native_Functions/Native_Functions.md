# 3. Native Functions

Within Python there are many Native, or standard functions, you will use often. This section is dedicated to providing explanations and examples of these functions, and why they are necessary.

## Console Outputting
We encountered the print statement earlier in the tutorial and used it to print simple strings. However, the print function is not restricted to strings, just about every data type in Python has a built-in print function.

``` python
my_list = [1, 3, 3, 7]
my_set = ('l', 'o', 'l')
my_dictionary = {"Chillies?" : "Yes, please!}

# The commented lines show the terminal output for each command.
print(my_list)       # [1, 3, 3, 7]
print(my_set)        # ('l', 'o', 'l')
print(my_dictionary) # {"Chillies?" : "Yes, please!"}
```
Notice that each data type will print it's specific braces and quotations for strings/characters. When dealing with unknown variables, printing it may be used to determine the data structure and its contents.

All of the print examples we have provided use variables and string literals. There is no specific formatting, what if we wanted to print the output of a function or the value of a certain variable to a file? Each entry would be printed on a newline, making it quite difficult to read. 

### Formatted Strings
Also known as f strings, are a generalize print statements. Say we had a chat bot which will print the number of users in the room upon request. One way would be to construct the string every time the request is made, however, this is inefficient. Including curly brackets within a string is known as a format field. The format field is replaces with whatever argument is in the format function call.

``` python
response_1 = "There are "
repsonse_2 = " people in the room."
response = response_1 + num_people + response_2
print(response)
print("There are {} people in the room.".format(num_people))
```

As we talked about in section 2, strings are a data type which have built-in functions that operate on them. In this case we are using the format function on a string literal. Typically, we may declare a prompt as a variable and call the format method on the variable.
``` python
response_prompt = "There are {} people in the room."
print(response_prompt.format(num_people))
```
F strings are incredibly robust. Different arguments may be placed inside of the format fields for additional functionality. The examples provided serve as an introduction,but know that they are quite useful.

## Directory (dir)
Short for directory, dir is your go to command when you have no idea what a data type, library, or class offers.

``` python
my_string = str("Hello World!")
dir(my_string)
# Terminal Output
'''
['__add__', '__class__', '__contains__', '__delattr_
_', '__dir__', '__doc__', '__eq__', '__format__', '_
_ge__', '__getattribute__', '__getitem__', '__getnew
args__', '__gt__', '__hash__', '__init__', '__init_s
ubclass__', '__iter__', '__le__', '__len__', '__lt__
', '__mod__', '__mul__', '__ne__', '__new__', '__red
uce__', '__reduce_ex__', '__repr__', '__rmod__', '__
rmul__', '__setattr__', '__sizeof__', '__str__', '__
subclasshook__', 'capitalize', 'casefold', 'center',
 'count', 'encode', 'endswith', 'expandtabs', 'find'
, 'format', 'format_map', 'index', 'isalnum', 'isalp
ha', 'isascii', 'isdecimal', 'isdigit', 'isidentifie
r', 'islower', 'isnumeric', 'isprintable', 'isspace'
, 'istitle', 'isupper', 'join', 'ljust', 'lower', 'l
strip', 'maketrans', 'partition', 'replace', 'rfind'
, 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip
', 'split', 'splitlines', 'startswith', 'strip', 'sw
apcase', 'title', 'translate', 'upper', 'zfill']
'''
```
Now there is alot to unpack from the above terminal output. Any item which has underscores before and after it should be ignored. We will discuss these items later, but for now assume they are unaccessible. Everything else in the list is either a property or function for the specific data type.

``` python
my_string = str("Hello World!")
# Converts lowercase to uppercase
print(my_string.upper()) # "HELLO WORLD!"
# Removes whitespace from string.
print(my_string.strip(' ')) # HELLO WORLD! 
```

Note that dir function will not describe how to call, or use any of the properties. The method simply describes what is available to the user.
## Math functions
#### Max and Min
The max and min functions can be used to determine the largest and smallest values respectively in a given set of numbers.
One can pass in multiple numbers to the function, a list, set, or tuple of numbers, and it will output the largest or smallest value among them. In general, many standard function in Python will take more than one data type. It is generally a good idea to play with and experiment how certain functions operate on specific data types.
```python
#Passing in multiple numbers
max(1500, 20, 2, 17) # 1500
min(12, 5050) # 12

#Passing in a list
theList = [5,6,2,3,8,2]
max(theList) # 8

#Passing in a set
aSet = {11,22,33,44,55,00,66,77,88,99}
min(aSet) # 0

#Passing in a tupple
myTupple = (5897653, 810276, 111)
max(myTupple) # 5897653
```
Passing in a string to the max or min function will determine the largest or smallest character (based on the ASCII value) in a string.
Passing in a list of strings will output the first string in descending order if passed to the max function or will return the first string in ascending order if passed to the min function.
```python
#Passing in a string
max("This is a string") # 't'
min("This is a string") # ' ' -> a white space has a lower ASCII value than 'a'
min("Testing") # = 'e'

#Passing in a list of strings
max(["apple", "apply", "abacus", "application"]) # 'apply'
min(["apple", "apply", "abacus", "application"]) # 'abacus'
```

### Abs
The abs() function takes a number and outputs the absolute value of it
```python
#Abs only takes in one number
abs(-10202) # 10202
abs(105) # 105
```
### Len
The function len() returns the length of a string or the number of objects in a list.
```python
#len() takes in only one argument
len("abcd") #4
len([1,2,3]) #3
len(('a', 'ab', 'abc', 'bbaa')) #4
len({"this", "is", "a", "set", "of", "strings", "and", "12345"}) #8
len((("tuple inside"), ("a tupple"), ("so it's one argument"))) #3
```
### Range
range() is a function used to generate a "list" of numbers. It can take 1, 2, or 3 arguments. When passing only 1 arguments, `range(y)`, it generates numbers from 0 up to, but not including, 'y'. For example, `range(5)` generates `0, 1, 2, 3, 4`. When passing 2 arguments, `range(x, y)`, it generates numbers from 'x' up to, but not including, 'y'. For example, `range(1, 11)` generates `1, 2, 3, 4, 5, 6, 7, 8, 9, 10`. When passing 3 arguments, `range(x, y, inc)`, it generates numbers from 'x' up to, but not including, 'y', in increments of 'inc'. For example, `range(0, 100, 20)` generates `0, 20, 40, 60, 80`. By default, the numbers generated are in increments of 1.

## Loops
Loops are used for one of two purposes: to iterate over a data structure with multiple values and to perform a certain function or code block multiple times. Both are used often when dealing with large groups of data and to minimize code written.

There are 2 variations of loops: _while_ loops and _for_ loops.
_for_ loops have a set parameter for how many iterations it will perform. The most common way to code a _for_ loop is as follows:
```python
for i in range(x):
  print('Hooray!')
```
where "Hooray!" will be printed 'x' times.
_for_ loops are also used to iterate over data structures. This is how to use a _for_ loop to iterate over a list to get the sum of all elements in the list:
```python
sum = 0
a = [1, 2, 3]
for i in range(len(a)):
  sum = sum + a[i]
print(sum)
# output: 6
```
alternatively:
```python
sum = 0
a = [1, 2, 3]
for num in a:
  sum = sum + a
print(sum)
# output 6
```
Both methods yield the same results. Also, both methods use iterators to perform tasks. In the first method, 'i' is used to access the elements of list 'a' (a[0], a[1], a[2]). In the second method, 'num' is created and copies each value of 'a' in every iteration of the loop. 

_while_ loops rely on a conditional* to run each iteration. A common way to code a _while_ loop is as follows:
```python
i = 5
while i > 0:
  print(i)
  i = i - 1
```
where 'i' will be printed until it is equal to 0. In this case, the output will be:

```python
5
4
3
2
1
```
*we will dive further into conditionals in [Section 5](../05_Control_Flow/Control_Flow.md)
