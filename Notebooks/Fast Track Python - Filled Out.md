
# Fast Track Python

__Python__ is an __interpreted__, __high-level__ programming language for __general-purpose programming__. Python has a design philosophy that __emphasizes code readability__, notably __using significant whitespace.__

Python features a __dynamic type system__ and __automatic memory management.__ It supports __multiple programming paradigms__, including __object-oriented__, __imperative__, __functional__, and __procedural,__ and has a large and comprehensive __standard library__. Many other paradigms are supported via extensions, including __design by contract__ and __logical programming__.

To say that code is __pythonic__ is to say that it uses Python idioms well, that it is natural or shows fluency in the language, that it conforms with Python's __minimalist philosophy__ and emphasis on __readability__. In contrast, code that is difficult to understand or reads like a rough transcription from another programming language is called __unpythonic__.

# Data Types

## Container vs Values

A value cannot be seperated into smaller data, but containers can hold many values and even other containers.


## Mutable vs Immutable

Any container that can be modified directly is a __mutable__ data type. Data types that cannot be modified, including all values, are __immutable__, and a new object must be created every time it changes.


## Indexes vs Keys vs Unstructured

Some containers are __indexed__ with integers, some are __keyed__ with any (immutable) data, and some completely lack structure.

Type      | Container? | Mutuable?  | Structure    | Example
----------|------------|------------|--------------|---------
NoneType  | Value      | Immutable  |-             | None
bool      | Value      | Immutable  |-             | True
int       | Value      | Immutable  |-             | -1
float     | Value      | Immutable  |-             | -1.2
tuple     | Container  | Immutable  | Indexed      | (2, 3)
str       | Container  | Immutable  | Indexed      | 'Hello'
list      | Container  | Mutable    | Indexed      | \[2, 3\]
dict      | Container  | Mutable    | Keyed        | {'one' : 1}
set       | Container  | Mutable    | Unstructured | {1, 2}



```python
# NoneType
# There is only one member of type NoneType, and that is None

print(None)
print(type(None))
```

    None
    <class 'NoneType'>
    


```python
# Bool
# There are only two members of the type bool, and those are True and False

print(True, type(True))
print(False, type(False))
```

    True <class 'bool'>
    False <class 'bool'>
    


```python
# Int (integer)
# All positive and negative whole numbers, and zero

print(-5, type(-5))
print(6, type(6))
```

    -5 <class 'int'>
    6 <class 'int'>
    


```python
# Float
# All numbers with a decimal, even with only zeros after

print(-5.2, type(-5.2))
print(6.0, type(6.0))

# Be careful with these, the computer makes the equivalent of rounding error mistakes
print(0.3, 0.1 + 0.1 + 0.1)
```

    -5.2 <class 'float'>
    6.0 <class 'float'>
    0.3 0.30000000000000004
    


```python
# Tuple
# The first container, a simple sequence of values
# The elements of a tuple can be anything, including other tuples
# Tuples are created with either parenthesis with at least one comma seperating values (,)
# Or with the tuple() function

print( (1, 2, (3, True)) , type( (1, 2, (3, True)) ) )
print((6,), type( (6,) ))
print( tuple(), type(tuple()))
```

    (1, 2, (3, True)) <class 'tuple'>
    (6,) <class 'tuple'>
    () <class 'tuple'>
    


```python
# Str
# Strings are a container of symbols, usually used for human-readable inputs and outputs
# Strings are created with single quotes ' or double quotes "

print('hello', type('hello'))
print("5", type("5"))
print("''", type("''"))
```

    hello <class 'str'>
    5 <class 'str'>
    '' <class 'str'>
    


```python
# List
# Lists are much like tuples, except they are mutable
# So if the list is in multiple parts of the program, and it is changed, then the change will happen everywhere
# Lists are made with square brackets []

print([1, 2, [3]], type([1, 2, [3]]))
print([1], type([1]))
print([], type([]))
```

    [1, 2, [3]] <class 'list'>
    [1] <class 'list'>
    [] <class 'list'>
    


```python
# Dict
# Dictionaries are used to store 'associative data', like a word (key) to its definition (value) in a language dictionary
# Dictionaries are constructed with curly braces {} with colons : seperating keys and values and commas seperating key-value pairs
# All keys of a dictionary must be unique and immutable, and key-value pairs are unordered
# Empty dictionaries are construced with curly braces with nothing in them

print({'one': 1, 'two': 2, 'three': 3}, type({'one': 1, 'two': 2, 'three': 3}))
print({6: 1, 5: 2, 4: {3: 2, 1: 0}}, type({6: 1, 5: 2, 4: {3: 2, 1: 0}}))
print({}, type({}))
```

    {'one': 1, 'two': 2, 'three': 3} <class 'dict'>
    {6: 1, 5: 2, 4: {3: 2, 1: 0}} <class 'dict'>
    {} <class 'dict'>
    


