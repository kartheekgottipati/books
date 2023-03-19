# Variables

In Python, variables are used to store values and data. Think of variables as containers that hold a particular value or set of values. Variables are created using an assignment operator, which assigns a value to a variable.

### Declare a variable and assign it a value

```python
>>> x = 5
>>> x
5

>>> y = 10.5
>>> y
10.5

>>> name = "John"
>>> name
"John"

>>> is_active = True
>>> is_active
True
```

### Reassign a variable

```python
>>> x = 5
>>> x
5

>>> x = 10
>>> x
10
```

### Assign multiple variables

```python
>>> x, y, name, is_active = 5, 10.5, "John", True
>>> x
5

>>> y
10.5

>>> name
"John"

>>> is_active
True
```

### Assign the same value to multiple variables

```python
>>> x = y = name = "John"
>>> x
"John"

>>> y
"John"

>>> name
"John"
```

### Naming conventions for variables

```python
# Variables can start with a letter or underscore
>>> x = 5
>>> x
5

>>> _x = 15
>>> _x
15

# Variables cannot start with a number
>>> 1x = 25
SyntaxError: invalid syntax

# Variables can only contain letters, numbers, and underscores
>>> x_1 = 10
>>> x_1
10

>>> x-1 = 20
SyntaxError: invalid syntax

>>> x$ = 20
SyntaxError: invalid syntax

# Variables are case sensitive
>>> x = 5
>>> x

>>> X
NameError: name 'X' is not defined

# Variables cannot be reserved keywords
>>> for = 5
SyntaxError: invalid syntax

>>> True = 5
SyntaxError: invalid syntax

>>> None = 5
SyntaxError: invalid syntax

>>> class = 5
SyntaxError: invalid syntax
```

# Reserved keywords in Python

```python
>>> import keyword
>>> print(keyword.kwlist)
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break',
'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally',
'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal',
'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

### Delete variables

```python
>>> x = 5
>>> x
5

>>> del x
>>> x
NameError: name 'x' is not defined
```

---

Conclusion

In this lesson, you learned how to declare, assign, and delete variables in Python. You also learned about naming conventions for variables and reserved keywords in Python.
