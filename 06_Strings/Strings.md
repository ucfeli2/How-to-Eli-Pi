# 6. Strings

While strings are not considered one of the primitive data types within many programming languages, they are incredibly fundamental and powerful data type. Becoming familiar with how strings operate, as well as how to manipulate them are essential skills for any programmer. Strings are also the topic of many coding interview questions; for our Computer Science and Computer Engineering majors. The entirety of this section is dedicated to explaining and exploring what the String data type offers in more detail.

## Fundamentals 
In it's most primitive state, any word, sentence, or block of text can be thought of as a sequential list of letters; also called characters. Regardless of the programming language, nearly every language uses this abstraction when it comes to strings. Technically speaking, a String is not an official data type in python. The data type may be thought of as a faux, or fake, data type since it relies on other fundamental data types and expands on their behavior/functionality.

Depending on the language, a string can be identified by looking for either single quotes, '', or double quotes, "". Anything within the two quotes composes the string. Note that the string variable is immutable. In short, mutability refers to how the data may be mutated, or changed. Typically, immutability means that the contents of variable may not be directly changed. Any change to the variable will result in a new copy needing to be created. Note that certain programming languages have a dedicated String data type, such as C++, which may make the identification process a bit more difficult.

For example, take the string "Hello World!":
The string may be represented with the character data type discussed earlier. The first character of the string is H, the next is e, the following is l, and so on. Strings will commonly be manipulated by accessing and applying operations on the individual characters within it.

### Strings as arrays
In python, every string is treated as a sequential list, or array, of characters. 

For example, all the characters in a string are at a specific index, hence the letter may be retrieved by accessing the string at the given index.
``` python
helloStr = "Hello World!"
print(helloStr[0]) # H
print(helloStr[3]) # l
print(helloStr[:5]) # Hello
```
In the last line of the code above there is a colon used to access the list. This notation simply allows for all of the character up until the index following the colon to be returned.

```python
MyString = "Hello! How are you doing today?"
print(MyString[:6]) #"Hello!"
print(MyString[7:10])#"How"
print(MyString[11:14]) #"are"

# Recall that negative indicies may also be used.
# However, many traditional programming languages do not allow for the use of 
# negative indicies. To prevent confusion they should not be used without  
# explaining their purpose.
print(MyString[-6:-1]) #"today"
```

### Built-in functions
Whenever working with a new data type it is helpful to call the dir command on it. By doing so, it will print out a list of the useful built-in functions which may operate on it.

```python
str = "Some random string"
dir(str)
# The list below is returned after calling dir(str):

#['__add__', '__class__', '__contains__', '__delattr__', '__dir__', 
#'__doc__', '__eq__', '__format__', '__ge__', '__getattribute__',
#'__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__',
# '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__',
#'__mod__', '__mul__', '__ne__', '__new__', '__reduce__', 
#'__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__',
#'__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold',
#'center', 'count', 'encode', 'endswith', 'expandtabs', 'find',
#'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii',
#'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 
#'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 
#'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 
#'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 
#'splitlines', 'startswith', 'strip', 'swapcase', 'title', 
#'translate', 'upper', 'zfill']
```
Recall that the entries with underscores encasing them should not be interacted with; think of them as private. Their purpose will be explained later alongside object-oriented programming.

As we look through the provided list there are some interesting and potentially helpful functions. The ones we will primarily discuss are: lower(), upper(), strip(), split(), concatenation, and isnumeric().

```python
# The first method str.lower() will take a string and convert every alphabetic character to lower case.
str = "ThIs Is My StRiNg"
str.lower() # "this is my string"

# Likewise, the str.upper() method will take a string and convert every alphabetic character to upper case.
str = "ThIs Is My StRiNg"
print(str.upper()) # "THIS IS MY STRING"

# Note that these two methods work on the entirety of a string. In some situtations it may be required to access individual characters or substrings which need to be capitalized. Questions like these are the basis of many interview questions.

# The str.strip() method will remove the leading and trailing whitespace from a string.
str = "    why is there so much     space in this       string      "
print(str.strip()) 

# It is important to note that the strip method does not remove internal whitespace from the string. That operation is left to the str.split() method.
# The split method allows for a string to be broken up into smaller substrings based on some delimitting character. The delimitting character will act as the boundaries between characters. 
# By default, delimiting will be based on whitespace; the ' ' character. However, other characters and even strings may be passed into the method for alternate delimitation.

str = "This simple string is something I really wish was fancier."
print(str.split())
# Returns:
# ['This', 'simple', 'string', 'is', 'something', 'I', 'really', 'wish',
# 'was', 'fancier.']

print(str.split('i'))
# Returns: 
# ['Th', 's s', 'mple str', 'ng ', 's someth', 'ng I really w',
# 'sh was fanc', 'er.']

print(str.split("is"))
# Returns:
#['Th', ' simple string ', ' something I really w', 'h was fancier.']

# After running the code above, we can see that a list is returned. Within this list are all the substrings between the deliminating characters/strings. Note that whatever is delimiting the string is not included. We cannot express how important this function is and we highly recommend attempting to code up your own version of a split function. (Hint. Regular expression or nested looping)

# The concatenation operations is not technically a function, but a way to combine two strings together. Using the addition operator, two strings are added together, or concatenation into a single string. Note that Applying arithmetic operations to data types has a somewhat ambiguous definition. It is very uncommon for data types to support these operations, however, strings are an exception. While this seems basic, it is an incredibly powerful, useful, and commonly used operation.

str_1 = "This is "
str_2 = "my string!"
print(str_1 + str_2) # "This is my string!"

# Lastly, we have the str.isnumeric() function. In many STEM fields, we do not have the physical memory to hold extremely large and small numbers. A common technique to storing large numbers as a string. The isnumeric() function will return true or false on whether a string contains exclusively numbers; no alphabet characters allowed.
str = "123456789
print(str.isnumeric()) # True

str = "D0 y0u L1k3 my L33T C0d3?"
print(str.isnumeric()) # False

str = "This string definitely does not have any numbers in it..."
print(str.isnumeric()) # False
```
Please note that the methods discussed in this section is far from the complete functionality that strings provide within Python. The goal is to provide the tools to allow yourself to explore what more the class has to offer.

