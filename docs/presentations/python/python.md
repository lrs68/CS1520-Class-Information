# Python

-###-

## Benevolent Dictator for Life

![Guido](https://upload.wikimedia.org/wikipedia/commons/6/66/Guido_van_Rossum_OSCON_2006.jpg)

<!-- .element: class="column-left" -->

* [Guido van Rossum](http://neopythonic.blogspot.com/2016/04/kings-day-speech.html) started development on Python in 1989 as a project to keep him busy over the holiday break when his office was closed
* Worked for Google from 2005-2013, and currently works at Dropbox
    * Both employers had him spend 50% of his time working on Python
* Favorite Exception is KeyboardInterrupt()

<!-- .element: class="column-right" style="font-size:0.7em;" -->

-###-

## Version History

* An interpreted language
* Version 2.0 was released in Oct. 2000
* Version 3.0 was released in Dec. 2008

-###-

## Python 3

* 3.0 is a backwards-***incompatible***
    * Because of this Python 2.7 is still actively used by many
* 3.6 is the current latest version of Python
    * We will be using 3.x versions of Python in this course!
    * Be aware of the difference when checking online resources and running Python code on your computer!

Note:
* discuss install/class setup
* pull version for your os from python.org
* edit using preferred text editor and run on the command line
* will start off as a review for some, will probably cover new material for everyone

-###-

## Basic Syntax

```python
import random

r = random.randint(0, 100)
while r < 85:
    if r > 70:
        print(r, ":  so close!", sep="")
    elif r > 45:
        print(r, end="")
        print(":  Getting there...")
    else:
        print("{}:  Still so far away!".format(r))

    r = random.randint(0, 100)

print("OUT!")
```

Note:
* whitespace matters!
    * defines code blocks
    * print functions
    * default adds a newline, link [print()](https://docs.python.org/3/whatsnew/3.0.html), can be changed with end="..."
    * `elif` is weird...

-###-

## Hello World

```python
print("Hello World!")

```

-###-

## [Comments](https://www.python.org/dev/peps/pep-0008/#id30)

```python
# This is a comment
# Extends to the end of the line.

"""This is a multiline
comment.

When they are not docstring, they are used as a block string.
"""

x = foo(y) # Inline comment

```

-###-

## Reserved Keywords

* Python has a basic set of language keywords
* Variables/files cannot use these

```python
and         elif    if      print
as          else    import  raise
assert      except  in      return
break       exec    is      try
class       finally lambda  while
continue    for     not     with
def         from    or      yield
del         global  pass
```

-###-

## Typing

* Like JavaScript, Python is dynamically typed
* However, unlike JavaScript, Python is strongly typed
    * `1 + "1"` will raise an error
    * `1 + int("1")` is fine, as is `str(1) + "1"`
* `1 == "1"` will return false
    * Not the same value, one is a string, one an int
    * Python does not have a `===` operator

-###-

## Booleans

```python
True
False
```

-###-

## Numerical Types

* `int`
* `float`
    * `7 / 2 = 3.5`
    * `7 // 2 = 3`
    * `7.0 / 2.0 = 3.5`
    * `7.0 // 2.0 = 3.0`

-###-

## Strings

* Can be `"double quoted"`
* or `'single quoted'`
* or 

```python
"""TRIPLE
QUOTED"""

'''triple singles also work'''
```
* Plenty string methods available
* Of particular note is the fact that they can be indexed and sliced


-###-

## Expressions

* Python has sanely behaved math operators (precedence, associativity, etc.)

```python
a=2+3 
b=2+3*4
c = (2 + 3) * 4
```

* Operators are same as C

```python
+, -, *, /, %, <<, >>, &, |, ^, ...
```

* Other operators (Python-specific)

```python
7 // 4             # Truncating division
7 ** 4             # Power operator
```

-###-

## Flow Control

* If-else

```python
if a < b:
    print "Computer says no"
else:
    print "Computer says yes"
```

-###-

## Flow Control

* If-elif-else

```python
if a == '+':
    op = PLUS
elif a == '-':
    op = MINUS
elif a == '*':
    op = TIMES
else:
    op = UNKNOWN
```

-###-

## Relational Operators

* `< > <= >= == !=`
* Boolean expressions (and, or, not)

```python
if b >= a and b <= c:
    print( "b is between a and c")
if not (b < a or b > c):
    print( "b is still between a and c")
```

-###-

## Slicing

```
s = "slicing is fun!!"

print(s[0])
print(s[2:7])
print(s[-5])
print(s[-5:-2])
print(s[11:])
print(s[:7])
print(s[-5:])
print(s[0:11:2]) # ?
```

Note:
* `s`
* `icing`
* `f`
* `fun`
* Indices must be integers
* Slices do not include end value
* If indices are omitted, they default to the beginning or end of the list.

-###-

## Functions

```python
def say_hi():
    print("Hi!")


def shout(message="Hi"):
    print(message, "!", sep="")

shout()
shout("I love python")
shout(message="And keyword arguments")

```

-###-

## Tuples

* A collection of values packed together. IMMUTABLE

```python
s = ('CS1520',55,'Victoria 122')
s[0] = 'CS/COE1520' # ERROR
```

* Sometimes the `()` are omitted in syntax

```python
s = 'CS1520',55,'Victoria 122'
```

* Special cases (0-tuple, 1-tuple)

```python
t = ()          # An empty tuple
w = ('CS1520',)   # A 1-item tuple

class_room = "%s %s" % (s[1], s[2])
```

-###-

## Tuple Unpacking

```python
(name, student_count, room) = s

name, student_count, room = s # Omitted the ()
```

## Lists

* Mutable sequences

```python
empty = []
l = [1, 2, 5]
l.append(3)
if 3 in l:
    print(3, "is in", l)
```

Note:
* Order maintained.
* Can hold any object

-###-

## Dictionaries

```python
empty = {}
d = {"Waits":1520, "Garrison":8}
d["Ramirez"] = 1501

d.keys()
d.values()
d.items()
```

Note:
* Dictionaries good to represent simple data records
* Easy to manipulate (can freely change fields, modify values, etc.)
* Improved readability (key names are usually more descriptive than numeric indices)
* Easy interoperability (convert to JSON)
* All objects are Dictionaries
* No order

## Looping

```python
crazy_list = ["a", 1, 1.0, "d"]
for item in crazy_list:
    print(item)
for i in range(len(crazy_list)):
    print(crazy_list[i])

crazy_index = {}
for n, item in enumerate(crazy_list):
        crazy_index[item].append(n)
```

-###-

## List Comprehensions

```python
squares = [x**2 for x in range(10)]
names = ['TODD', 'WAITS']
lower = [name.lower() for name in names if name == "TODD"]
```

-###-

## List Comprehensions

```python
result = []
for name in sequence:
    if condition: 
        result.append(expression)
```

Note:
* List comprehensions come from math set theory

-###-

## Set/Dict Comprehensions

```python
{ x.upper() for x in names } # set

classes = { 'Waits': 'CS1520', 'Ramirez': 'CS1520', 'Frank': 'CS1401' }
{ name:class for name, class in classes.items() if class == 'CS1520' } # dict
```

-###-

## Iterators

* Both lists and range objects are iterable
* Meaning that an iterator can be created for either type
* Iterators must implement the method `__next__()`
* Successive calls to `__next__()` will iterate through the items in the collection
* When no more items remain in the collection, all future calls to `__next__()` should raise a `StopIteration` exception

-###-

## Exceptions and Try statements

```python
try:
    result = x / y
except ZeroDivisionError:
    print("division by zero!")
else:
    print("result is", result)
finally:
    print("executing finally clause")

try:
    raise Exception("foo", "bar")
except Exception as e:
    print(e)
    print(type(e))
    print(e.args)
```

-###-

## Breaking Down the Loop

-###-

## Generators

-###-

## Basic Object Oriented Python

-###-

## Basic Inheritance

-###-

## Decorators

-###-

## Basic File I/O

-###-

## Python Contexts

-###-

## DIY Contexts

-###-

## Pythonic Coding

> "Code is read much more often than it is written."
> "A style guide is about consistency. Consistency with this style guide is important. Consistency within a project is more important. Consistency within one module or function is the most important."

-###-

## Tips

* If it's hard to explain to a person, you're probably doing it wrong

-###-

## [PEP 8](https://www.python.org/dev/peps/pep-0008/)

-###-

## Dislaimer

* This is only a brief introduction to Python
* There are many topics that we neared by did not touch upon
    * Multiple inheritance
    * Protocols
        * Containers
        * Iterators
        * Context Managers
    * Class variables 
    * And many more!!!

-###-