```python
# Set
# Sets are like dictionaries except there are only keys
# Sets are constructed with curly braces without colons
# Elements of sets must be unique and immutable
# The set arithmetic section will show one reason why sets are useful
# Empty sets are constructed with set()

print({1, 2, 3, 3}, type({1, 2, 3, 3})) # Note how the extra 3 gets dropped
print({1, 2, (4, 5)}, type({1, 2, (4, 5)}))
print(set(), type(set()))
```

    {1, 2, 3} <class 'set'>
    {(4, 5), 1, 2} <class 'set'>
    set() <class 'set'>
    

# Statements

Statements are pieces of code that define a context for multiple lines. Unlike most languages, the code inside of a statement is signified by a colon `:`, then __indentation__, rather than curly braces. Any statement can be placed inside any other statement.

## Assignment Statements

The assignment statement uses the symbol `=`. `x=2` means that label `x` receives a reference to a separate, dynamically allocated object of numeric (int) type of value `2`.


```python
# Assignment

x = 2
print(x)

new_print = print
new_print(3)
```

    2
    3
    

## Conditional Statements

The `if` statement, which conditionally executes a block of code, along with `else` and `elif` (a contraction of else and if). Empty data types, `False`, and `None` are considered `False`.


```python
# Conditionals

a = []
b = ['hello']

if a:
    print('a is not empty')
else:
    print('a is empty')

if b:
    print('b is not empty')
else:
    print('b is empty')

x = False
y = True

if x:
    print('x is true')
elif y:
    print('x is false and y is true')
else:
    print('x is false and y is false')
```

    a is empty
    b is not empty
    x is false and y is true
    

## Iteration Statements

The `for` statement, which iterates over containers, captures each element to a local variable for use by the attached block. 

The `while` statement executes a block of code as long as its condition is `True`.

Both iteration statements can use `break` and `continue` keywords, to break out of the loop and skip to the next element in the iteration, respectively.

Iteration statements also have an `else` block, like `if` statements, which is executed if the statement is not __broken__.


```python
# For

list_of_lists = [[True, True, False, True], [False, True, True], [True, True, True]]

# print the sublists
for sublist in list_of_lists:
    print(sublist)
    
print()

# Where's the False? 
for sublist in list_of_lists:
    i = 0
    for value in sublist:
        if value:
            i = i + 1
        else:
            break
    else:
        i = None
    print('The First False is at', i)
```

    [True, True, False, True]
    [False, True, True]
    [True, True, True]
    
    The First False is at 2
    The First False is at 0
    The First False is at None
    


```python
# While

# Squares less than 100

i = 0
square = i*i

while square < 100: # < is less than
    print(i, square)
    i = i + 1
    square = i * i
    
```

    0 0
    1 1
    2 4
    3 9
    4 16
    5 25
    6 36
    7 49
    8 64
    9 81
    

## Error Handling

The `try` statement, which allows exceptions raised in its attached code block to be caught and handled by `except` clauses; it also ensures that clean-up code in a `finally` block will always be run regardless of how the block exits. The `raise` statement, used to raise a specified exception or re-raise a caught exception.


```python
# Error Handling


# Safe Division
A = [2, 'fish']
B = [0, 1]

errors = 0

for a in A:
    for b in B:
        try:
            print(a, 'divided by', b, 'is', a / b)
        except ZeroDivisionError:
            errors = errors + 1
            print("You can't divide by zero:", a, b)
        except:
            errors = errors + 1
            print("Something else went wrong:", a, b)
print()
print('total errors:', errors)
            
```

    You can't divide by zero: 2 0
    2 divided by 1 is 2.0
    Something else went wrong: fish 0
    Something else went wrong: fish 1
    
    total errors: 3
    

## Code Reusability

### Functions

The `def` statement defines a __function__, __method__, or __generator__.
__Functions__ are segments of code that make their own scope, take in parameters, process them, and stop all processing once __returned__ with the `return` keyword, and will start back _at the top of the function_ when called again. 

### Generators

Python also has __Generators__, which operate the same way, but use the `yield` keyword instead, and resume _at the yield_ when called with the `next` function. Both will return `None` if there is no more code in the block.

### Classes

The `class` statement executes a block of code and attaches its local namespace to a class, for use in object-oriented programming.



```python
# Functions

def return_print(x):
    print(x)
    return x

print(5 + return_print( 6 + return_print(7)))


def powerer(x, y):
    return x**y

def cuber(x):
    return powerer(x, 3)

print(cuber(6))
```

    7
    13
    18
    216
    


```python
# Generators

# Tally

def Tally():
    i = 0
    while True:
        i = i + 1
        yield i

tally = Tally()

print(next(tally))
print(next(tally))
print(next(tally))
print(next(tally))
print(next(tally))

```

    1
    2
    3
    4
    5
    


```python
# Classes

class vector3D:
    def magnitude(self):
        return (self.x**2 + self.y**2 + self.z**2)**(1/2)

my_vec = vector3D()

my_vec.x = 4
my_vec.y = 13
my_vec.z = 16

print(my_vec.y)
print(my_vec.magnitude())
```

    13
    21.0
    

# Simple Expressions

Expressions are pieces of code that are waiting to be evaluated and simplified. An expression can always be placed in parentheses to elevate its evaluation order, within other expressions, or within statements.

## Arithmetic operators
* addition: `+`
* subtraction: `-`
* multiplication: `*`
* division: `/`
* floor division: `//`
* exponent: `**`
* modulus: `%`

