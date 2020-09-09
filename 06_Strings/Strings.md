# 6. Strings

While strings are not considered one of the primitive data types within many programming languages, they are incredibly fundamental and powerful data type. Becoming familiar with how strings operate, as well as how to manipulate them are essential skills for any programmer. Strings are also the topic of many coding interview questions; for our Computer Science and Computer Engineering majors. The entirety of this section is dedicated to explaining and exploring what the String data type offers in more detail.

## Fundamentals 
In it's most primitive state, any word, sentence, or block of text can be thought of as a sequential list of letters; called characters. Regardless of the programming language, nearly every language uses this abstraction when it comes to strings. Technically speaking, a String is not an official data type in python. The data type may be thought of as a faux, or fake, data type since it relies on other fundamental data types and expands on their behavior/functionality.

Depending on the language, a string can be identified by looking for either single quotes, '', or double quotes, "". The contents within the two quotes composes the string. Note that certain programming languages have a dedicated String data type, such as C++, which may make the identification process a bit more difficult.

For example, take the string "Hello World!":
The string may be represented with the character data type discussed earlier. The first character of the string is H, the next is e, the following is l, and so on. Strings will commonly be manipulated by accessing and applying operations on the individual characters within it.

### Strings as arrays
In python, every string is treated as an list, or array, of characters. 

For example, all the characters in a string are index, so they can be retrieved by specifying the incides
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
# negative array indicies, hence to prevent confusion they should not
# be used without explaining their purpose.
print(MyString[-6:-1]) #"today"
```

### Built-in functions
Whenever working with a new data type it is helpful to call the dir command on it. By doing so, it will print out a list of the useful function which may operate on it, as well as useful information about the data.

```python
str = "Some random string"
dir(str)
# The list below is returned after calling dir(str)

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
Recall that the entires with underscores encasing them should not be interacted with. Their purpose will be explained alongside object-oriented programming.

As we look through the provided list there are some interesting and potentially helpful functions. The ones we will primarily discuss are: lower(), upper(), strip(), split(), and isnumeric().

```python
# The first method str.lower() will take a string and convert every alphabetic character to lower case.
str = "ThIs Is My StRiNg"
str.lower() # "this is my string"

# Likewise, the str.upper() method will take a string and convert every alphabetic character to upper case.
str = "ThIs Is My StRiNg"
print(str.upper()) # "THIS IS MY STRING"

# Note that these two methods work on the entirety of the string. In some situtations it may be required to access individual characters or substrings which need to be capitalized. Questions like these delve more into the interview questions aspect but we will provide examples later in the section.

# The str.strip() method will remove the leading and trailing whitespace from a string.
str = "    why is there so much     space in this       string      "
print(str.strip()) 

# It is important to note that the strip method does not remove internal whitespace from the string. That operation is left to the str.split() method.
# The split method allows for a string to be broken up into smaller substrings based on some delimitting character. The delimitting character will act as the boundaries between characters. 
# By default, delimiting will be based on whitespace; the ' ' character. However, other characters and even strings may be passed into the method for alternate delimitation.

str = "This simple string is something I really wish was fancier."
print(str.split())
print(str.split('i'))
print(str.split("is"))

# After running the code above, we can see that a list is returned. Within this list are all the substrings between the deliminating characters/strings. Note that whatever is delimiting the string is not included. We cannot express how important this function is and we highly recommend attempting to code up your own version of a split function. (Hint. Regular expression or nested looping)

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
Python provides two types of strings but there are technically three ways to declare a string is. As shown earlier, a string can be defined in either single or double quotes. The third type of string refers to multi-line comments, also called docstrings (in Python )

To preface, multi-line strings behave identically as normal strings, however, they have a drastically different purpose in Python. Multi-line strings are used for primarily documentation purposes. When writing a large block of text, prefacing every line with a # symbol gets tiresome and repetitive. Hence we can use tripple quotes, """, to enclose a large body of text.

```python
"""
This function simply returns the maximum of three numbers. Note, there is no explicit checking of data types done. The intentended usage is to determine the maximum value out of three integers and any other input is not guarenteed to be caught/checked.
Params: a, b, c where each parameter is an iterable object
Returns: The largest value of the three iterables
"""
def max_triple(a, b, c):
  return max(a, b, c)
```
The contents of the code above is not drastically important. The key takeaway is the use of multi-line comments, to provide documentation into what the function does; the paramaters, return values, etc.

## F-Strings
Short for formatted strings, F-strings allow the programmer to define a sort of template when outputting data.

TO DO: 
* Reversing strings
* Unsure if we discussed it earlier in the course but concatenating strings together using +.