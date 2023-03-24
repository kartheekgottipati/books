# Functions

## What is a function?

A function is a block of organized, reusable code that is used to perform a single, related action. Functions provide better modularity for your application and a high degree of code reusing. As you already know, Python gives you many built-in functions like `print()`, etc. but you can also create your own functions.

Types of functions:

- Built-in functions - functions that are built into Python.
- User-defined functions - functions defined by the users themselves.

What will be covered in this chapter:

- Defining a function
- Calling a function
- Docstrings
- Function arguments
- Anonymous functions
- The `return` statement
- Scope of variables
- Global vs. local variables
- The `global` statement
- Naming a variable
- Coding style

## Defining a function

You can define functions to provide the required functionality. Here are simple rules to define a function in Python.

- Function blocks begin with the keyword `def` followed by the function name and parentheses ( ( ) ).
- Any input parameters or arguments should be placed within these parentheses. You can also define parameters inside these parentheses.
- The first statement of a function can be an optional statement - the documentation string of the function or docstring.
- The code block within every function starts with a colon (:) and is indented.
- The statement `return [expression]` exits a function, optionally passing back an expression to the caller. A return statement with no arguments is the same as `return None`.

Here is an example function that adds two numbers and returns the result.

```python
def add_numbers(x, y):
    """Add two numbers together"""
    return x + y
```

## Calling a function

To call a function, use the function name followed by parenthesis:

```python
add_numbers(1, 2)
```

## Docstrings

The first string after the function header is called the docstring and is short for documentation string. It is briefly used to explain what a function does. Although optional, documentation is a good programming practice. Unless you can remember what you had for dinner last week, always document your code.

Docstrings can be single or multi-line strings. For multi-line strings, put three quotes in the first line. Everything else should be indented to the same level as the quotes. For example:

```python
def print_max(x, y):
    """Prints the maximum of two numbers.

    The two values must be integers."""
    # convert to integers, if possible
    x = int(x)
    y = int(y)

    if x > y:
        print(x, 'is maximum')
    else:
        print(y, 'is maximum')
```

## Function arguments

You can call functions by using the following types of formal arguments:

- Required arguments
- Keyword arguments
- Default arguments
- Variable-length arguments

### Required arguments

Required arguments are the arguments passed to a function in correct positional order. Here, the number of arguments in the function call should match exactly with the function definition.

```python
def greet(name):
    print("Hello, " + name + ". Good morning!")
```

```python
greet("Paul")
# Output: Hello, Paul. Good morning!
```

```python
greet()
# Output: TypeError: greet() missing 1 required positional argument: 'name'
```

```python
greet("John", "Paul")
# Output: TypeError: greet() takes 1 positional argument but 2 were given
```

### Keyword arguments

Keyword arguments are related to the function calls. When you use keyword arguments in a function call, the caller identifies the arguments by the parameter name.

```python
def greet(name, message):
    print(message + ", " + name + ". Good morning!")
```

```python
greet("Paul", "Hello")
# Output: Hello, Paul. Good morning!
```

```python
greet(message="Hello", name="Paul")
# Output: Hello, Paul. Good morning!
```

```python
greet("Paul")
# Output: TypeError: greet() missing 1 required keyword-only argument: 'message'
```

```python
greet("Paul", "Hello", "Good morning!")
# Output: TypeError: greet() takes 2 positional arguments but 3 were given
```

```python
greet(name="Paul", "Hello")
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet(name="Paul", message="Hello", "Good morning!")
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet("Paul", message="Hello")
# Output: TypeError: greet() got multiple values for argument 'message'
```

```python
greet(name="Paul", message="Hello", name="John")
# Output: TypeError: greet() got multiple values for argument 'name'
```

```python
greet(name="Paul", message="Hello", name="John", message="Good morning!")
# Output: TypeError: greet() got multiple values for argument 'message'
```

## Default arguments

A default argument is an argument that assumes a default value if a value is not provided in the function call for that argument.

```python
def greet(name, message="Hello"):
    print(message + ", " + name + ". Good morning!")
```

```python
greet("Paul")
# Output: Hello, Paul. Good morning!
```

```python
greet("Paul", "Good morning!")
# Output: Good morning!, Paul. Good morning!
```

