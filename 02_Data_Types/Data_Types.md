# 2. Data Types

## Python has 9 Data Types
Many of the standard data types have a constructor that intializes a variable to a specific type. 

These "constructors" look like exactly like functions, however, have names that are usually keywords. 

Keywords are specific words that the language reserves, which means the programmer is not allowed to use those words. For example, we wouldn't want a variable names _int_, or _string_. It is ambiguous what the purpose of the variable means. An especially evil person could initialize a variable named _int_, that is of type string. We can initialize variable without the use of constructors, however, there is a chance of ambiguity.

**Note**: Some types in Python are called _immutable_. This means that once created, they cannot be changed. If you were to create a new instance of a variable or re-assign a variable name, the original copy is not overwritten. This becomes important in some applications, and is something to keep in the back of your mind. 

Opposite to immutable types are _mutable_ types. This means that the object can be changed after creation. Things like lists are _mutable_ as they can be added to or deleted from without creating a new copy of the object.
  
### 1. Integers (_int_)
Whole numbers
ex. `3`, `300`, `200`
```python
intNumber = 35
x = int(13)
y = int("5") #the string 5 is converted to an integer by passing it to the int() constructor
# NOTE: We cannot pass non-number variables to the int() constructor (i.e. things like strings)
z = intNumber + x + y #z is also an integer
```

### 2. Floating Point (_float_)
Numbers with a decimal point
ex. `2.3334`, `4.6`, `100.0000001`
```python
floatingNumber = 2.3
x = float(5.58973)
y = float("12.33")
z = floatingNumber + x + y #z = 20.21973
```
### 3. Booleans (_bool_)
Logical Value indicating `True` or `False`
```python
a = True
b = False
intTrue = bool(-5) #Any number other than 0 is considered as true
intFalse = bool(0)
#(), [], {}, "", None, 0, and False are considered as False
c = bool(None) #c = False
```

### 4. Complex Numbers (_complex_)
Two dimensional numbers represented as a+ib, where a and b are real numbers and i is the square root of -1.

```python
z = complex(1, 5) # Initializes to 1 + i1
print(z.real)     # Prints the value 1
print(z.imag)     # Prints the value 5 
```
Note that python uses j instead of i. They are exactly the same, the engineering disciplines choose to use j, whereas mathematics uses i. Complex numbers may seem the least applicable with respect to the other data types. However, they are incredibly useful within Electrical Engineering.

### 5. Strings (_str_)
Ordered sequence of characters (numbers, letters, etc.)
ex. `"hello"`, `'Kaarthick'`, `"2000"`
```python
a = "Toast"
b = str(20) # The str() function turns whatever input is passed into a string
c = 'of Kingdom Orlando' # There is no difference between single quotes and double quotes in python

#You can construct a string by concatenating other strings as such:
d = a + ", aged " + b + ", " + c # d = 'Toast, aged 20, of Kingdom Orlando'
```
As in other languages, strings are stored as a sequential list, or array, of characters. Each character is accessible by indexing the string at a given position. Note that indexing the string starts at zero.

```python
message = "Hello World!"
print(message[0]) # Will print H, the first letter of the string.
print(message[6]) # Will print the letter W.

# Python is able to access strings using negative indicies.
print(message[-1]) # Will print the letter !.
```
String operations are made extremely intuitive in Python. It is essential to become proficient with them

### 6. Lists (_list_)
Ordered sequence of objects
ex. `[10, "howdy", 200.3]`
```python
aList = ['a', 2]
aList.append(True) #append adds the object to the end of the list; aList = ['a', 2, True]
secondElement = aList[1] #lists are indexed, so we can access specific elements by their indexed number, like in arrays
```

### 7. Dictionaries (_dict_)
Unordered _key_ : _value_ pairs
ex. `{"myKey":"value", "name":"Tyler"}`
Also known as "Hash Tables" in other languages
```python
myDict = {
  "organization" : "Eli2",
  "college" : "UCF"
}

#The keys are unique in a dictionary, so we can access a value by referring to the key
org = myDict["organization"] #or org = myDict.get("organization")

#Changing the values
myDict["college"] = "University of Central Florida"

#Add can values to the dictionary by giving the new key a value
myDict["city"] = "Orlando"

#Can remove specific key-value by using the pop method
removedValue = myDict.pop("city") #removedValue = "Orlando"
```

### 8. Tuples (_tup_)
Ordered immutable (or unchangeable) sequence of objects
ex. `(10, "hello", 2005.6))`
```python
#creating a Tuple
aTuple = ("UCF", "ELI2", "Python", "Course")

#Tuples are index, so we can access an element using its index
print(aTuple[0]) #UCF

#Since tuples are immutable, you can't change values
aTuple[1] = "Engineering" #Throws an error

#As with lists, you can access specific range of elements within the tuple
print(aTuple[1:3]) #('ELI2', 'Python') - starting from index 1 up to index 3 (excluding index 3)
```

### 9. Sets (_set_)
Unordered collection of unique objects
ex. `{"a", "b"}`
```python
aSet = {"a", "b", "c", "d"}

#Since they are unordered, the elements won't print out in the same order
print(aSet)

#Cannot change values in a set, but can add to it
aSet.add('e') #aSet = {'a', 'b', 'c', 'd', 'e'}

#Cannot add duplicate elements to a set
aSet.add('a') #aSet is still {'a', 'b', 'c', 'd', 'e'}

#Can remove the last item in the set using pop, but we won't know what will be remove since it's unordered
poppedItem = aSet.pop()
print(poppedItem)
```

### Arithmetic Operators
Python features 7 basic operations to perform on numeric data types (_int_ and _float_):

- Addition
ex. `2+1` results in `3`
- Subtraction
ex. `2-1` results in `1`
- Multiplication
ex. `2*2` results in `4`
- Division
ex. `7/4` results in `1.75`
- Integer Division (whole-number division)
ex. `7//4` results in `1`
- Modulo ("mod")
remainder after integer division
ex. `7%4` results in `3`
- Power
`x` raised to the `y` power
ex. `2**3` results in `8`