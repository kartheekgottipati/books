# Magic Methods

Magic methods are not actually magic. They are special methods which provide syntactic sugar for the corresponding operator. For example, the `+` operator is used to add two numbers. However, we can also use the `__add__()` method to add two numbers. This is an example of magic method.

## `__init__()` Method

Let's see an example of `__init__()` method:

```python
class Car:
    def __init__(self, brand, model, year):
        self.brand = brand
        self.model = model
        self.year = year
```

```python
car = Car('Audi', 'A4', 2016)
```

In the above example, we have defined the `__init__()` method. This method is called when we create a new instance of the `Car` class.

## `__str__()` Method

Let's see an example of `__str__()` method:

```python
class Car:
    def __init__(self, brand, model, year):
        self.brand = brand
        self.model = model
        self.year = year

    def __str__(self):
        return f'{self.brand} {self.model} {self.year}'
```

In the above example, we have defined the `__str__()` method. This method is called when we try to print the object of the `Car` class.

## `__repr__()` Method

Let's see an example of `__repr__()` method:

```python
class Car:
    def __init__(self, brand, model, year):
        self.brand = brand
        self.model = model
        self.year = year

    def __repr__(self):
        return f'{self.brand} {self.model} {self.year}'
```

In the above example, we have defined the `__repr__()` method. This method is called when we try to represent the object of the `Car` class.

## `__add__()` Method

Let's see an example of `__add__()` method:

```python
class Car:
    def __init__(self, brand, model, year):
        self.brand = brand
        self.model = model
        self.year = year

    def __add__(self, other):
        return f'{self.brand} {self.model} {self.year} + {other.brand} {other.model} {other.year}'
```

In the above example, we have defined the `__add__()` method. This method is called when we try to add two objects of the `Car` class.

## `__len__()` Method

Let's see an example of `__len__()` method:

```python
class Car:
    def __init__(self, brand, model, year):
        self.brand = brand
        self.model = model
        self.year = year

    def __len__(self):
        return len(self.brand) + len(self.model) + len(str(self.year))
```

In the above example, we have defined the `__len__()` method. This method is called when we try to get the length of the object of the `Car` class.

For more information about magic methods, you can visit the python documentation at <https://docs.python.org/3/reference/datamodel.html#special-method-names>

--------------------------------------------------------------------------------

Conclusion

In this article, we have learned about magic methods in Python. We have also seen some examples of magic methods including `__init__()` method, `__str__()` method, `__repr__()` method, `__add__()` method, and `__len__()` method.
