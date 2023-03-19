# String Formatting

String formatting is a way to insert variables into strings. It is a very useful tool for creating dynamic strings. In this article, we will learn about the different ways to format strings in Python.

## String Formatting with %

The `%` operator is used to format a set of variables enclosed in a "tuple" (a fixed size list), together with a format string, which contains normal text together with "argument specifiers", special symbols like `%s` and `%d`.

`NOTE:` You will learn about tuples in the following chapters.

Argument specifiers:

| Specifier               | Description                                                                   |
| ----------------------- | ----------------------------------------------------------------------------- |
| `%s`                    | String (or any object with a string representation, like numbers)             |
| `%d`                    | Integers                                                                      |
| `%f`                    | Floating point numbers                                                        |
| `%.<number of digits>f` | Floating point numbers with a fixed amount of digits to the right of the dot. |
| `%x/%X`                 | Integers in hex representation (lowercase/uppercase)                          |

```python
>>> name = "John"
>>> age = 23
>>> number = 13.579
>>> print("%s is %d years old." % (name, age))
John is 23 years old.

>>> # Floating point numbers with 2 digits to the right of the dot

>>> print("Pi is approximately %.2f." % number)
Pi is approximately 13.58.

>>> # Integers in hex representation

>>> print("Hexadecimal representation of %d is %x." % (number, number))
Hexadecimal representation of 13 is d.

>>> # Integers in hex representation (uppercase)

>>> print("Hexadecimal representation of %d is %X." % (number, number))
Hexadecimal representation of 13 is D.

>>> # Binary representation

>>> print("Binary representation of %d is %s." % (number, bin(number)))
Binary representation of 13 is 0b1101.

>>> # Octal representation

>>> print("Octal representation of %d is %o." % (number, number))
Octal representation of 13 is 15.

>>> # Scientific notation

>>> print("Scientific notation of %d is %e." % (number, number))
Scientific notation of 13 is 1.357900e+01.

>>> # Exponent notation

>>> print("Exponent notation of %d is %E." % (number, number))
Exponent notation of 13 is 1.357900E+01.

>>> # General format

>>> print("General format of %d is %g." % (number, number))
General format of 13 is 13.579.

>>> # General format (exponent notation)

>>> print("General format of %d is %G." % (number, number))
General format of 13 is 13.579.
```

## String Formatting with format()

The `format()` method that is available with the string object is probably the most versatile method for formatting strings. It uses the string format method to format the string. The syntax of the format() method is:

```python
string.format(value1, value2, ...)
```

The format() method formats the specified value(s) and insert them inside the string's placeholder. The placeholder is defined using curly brackets: `{}`. Read more about the format() method [here](https://www.w3schools.com/python/ref_string_format.asp).

```python
>>> name = "John"
>>> age = 23
>>> number = 13.579
>>> print("{} is {} years old.".format(name, age))
John is 23 years old.

>>> # Floating point numbers with 2 digits to the right of the dot

>>> print("Pi is approximately {:.2f}.".format(number))
Pi is approximately 13.58.

>>> # Integers in hex representation

>>> print("Hexadecimal representation of {} is {:X}.".format(number, number))
Hexadecimal representation of 13.579 is 13.579.

>>> # Integers in hex representation (uppercase)

>>> print("Hexadecimal representation of {} is {:X}.".format(number, number))
Hexadecimal representation of 13.579 is D.

>>> # Binary representation

>>> print("Binary representation of {} is {:b}.".format(number, number))
Binary representation of 13.579 is 1101.

>>> # Octal representation

>>> print("Octal representation of {} is {:o}.".format(number, number))
Octal representation of 13.579 is 15.

>>> # Scientific notation

>>> print("Scientific notation of {} is {:e}.".format(number, number))
Scientific notation of 13.579 is 1.357900e+01.

>>> # Exponent notation

>>> print("Exponent notation of {} is {:E}.".format(number, number))
Exponent notation of 13.579 is 1.357900E+01.

>>> # General format

>>> print("General format of {} is {:g}.".format(number, number))
General format of 13.579 is 13.579.

>>> # General format (exponent notation)

>>> print("General format of {} is {:G}.".format(number, number))
General format of 13.579 is 13.579.
```

