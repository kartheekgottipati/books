# Data Types

In this section, we will learn about the different data types in Python. In Python, data types are used to classify and represent various types of data. Understanding data types is crucial to writing efficient and error-free code. Python has several built-in data types that include:

## Numbers

In Python, numbers are immutable data types, which means that the value of a number object cannot be changed once it has been assigned. Python supports the following types of numbers:

### Integers

Integers are whole numbers that can be either positive or negative. In Python, integers are represented by the `int` class. Integers can be represented in decimal (base 10), binary (base 2), octal (base 8), or hexadecimal (base 16) form. The following are examples of integers in Python:

```python
# Decimal
num = 10
```

```python
# Binary
num = 0b1010
```

```python
# Octal
num = 0o12
```

```python
# Hexadecimal
num = 0xA
```

### Floats

Floats are numbers that have a decimal point in them. In Python, floats are represented by the `float` class. Floats can be represented in decimal (base 10), binary (base 2), octal (base 8), or hexadecimal (base 16) form. The following are examples of floats in Python:

```python
# Decimal
num = 10.5
```

```python
# Binary
num = 0b1010.1
```

```python
# Octal
num = 0o12.4
```

```python
# Hexadecimal
num = 0xA.8
```

### Complex Numbers

Complex numbers are numbers that have a real part and an imaginary part. In Python, complex numbers are represented by the `complex` class. Complex numbers can be represented in decimal (base 10), binary (base 2), octal (base 8), or hexadecimal (base 16) form. The following are examples of complex numbers in Python:

```python
# Decimal
num = 10 + 5j
```

```python
# Binary
num = 0b1010 + 0b101j
```

```python
# Octal
num = 0o12 + 0o5j
```

```python
# Hexadecimal
num = 0xA + 0x5j
```

## Booleans

Booleans are data types that can have one of two values: `True` or `False`. In Python, booleans are represented by the `bool` class. The following are examples of booleans in Python:

```python
# Boolean
is_true = True
is_false = False
```

## Strings

Strings are sequences of characters. In Python, strings are represented by the `str` class. Strings can be enclosed in single quotes (`'`) or double quotes (`"`). The following are examples of strings in Python:

### String creation

```python
# Single quotes
string = 'Hello World!'
```

```python
# Double quotes
string = "Hello World!"
```

```python
# Triple quotes
string = '''Hello World!'''
```

```python
# Triple quotes
string = """Hello World!"""
```

### String escape characters

```python
# Escape characters
string = 'Hello\nWorld!'
```

# Raw strings

```python
# Raw strings are strings that have a r or R prefix. Raw strings ignore escape characters.
string = r'Hello\nWorld!'
```

# Unicode strings

```python
# Unicode strings are strings that have a u or U prefix. Unicode strings are encoded in UTF-8.
string = u'Hello World!'
```

# Byte strings

```python
# Byte strings are strings that have a b or B prefix. Byte strings are encoded in ASCII.
string = b'Hello World!'
```

## String concatenation

String concatenation is the process of combining two or more strings into a single string. Strings can be concatenated using the `+` operator. The following is an example of string concatenation in Python:

```python
my_string = 'Hello' + ' ' + 'World!'
my_string
```

--------------------------------------------------------------------------------

Conclusion

In this section, we learned about the different data types in Python. In the next section, we will learn about the different operators we can perform on data types in Python.
