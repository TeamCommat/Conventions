# Python Coding Convention

### Code layout

1. Indent codes with 4 spaces. Do not use tabs for indentation.
2. Write less than 80 letters per line. If the code gets longer, consider moving on to the next line, or dividing it into two parts.
3. Add two empty lines to divide functions and classes.
4. Do not write unnessesary semi-colon `;` at the end of the line.
5. Do not write unnessasary spaces in between `(), {}, []`.

   ```python
   # BAD
   my_tuple = ( 1, 2, 3 )


   # Good
   my_tuple = (1, 2, 3)
   ```
6. Add spaces at both sides of binary operators when declaring a variable. For calculation of two simple variables of same time, do not write space on both sides.

   ```python
   # BAD
   i=i+1
   submitted +=1
   x = x * 2 - 1
   hypot2 = x * x + y * y
   c = (a + b) * (a - b)

   # GOOD
   i = i + 1
   submitted += 1
   x = x*2 - 1
   hypot2 = x*x + y*y
   c = (a+b) * (a-b)
   ```
7. Do not add space on both sides of `=` when it expresses parameters.

   ```python
   # BAD
   def function(real, imag = 0.0):
       return another_function(r = real, i = imag)

   # GOOD
   def function(real, imag=0.0):
       return another_function(r=real, i=imag)
   ```

### Code style

1. Aviod implicit code style. Try to write code clear as possible.

   ```python
   # BAD
   def make_complex(*args):
       x, y = args
       return dict(**locals())

   # GOOD
   def make_complex(x, y):
       return {'x': x, 'y': y}
   ```
2. Do not write multiple statements in a single line.

   ```python
   # BAD
   print('foo'); print('bar')

   if x == 'foo': print 'bar'

   ## GOOD
   print('foo')
   print('bar')

   if x == 'foo':
       print('bar')

   ```
3. Use single quote for characters and strings. Using double quotes may cause unexpected errors.

   ```python
   print('Hello, world')
   print('It\'s me, mario!') # It's me, mario!
   print('C:\\Users\\Mario') # C:\Users\Mario
   ```
4. When multiple complex comparision is used for conditions, do not use both of them in a single line. Instead, divide them to two diffrent variables.

   ```python
   # BAD
   if <complex comparison> and <other complex comparison>:
       ...

   # GOOD
   cond1 = <complex comparison>
   cond2 = <other complex comparison>

   if cond1 and cond2:
       ...
   ```
5. When dealing with `None` value in a variable, do not check them directly. Instead, use `is`, `not` keywords.

   ```python
   # BAD
   if attr == True:
       print('True!')

   if attr == None:
       print('attr is None!')

   # GOOD
   if attr:
       print('attr is true!')

   if attr is None:
       print('attr is None!')
   ```
6. When accessing to dictionary variables, try to use `get()` function. It shortens the code and prevents unexpected behaviors.

   ```python
   d = {'hello': 'world'}

   # BAD
   if d.has_key('hello'):
       print(d['hello']) # world
   else:
       print('default_value')

   # GOOD
   print(d.get('hello', 'default_value')) # world
   print(d.get('bye', 'default_value')) # default_value
   ```
7. Try to shorten codes when dealing with python arrays. For example, when filtering elements that are even,

   ```python
   # BAD
   a = [1, 2, 3, 4, 5]
   b = []
   for i in a:
       if i%2 == 0:
           b.append(i)

   # GOOD
   a = [1, 2, 3, 4, 5]
   b = [i for i in a if i%2 == 0]

   # BEST
   b = filter(lambda x: x%2 == 0, a)
   ```
8. When reading from a external text, do not open and print them directly.

   ```python
   # BAD
   f = open('file.txt')
   a = f.read()
   print(a)
   f.close()

   # GOOD
   with open('file.txt') as f:
       for line in f:
           print line
   ```
9. When a single line gets too long, aviod using backslashes (`\`). Instead, use parentheses.

   ```python
   # BAD
   very_long_string = """For a long time I used to go to bed early. Sometimes, \
       when I had put out my candle, my eyes would close so quickly that I had not even \
       time to say “I’m going to sleep.”"""
   from some.deep.module.inside.a.module import a_nice_function, another_nice_function, \
       also_another_nice_function

   # GOOD
   my_very_big_string = (
       "For a long time I used to go to bed early. Sometimes, "
       "when I had put out my candle, my eyes would close so quickly "
       "that I had not even time to say “I’m going to sleep.”"
   )

   from some.deep.module.inside.a.module import (
       a_nice_function, another_nice_function, also_another_nice_function)
   ```
10. When creating a list that contains same value, use asterisk for multiplying list elements.

    ```python
    # BAD
    repeting_list = []
    for i in range(100):
        repeting_list.append(0)

    # GOOD
    repeting_list = [0]*100
    ```
11. When creating a multi dimensional list, use list comprehension.

    ```python
    two_dimensional_array = [[0] for __ in range(5)]
    print(two_dimensional_array)
    ```
12. For conditional statements in dictionary, do not use `has_key()` function, instead, use `in` to know if the dictionary has the key.
13. Import one by one. But when using `from` to import from the same directory, import multiple things at once.

    ```python
    # BAD
    import os, sys

    # GOOD
    import os
    import sys

    # GOOD
    from pytorch import nn, optim
    ```
14. Do not add unnecessary comments that explain the obvious.

    ```python
    # BAD
    x = x + 1 # Incresement in x for 1

    # GOOD
    x = x + 1 # Adds 1 in x for compensation for boundary value
    ```

### Naming rules

1. Aviod using `l` (lower case L), `O` (upper case O), or `I` (upper case i) for single-letter variable name. It is hard to distinguish from `0`, `1`.
2. When declaring variables that are not going to be used, add two underscores in front of the variable name.

   ```python-repl
   __unused_variable = 0
   ```
3. Class names should be in Camel Case.
4. Function names should all be in lower case and underscores.
5. Constants should be only declared in module unit, and their names should all be in capital case.
