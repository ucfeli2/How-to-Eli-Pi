# 2. Data Types

## Python has 8 Data Types
Many of the standard data types have a constructor that intializes a variable to a specific type. 

These "constructors" look like exactly like functions, however, have names that are usually keywords. 

Keywords are specific words that the language reserves, which means the programmer is not allowed to use those words. For example, we wouldn't want a variable names _int_, or _string_. It is ambiguous what the purpose of the variable means. An especially evil person could initialize a variable named _int_, that is of type string. We can initialize variable without the use of constructors, however, there is a chance of ambiguity.
  
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

### 
### 4. Strings (_str_)
Ordered sequence of characters (numbers, letters, etc.)
ex. `"hello"`, `'Kaarthick'`, `"2000"`
```python
a = "Toast"
b = str(20) # The str() function turns whatever input is passed into a string
c = 'of Kingdom Orlando' # There is no difference between single quotes and double quotes in python

#You can construct a string by concatenating other strings as such:
d = a + ", aged " + b + ", " + c #'Toast, aged 20, of Kingdom Orlando'
```

### 5. Lists (_list_)
Ordered sequence of objects
ex. `[10, "howdy", 200.3]`
```python
aList = ['a', 2]
aList.append(True) #append adds the object to the end of the list; aList = ['a', 2, True]

```

### 6. Dictionaries (_dict_)
Unordered _key_:_value_ pairs
ex. `{"myKey":"value", "name":"Tyler"}`
Also known as "Hash Tables" in other languages

### 7. Tuples (_tup_)
Ordered immutable (or unchangeable) sequence of objects
ex. `(10, "hello", 2005.6))`

### 8. Sets (_set_)
Unordered collection of unique objects
ex. `{"a", "b"}`


### Arithmetic Operators
Python features 7 basic operations to perform on numeric data types (_int_ and _float_):
- Addition: `2+1` output: `3`
- Subtraction: `2-1` output: `1`
- Multiplication: `2*2` output: `4`
- Division: `7/4` output: `1.75`
- Modulo ("Mod"): `7%4` output: `3`
- Power: `2**3` output: `8`
- Floor Division ("Integer Division"): `7//4` output: `1`