## Set operators
* set xor: `^`
* set intersection: `&`
* set union: `|`

Both arithmetic and set operators have corresponding augmented assignment statements, created by adding `=` to the operator.

## Comparison operators
* logical and: `and`
* logical or: `or`
* logical not: `not`
* value equality: `==`
* value inequality: `!=`
* identity equality: `is`
* identity inequality: `is not`
* less than: `<`
* greater than: `>`
* less that or equal to: `<=`
* greater than or equal to: `>=`

## Membership Operator
* membership test: `in`

## Indexing
* `d['x']`

## Function Calling
* `f(x)`

## Method Calling
* `Cls.func(x)`


```python
# Arithmetic


for i in [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]:
    d = i//5
    r = i%5
    print(i, d, r, d*5 + r)
```

    1 0 1 1
    2 0 2 2
    3 0 3 3
    4 0 4 4
    5 1 0 5
    6 1 1 6
    7 1 2 7
    8 1 3 8
    9 1 4 9
    10 2 0 10
    11 2 1 11
    12 2 2 12
    


```python
# Set

mine = {1, 2, 5, 7, 10}
yours = {2, 4, 6, 8, 10}

both_of_ours     = mine & yours
only_mine        = mine - yours
one_of_ours      = mine | yours
only_yours       = yours - mine
only_one_of_ours = mine ^ yours

print(both_of_ours)
print(only_mine)
print(one_of_ours)
print(only_yours)
print(only_one_of_ours)
```

    {2, 10}
    {1, 5, 7}
    {1, 2, 4, 5, 6, 7, 8, 10}
    {8, 4, 6}
    {1, 4, 5, 6, 7, 8}
    


```python
# Comparison

print(2 > 3)

```

    False
    


```python
# Membership

s = {2, 3, 4, 5, 6, 7, 8, 9, 10}

print(5 in s)
print(11 in s)

```

    True
    False
    


```python
# Indexing

a = [0, 1, 2, 3, 4, 5]
print(a[2])

a[3] = 'three'
print(a)
```

    2
    [0, 1, 2, 'three', 4, 5]
    

# Assignment Expressions

For many python __statements__, there is a __statement expression__ counterpart that uses the same keywords, but are contained in one __expression__. This is where python syntax differs from a lot of other languages, and makes python very quick to write. 

## Assignment Expression

No current implementation.

## Conditional Expressions

Uses `if` and `else` in one expression.


```python
# Conditional Expressions

clouds = False

weather = 'cloudy' if clouds else 'sunny'

print(weather)
```

    sunny
    

## Iteration Expressions

Iteration expressions are done via __comprehensions__ which takes one container, applies an inline function to each value in the container, and puts it in another container.


```python
# Iteration expressions

x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

squares =     [i**2 for i in x]
odd_squares = [i**2 for i in x if (i**2)%2==1]

print(squares)
print(odd_squares)
```

    [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
    [1, 9, 25, 49, 81]
    

## Function Expression

Function expressions are done via the `lambda` keyword.


```python
# Function Expressions

tripler = lambda x: x*3

print(tripler(5))
```

    15
    

## Error Exception Expressions

No comparison

# Pulling it All Together



```python
# Putting it All Together

# Example: Hailstone Numbers
print('Hailstone')
step = lambda x: x/2 if x%2==0 else x*3+1

for i in range(1, 30):
    s = i
    h = 0
    while s != 1:
        s = step(s)
        h += 1
    print(i, h)
        
# Example: Fizzbuzz
print()
for i in range(31):
    if i%15==0:
        print('fizzbuzz')
    elif i%3==0:
        print('fizz')
    elif i%5==0:
        print('buzz')
    else:
        print(i)
        
# Another Fizzbuzz Example
print()
print('Another Fizzbuzz')
print()
for i in range(31):
    print([i, 'fizz', 'buzz', 'fizzbuzz'][(1 if i%3==0 else 0) + (2 if i%5==0 else 0)])
```

    Hailstone
    1 0
    2 1
    3 7
    4 2
    5 5
    6 8
    7 16
    8 3
    9 19
    10 6
    11 14
    12 9
    13 9
    14 17
    15 17
    16 4
    17 12
    18 20
    19 20
    20 7
    21 7
    22 15
    23 15
    24 10
    25 23
    26 10
    27 111
    28 18
    29 18
    
    fizzbuzz
    1
    2
    fizz
    4
    buzz
    fizz
    7
    8
    fizz
    buzz
    11
    fizz
    13
    14
    fizzbuzz
    16
    17
    fizz
    19
    buzz
    fizz
    22
    23
    fizz
    buzz
    26
    fizz
    28
    29
    fizzbuzz
    
    Another Fizzbuzz
    
    fizzbuzz
    1
    2
    fizz
    4
    buzz
    fizz
    7
    8
    fizz
    buzz
    11
    fizz
    13
    14
    fizzbuzz
    16
    17
    fizz
    19
    buzz
    fizz
    22
    23
    fizz
    buzz
    26
    fizz
    28
    29
    fizzbuzz
    


```python

```
