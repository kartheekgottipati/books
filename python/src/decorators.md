# Decorators

Decorators are a powerful tool in Python that allows us to modify the behavior of a function or a class. They are very helpful in situations where we want to add some extra functionality to an existing code.

In this lesson, we'll learn about decorators and how to use them in Python.

## What are decorators?

Decorators are a design pattern in Python that allows a user to add new functionality to an existing object without modifying its structure. Decorators are usually called before the definition of a function you want to decorate.

Here's an example of a decorator:

```python
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper
```

```python
@my_decorator
def say_whee():
    print("Whee!")
```

```python
say_whee()
```

The output of the above code is:

```bash
Something is happening before the function is called.
Whee!
Something is happening after the function is called.
```

## How do decorators work?

Decorators wrap a function, modifying its behavior. In the example above, the `say_whee()` function is wrapped inside the `wrapper()` function inside the `my_decorator()` function. The `wrapper()` function is the one being called when we call `say_whee()`.

The `wrapper()` function prints a string before and after the original function is called. The `wrapper()` function is defined inside the `my_decorator()` function and then returned. The `my_decorator()` function takes in a function as an argument, puts it inside the `wrapper()` function and returns the `wrapper()` function.

The `@my_decorator` is just a short way of saying `say_whee = my_decorator(say_whee)`.

## Decorating functions with parameters

We can also decorate functions that take parameters. Here's an example:

```python
def decorator_with_arguments(function):
    def wrapper_accepting_arguments(arg1, arg2):
        print("My arguments are: {0}, {1}".format(arg1, arg2))
        function(arg1, arg2)
    return wrapper_accepting_arguments
```

```python
@decorator_with_arguments
def cities(city_one, city_two):
    print("I love {0} and {1}!".format(city_one, city_two))
```

```python
cities("New York", "London")
```

The output of the above code is:

```bash
My arguments are: New York, London
I love New York and London!
```

## Chaining decorators in Python

We can chain multiple decorators in Python. Here's an example:

```python
def decorator_one(func):
    def wrapper():
        print("Decorator one")
        func()
    return wrapper
```

```python
def decorator_two(func):
    def wrapper():
        print("Decorator two")
        func()
    return wrapper
```

```python
@decorator_one
@decorator_two
def say_whee():
    print("Whee!")
```

```python
say_whee()
```

The output of the above code is:

```bash
Decorator one
Decorator two
Whee!
```

## Decorators with parameters

We can also create decorators that take arguments. Here's an example:

```python
def function_repeater(number_of_times):
    def my_decorator(func):
        def wrapper(*args, **kwargs):
            for _ in range(number_of_times):
                func(*args, **kwargs)
        return wrapper
    return my_decorator
```

```python
@function_repeater(number_of_times=3)
def greet(name):
    print(f"Hello {name}")
```

```python
greet("World")
```

The output of the above code is:

```bash
Hello World
Hello World
Hello World
```

## Decorators that take arguments

We can also create decorators that take arguments. Here's an example:

```python
def function_repeater(number_of_times):
    def my_decorator(func):
        def wrapper(*args, **kwargs):
            for _ in range(number_of_times):
                func(*args, **kwargs)
        return wrapper
    return my_decorator
```

```python
@function_repeater(number_of_times=3)
def greet(name):
    print(f"Hello {name}")
```

```python
greet("John")
```

The output of the above code is:

```bash
Hello John
Hello John
Hello John
```

## Popular decorators in Python

There are a few popular decorators in Python that we should know about. Here are some of them:

- @classmethod
- @staticmethod
- @property
- @abstractmethod

### @classmethod

`@classmethod` is a decorator that is used to define a class method. A class method is a method that is bound to a class rather than its object. It doesn't require creation of a class instance, much like staticmethod.

Here's an example:

```python
class Person:
    def __init__(self, first, last):
        self.first = first
        self.last = last

    @classmethod
    def from_string(cls, person_str):
        first, last = person_str.split(" ")
        person = cls(first, last)
        return person
```

```python
person = Person.from_string("John Doe")
print(person.first)
print(person.last)
```

The output of the above code is:

```bash
John
Doe
```

### @staticmethod

`@staticmethod` is a decorator that is used to define a static method. A static method is a method that knows nothing about the class and just deals with the parameters.

Here's an example:

```python
class Person:
    def __init__(self, first, last):
        self.first = first
        self.last = last

    @staticmethod
    def is_string_empty(string):
        return not bool(string and string.strip())
```

```python
print(Person.is_string_empty(" "))
print(Person.is_string_empty("a"))
```

The output of the above code is:

```bash
True
False
```

### @property

`@property` is a decorator that is used to define a property of a class. A property is a class method that looks like an attribute.

Here's an example:

```python
class Person:
    def __init__(self, first, last):
        self.first = first
        self.last = last

    @property
    def full_name(self):
        return f"{self.first} {self.last}"
```

```python
person = Person("John", "Doe")
print(person.full_name)
```

The output of the above code is:

```bash
John Doe
```

### @abstractmethod

`@abstractmethod` is a decorator that is used to define an abstract method. An abstract method is a method that is declared, but contains no implementation. Abstract methods are meant to be implemented by subclasses.

Here's an example:

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

    @abstractmethod
    def perimeter(self):
        pass
```

```python
class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side * self.side

    def perimeter(self):
        return 4 * self.side
```

```python
square = Square(4)
print(square.area())
print(square.perimeter())
```

The output of the above code is:

```bash
16
16
```

In this article, we learned about decorators in Python. We learned about the syntax of decorators, how to create decorators, how to chain decorators, how to create decorators that take arguments, and some popular decorators in Python. We also learned about the `@classmethod`, `@staticmethod`, `@property`, and `@abstractmethod` decorators.