```python
greet(name="Paul", message="Good morning!")
# Output: Good morning!, Paul. Good morning!
```

```python
greet("Paul", message="Good morning!")
# Output: Good morning!, Paul. Good morning!
```

```python
greet("Paul", "Good morning!", "Hello")
# Output: TypeError: greet() takes from 1 to 2 positional arguments but 3 were given
```

```python
greet("Paul", message="Good morning!", "Hello")
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet("Paul", "Good morning!", message="Hello")
# Output: TypeError: greet() got multiple values for argument 'message'
```

```python
greet("Paul", message="Good morning!", message="Hello")
# Output: TypeError: greet() got multiple values for argument 'message'
```

```python
greet("Paul", "Good morning!", message="Hello", "How are you?")
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet("Paul", "Good morning!", message="Hello", message="How are you?")
# Output: TypeError: greet() got multiple values for argument 'message'
```

```python
greet("Paul", "Good morning!", message="Hello", message="How are you?", "I am fine.")
# Output: SyntaxError: positional argument follows keyword argument
```

## Variable-length arguments

Sometimes, you may need to process a function for more arguments than you specified while defining the function. These arguments are called variable-length arguments and are not named in the function definition, unlike required and default arguments.

```python
def greet(*names):
    for name in names:
        print("Hello, " + name + ". Good morning!")
```

```python
greet("Paul")
# Output: Hello, Paul. Good morning!
```

```python
greet("Paul", "John")
# Output: Hello, Paul. Good morning!
#         Hello, John. Good morning!
```

```python
greet("Paul", "John", "George")
# Output: Hello, Paul. Good morning!
#         Hello, John. Good morning!
#         Hello, George. Good morning!
```

```python
greet()
# Output: TypeError: greet() missing 1 required positional argument: 'names'
```

## Variable-length keyword arguments

You may need to process a function for more keyword arguments than you specified while defining the function. These arguments are called variable-length keyword arguments and are not named in the function definition, unlike required, default, and variable-length arguments.

```python
def greet(**kwargs):
    for key, value in kwargs.items():
        print(key + ": " + value)
```

```python
greet(name="Paul", message="Hello")
# Output: name: Paul
#         message: Hello
```

```python
greet(name="Paul", message="Hello", age="25")
# Output: name: Paul
#         message: Hello
#         age: 25
```

```python
greet()
# Output: TypeError: greet() missing 1 required keyword-only argument: 'kwargs'
```

## Combining positional, keyword, default, and variable-length arguments

```python
greet(name="Paul", message="Hello", "Good morning!")
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet(name="Paul", message="Hello", message="Good morning!")
# Output: TypeError: greet() got multiple values for argument 'message'
```

```python
greet(name="Paul", message="Hello", message="Good morning!", "How are you?")
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet(name="Paul", message="Hello", message="Good morning!", message="How are you?")
# Output: TypeError: greet() got multiple values for argument 'message'
```

```python
greet(name="Paul", message="Hello", message="Good morning!", message="How are you?", "I am fine.")
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet(name="Paul", message="Hello", message="Good morning!", message="How are you?", message="I am fine.")
# Output: TypeError: greet() got multiple values for argument 'message'
```

## Variable length arguments & keyword arguments

```python
def greet(*args, **kwargs):
    for arg in args:
        print(arg)

    for key, value in kwargs:
        print(key + ": " + value)
```

```python
greet("Hello", "Good morning!", name="Paul", message="Hello")
# Output: Hello
#         Good morning!
#         name: Paul
#         message: Hello
```

```python
greet("Hello", "Good morning!", name="Paul", message="Hello", age="25")
# Output: Hello
#         Good morning!
#         name: Paul
#         message: Hello
#         age: 25
```

```python
greet()
# Output: TypeError: greet() missing 1 required positional argument: 'args'
```

```python
greet(name="Paul", message="Hello")
# Output: TypeError: greet() missing 1 required positional argument: 'args'
```

```python
greet(
    "Hello",
    "Good morning!",
    name="Paul",
    message="Hello", "How are you?"
)
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet(
    "Hello",
    "Good morning!",
    name="Paul",
    message="Hello",
    message="How are you?"
)
# Output: TypeError: greet() got multiple values for argument 'message'
```

