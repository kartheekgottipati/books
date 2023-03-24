# Variables

In Python, variables are used to store values and data. Think of variables as containers that hold a particular value or set of values. Variables are created using an assignment operator, which assigns a value to a variable.

## Declare a variable and assign it a value

```python
>>> x = 5
>>> x
5
```

## Assign a value to a variable

```python
>>> y = 10.5
>>> y
10.5
```

## Assign a string to a variable

```python
>>> name = "John"
>>> name
"John"
```

## Assign a boolean to a variable

```python
>>> is_active = True
>>> is_active
True
```

## Reassign a variable

```python
>>> x = 6
>>> x
5
```

```python
>>> x = 10
>>> x
10
```

## Assign multiple variables

```python
>>> x, y, name, is_active = 5, 10.5, "John", True
```

```python
>>> x
5
```

```python
>>> y
10.5
```

```python
>>> name
"John"
```

```python
>>> is_active
True
```

## Assign the same value to multiple variables

```python
>>> x = y = name = "John"
>>> x
"John"
```

```python
>>> y
"John"
```

```python
>>> name
"John"
```

## Naming conventions for variables

```python
# Variables can start with a letter or underscore
>>> x = 5
>>> x
5
```

```python
>>> _x = 15
>>> _x
15
```

# Variables cannot start with a number

```python
>>> 1x = 25
SyntaxError: invalid syntax
```

# Variables can only contain letters, numbers, and underscores

```python
>>> x1 = 5
>>> x1
5
```

```python
>>> x_1 = 15
>>> x_1
15
```

```python
>>> x-1 = 25
SyntaxError: invalid syntax
```

# Variables are case sensitive

```python
>>> x = 5
>>> x
5
```

```python
>>> X
NameError: name 'X' is not defined
```

```python
>>> X = 15
>>> X
15
```

# Variables cannot be reserved keywords

```python
>>> for = 5
SyntaxError: invalid syntax
```

```python
>>> True = 5
SyntaxError: invalid syntax
```

```python
>>> None = 5
SyntaxError: invalid syntax
```

```python
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

## Delete variables

```python
>>> x = 5
>>> x
5
```

```python
>>> del x
>>> x
NameError: name 'x' is not defined
```

--------------------------------------------------------------------------------

Conclusion

In this lesson, you learned how to declare, assign, and delete variables in Python. You also learned about naming conventions for variables and reserved keywords in Python.
