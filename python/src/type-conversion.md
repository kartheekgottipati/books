# Type Conversion

Python is a dynamically typed language. This means that you don't need to declare the type of a variable when you create it. The type is inferred from the value you assign to it. This is a powerful feature of Python, but it can also lead to some confusion. For example, what happens when you try to add a string and an integer?

```python
>>> 1 + '1'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

The error message tells us that we can't add an integer and a string. But what if we want to add them? We can convert the integer to a string using the `str` function.

```python
>>> str(1) + '1'
'11'
```

We can also convert a string to an integer using the `int` function.

```python
>>> int('1') + 1
2
```

The `int` function will only work if the string contains a valid integer. If it doesn't, it will raise an error.

```python
>>> int('1.1')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '1.1'
```

We can also convert a string to a float using the `float` function.

```python
>>> float('1.1') + 1
2.1
```

The `float` function will only work if the string contains a valid float. If it doesn't, it will raise an error.

```python
>>> float('1')
1.0
```

There are two types of type conversions:

- implicit
- explicit

Implicit type conversions happen automatically. For example, when we add an integer and a float, the integer is converted to a float.

```python
>>> 1 + 1.0
2.0

>>> 1.0 + 1
2.0
```

Explicit type conversions happen when we call a type conversion function like `int`, `float`, or `str`. Explicit type conversions are useful when we want to convert a value to a specific type.

We can convert a float to an integer using the `int` function.

```python
>>> int(1.0)
1
```

We can convert an integer to a float using the `float` function.

```python
>>> float(1)
1.0
```

We can convert an integer to a string using the `str` function.

```python
>>> str(1)
'1'
```

We can convert a string to an integer using the `int` function.

```python
>>> int('1')
1
```

We can convert a string to a float using the `float` function.

```python
>>> float('1.0')
1.0
```

We can convert a float to a string using the `str` function.

```python
>>> str(1.0)
'1.0'
```

We can convert a string to an integer using the `int` function.

```python
>>> int('1.0')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '1.0'
```

We can convert a string to a float using the `float` function.

```python
>>> float('1')
1.0
```

We can convert a int to a string using the `str` function.

```python
>>> str(1)
'1'
```

We can not convert a string to an integer using the `int` function if the string contains a decimal point.

```python
>>> int('1.0')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '1.0'
```

We can convert a string to a float using the `float` function.

```python
>>> float('1.0')
1.0
```

We can convert a float to a string using the `str` function.

```python
>>> str(1.0)
'1.0'
```

Type conversion is an important concept in programming because it allows you to perform operations on data types that are not compatible. Without type conversion, you would be limited in the types of operations you can perform on your data.

However, it is important to use type conversion carefully and appropriately. Improper use of type conversion can lead to unexpected results or errors in your code. It is important to ensure that the data type you are converting to is appropriate for the operation you are trying to perform.

--------------------------------------------------------------------------------

Conclusion

In this lesson, we learned about type conversion. We learned that Python is a dynamically typed language, which means that we don't need to declare the type of a variable when we create it. We also learned that we can convert a value to a different type using type conversion functions like `int`, `float`, and `str`. We learned that there are two types of type conversions: implicit and explicit. We also learned that it is important to use type conversion carefully and appropriately.