## String Formatting with f-Strings

Python 3.6 introduced a new way of formatting strings called f-strings. f-strings are string literals that have an f at the beginning and curly braces containing expressions that will be replaced with their values. Read more about f-strings [here](https://www.python.org/dev/peps/pep-0498/).

```python
>>> name = "John"
>>> age = 23
>>> number = 13.579
>>> print(f"{name} is {age} years old.")
John is 23 years old.

>>> # Floating point numbers with 2 digits to the right of the dot

>>> print(f"Pi is approximately {number:.2f}.")
Pi is approximately 13.58.

>>> # Integers in hex representation

>>> print(f"Hexadecimal representation of {number} is {number}.")
Hexadecimal representation of 13.579 is 13.579.

>>> # Integers in hex representation (uppercase)

>>> print(f"Hexadecimal representation of {number} is {number:X}.")
Hexadecimal representation of 13.579 is D.

>>> # Binary representation

>>> print(f"Binary representation of {number} is {number:b}.")
Binary representation of 13.579 is 1101.

>>> # Octal representation

>>> print(f"Octal representation of {number} is {number:o}.")
Octal representation of 13.579 is 15.

>>> # Scientific notation

>>> print(f"Scientific notation of {number} is {number:e}.")
Scientific notation of 13.579 is 1.357900e+01.

>>> # Exponent notation

>>> print(f"Exponent notation of {number} is {number:E}.")
Exponent notation of 13.579 is 1.357900E+01.

>>> # General format

>>> print(f"General format of {number} is {number:g}.")
General format of 13.579 is 13.579.

>>> # General format (exponent notation)

>>> print(f"General format of {number} is {number:G}.")
General format of 13.579 is 13.579.

```

## String Formatting with Template Strings (Advanced)

The `string` module contains a `Template` class that allows you to substitute placeholders with actual values. The syntax of the `Template` class is:

```python
string.Template(template)
```

The `Template` class uses the `$` character as a placeholder. Read more about the `Template` class [here](https://docs.python.org/3/library/string.html#template-strings).

```python

>>> from string import Template
>>> name = "John"
>>> age = 23
>>> number = 13.579
>>> t = Template("$name is $age years old.")
>>> print(t.substitute(name=name, age=age))
John is 23 years old.

>>> # Floating point numbers with 2 digits to the right of the dot

>>> t = Template("Pi is approximately $number:.2f.")
>>> print(t.substitute(number=number))
Pi is approximately 13.58.

>>> # Integers in hex representation

>>> t = Template("Hexadecimal representation of $number is $number.")
>>> print(t.substitute(number=number))

>>> # Integers in hex representation (uppercase)

>>> t = Template("Hexadecimal representation of $number is $number:X.")
>>> print(t.substitute(number=number))

>>> # Binary representation

>>> t = Template("Binary representation of $number is $number:b.")
>>> print(t.substitute(number=number))

>>> # Octal representation

>>> t = Template("Octal representation of $number is $number:o.")
>>> print(t.substitute(number=number))

>>> # Scientific notation

>>> t = Template("Scientific notation of $number is $number:e.")
>>> print(t.substitute(number=number))

>>> # Exponent notation

>>> t = Template("Exponent notation of $number is $number:E.")
>>> print(t.substitute(number=number))

>>> # General format

>>> t = Template("General format of $number is $number:g.")
>>> print(t.substitute(number=number))

>>> # General format (exponent notation)

>>> t = Template("General format of $number is $number:G.")
>>> print(t.substitute(number=number))

```

---

Conclusion

In this tutorial, you learned how to format strings in Python. You learned about the different ways of formatting strings in Python and how to use them. You also learned about the `Template` class and how to use it.