```python
greet(
    "Hello",
    "Good morning!",
    name="Paul",
    message="Hello",
    message="How are you?", "I am fine."
)
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet(
    "Hello",
    "Good morning!",
    name="Paul",
    message="Hello",
    message="How are you?",
    message="I am fine."
)
# Output: TypeError: greet() got multiple values for argument 'message'
```

```python
greet(
    "Hello",
    "Good morning!",
    name="Paul",
    message="Hello",
    message="How are you?",
    message="I am fine.", "I am fine."
)
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet(
    "Hello", "Good morning!",
    name="Paul",
    message="Hello",
    message="How are you?",
    message="I am fine.",
    message="I am fine."
)
# Output: TypeError: greet() got multiple values for argument 'message'
```

```python
greet(
    "Hello",
    "Good morning!",
    name="Paul",
    message="Hello",
    message="How are you?",
    message="I am fine.",
    message="I am fine.",
    "I am fine."
)
# Output: SyntaxError: positional argument follows keyword argument
```

```python
greet(
    "Hello", "Good morning!",
    name="Paul",
    message="Hello",
    message="How are you?",
    message="I am fine.",
    message="I am fine.",
    message="I am fine."
)
# Output: TypeError: greet() got multiple values for argument 'message'
```

## Lambda functions

Lambda functions are small anonymous functions. A lambda function can take any number of arguments, but can only have one expression.

```python
def add(x, y):
    return x + y
```

```python
print(add(2, 3))
# Output: 5
```

This same function can be written as a lambda function as follows:

```python
add = lambda x, y: x + y
```

```python
print(add(2, 3))
# Output: 5
```

## return statement

The return statement is used to exit a function and go back to the place from where it was called.

```python
def add(x, y):
    return x + y
```

```python
print(add(2, 3))
# Output: 5
```

## Return with no value

If you do not specify the return value, a function returns None.

```python
def add(x, y):
    return
```

```python
print(add(2, 3))
# Output: None
```

## Return multiple values

You can return multiple values from a function using a tuple.

```python
def add_sub(x, y):
    return x + y, x - y
```

```python
add, sub = add_sub(2, 3)
```

```python
print(add)
# Output: 5
```

```python
print(sub)
# Output: -1
```

## Variable scope

A variable is only available from inside the region it is created. This is called scope.

```python
def add(x, y):
    return x + y
```

```python
print(add(2, 3))
# Output: 5
```

```python
print(x)
# Output: NameError: name 'x' is not defined
```

### Global variables

Variables that are created outside of a function (as in all of the examples above) are known as global variables. Global variables can be used by everyone, both inside of functions and outside.

```python
x = 10

def add(y):
    return x + y
```

```python
print(add(3))
# Output: 13
```

```python
print(x)
# Output: 10
```

### Local variables

A variable created inside a function belongs to the local scope of that function, and can only be used inside that function.

```python
def add(x, y):
    z = x + y
    return z
```

```python
print(add(2, 3))
# Output: 5
```

```python
print(z)
# Output: NameError: name 'z' is not defined
```

### Global keyword

Normally, when you create a variable inside a function, that variable is local, and can only be used inside that function.

To create a global variable inside a function, you can use the global keyword.

```python
x = 10

def add(y):
    global x
    x = x + y
    return x
```

```python
print(add(3))
# Output: 13
```

```python
print(x)
# Output: 13
```

### Nonlocal keyword

nonlocal keyword is used to work with variables inside nested functions, where the variable should not belong to the inner function.

```python
def add(x, y):
    def add2(z):
        nonlocal x
        x = x + z
        return x

    print(add2(y))

    return add2(y)
```

```python
print(add(2, 3))
# Output: 5
#         8
```

### The pass statement

function definitions cannot be empty, but if you for some reason have a function definition with no content, put in the pass statement to avoid getting an error.

```python
def add(x, y):
    pass
```

```python
print(add(2, 3))
# Output: None
```

--------------------------------------------------------------------------------

Conclusion

In this tutorial, you have learned about functions in Python. You have learned about the syntax of functions, how to call a function, how to pass arguments to a function, how to return values from a function, how to use lambda functions and variable scope.