One last operation, if you could call it, we wish to discuss is how to loop through a string. As mentioned earlier, a string functions very similarly to a list. Hence, we can use simple looping to present each character.

```python
# This first approach will use the 'in' keyword, allowing each character to be access without worrying about the loop boundary or any conditions. 
str = "I hope you're having a great day!
for letter in str:
  print(letter)
  # Other operations can be done here like checking if the character
  # is a letter or number by ascii ranges, or other built-in functions

# A more traditional approach which will be present in other programming languages is to loop until the end of the string.
# This approach reveals the more "array-like" aspect of the string.

string_length = len(str)
for index in range(string_length):
  print(str[index])
```
### Formating and Types of Strings
Python provides two types of strings but there are technically three ways to declare a string. As shown earlier, a string can be defined in either single or double quotes. The third type of string refers to multi-line comments, also called docstrings (only in Python ).

To preface, multi-line strings behave identically as normal strings, however, they have a drastically different purpose. Multi-line strings are used for primarily documentation purposes. When writing a large block of text, prefacing every line with a # symbol gets tiresome and repetitive. Hence we can use tripple quotes, """, to enclose a large body of text.

```python
"""
This function simply returns the maximum of three numbers. Note, there is no explicit checking of data types done. The intentended usage is to determine the maximum value out of three integers and any other input is not guarenteed to be checked/caught.
Params: a, b, c where each parameter is an iterable object
Returns: The largest value of the three iterables
"""
def max_triple(a, b, c):
  return max(a, b, c)
```
The contents of the code above is not drastically important. The key takeaway is the use of multi-line comments, to provide documentation into what the function does; the paramaters, return values, etc. One can also use the multi-line/continuation character `\` at the end of a line to have a continuous string broken into multi-lines for stylistic purposes.

```python
  str = "This is my really really really really really really long string that would be extremely hard to read since it is on a single line, and usually we should keep our lines to about 100 characters."

  betterStr = "This is my really really really really long string" \
              "which uses the continuation character to properly format" \
              "this somewhat large body of text so it is easily readable" \
              "by any person without needing them to scroll across the page."
# Do know that the line continuation character only works if a new-line is 
# present. Trying to type the strings above into the interpreter will not work.
```

## F-Strings
Short for formatted strings, F-strings allow the programmer to define a sort of template when outputting data. There are other functions to format strings, like str.format(), but f-strings make it easier for the user to format the strings and easier on the eyes. The format for f-strings is to simply append the character `f` right before a starting string quote and then use curly brackets within the string to insert python code.
```python
FirstName = "Bobby"
OrgName = "ELI2"
YearsAtOrg = 2

OutputString = f"{FirstName} has been at {OrgName} for {YearsAtOrg * 12} months so far and they love it"

print(OutputString) # Bobby has been at ELI2 for 24 months so far and they love it

# For those who have experience with other progrmaming languages like C, f-strings
# are very similar to the print f function. A more c-like implementation of the 
# line above is:
print("{}has been at {} for {} months so far and they love it".format(FirstName, OrgName, YearsAtOrg * 12))
# Similar to the first implementation, the curly braces are filled sequentially 
# with the arguments from the .format() function call.
```

## Application - Reversing Strings
One incredibly common programming interview, or challenge, question is to reverse a string. There are specific types of strings to where this operation is useful and this operation can help check for these types of strings. Lets take the string tacocat. When reversed, the string is the exact same. This property means that the string is a palindrome. Say you wanted to find a way to check if any arbitrary string is a palindrome, you could do the following.

```python
myString="TacoCat"
# Casing doesn't matter in palindromes, however, the string should be converted
# to all one case so we can check for equality.
print(myString==mystring.lower()) #False: TacoCat != tacocat
myString =myString.lower()

# One approach would involve using array slicing to to reverse the array. 
if (myString == myString[::-1]): # Using ::-1 as an index reverses the array.
  print(myString + " is a palindrome")

# A more traditional approach involves using two indicies to swap characters.
str1 = "TacoCat"
str2 = "1234"

# Abstracted the reversal algorithm into its own function.
# The indicies i and j will start at the beginnin and end of the string.
# The two characters will be swapped and the indicies are moved inward.
# Note, the string declared within quotes is an immutable data type in Python.
# Meaning, it is not possible to directly change an individual character. To 
# "hack" around this issue, the string is first converted into a list.
# This implementation below is not the pythonic way of reversing a list, however,
# it is included to show the process in other programming languages, like C.
def reverse(str):
    strAsList = list(str) # Convert the string into an list.
    i, j = 0, len(strAsList) - 1
    while (i < j):
             temp = strAsList[i]
             strAsList[i] = strAsList[j]
             strAsList[j] = temp
             i += 1
             j -= 1
    return str(strAsList)

print(reverse(str1))
print(reverse(str2))
```

This marks the ends of our discussion of strings. There are many more things we would like to discuss but we lack the time. We highly encourage you play around with the data type and come up with your own questions, or even try some programming interview questions. The next section we will discuss are the native data structures within Python.