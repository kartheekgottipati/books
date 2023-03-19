# Classes and Objects

A class is a blueprint for the object. We can think of class as an sketch of a parrot with labels. It contains all the details about the name, colors, size etc. Based on these descriptions, we can study about the parrot. Here, `parrot` is an object.

A class is a code template for creating objects. Objects have member variables and have behaviour associated with them. In python a class is created by the keyword `class`.

```python
class Parrot:
    pass
```

Here, we use class keyword to define an empty class `Parrot`. From class, we construct instances. An instance is a specific object created from a particular class.

```python
obj = Parrot()
```

Here, `obj` is object of class `Parrot`. It's a new instance of the class and we can access the attributes and methods of the class using the dot operator with object. For example, `obj.name` will access the attribute `name` of the object `obj`.

## Constructors

A constructor is a special type of method (function) which is used to initialize the instance members of the class. It is run as soon as an object of a class is instantiated. The method is useful to do any initialization you want to do with your object.

```python
class Parrot:

    # instance attribute
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # instance method
    def sing(self, song):
        return "{} sings {}".format(self.name, song)

    def dance(self):
        return "{} is now dancing".format(self.name)
```

Here, we have defined the `__init__()` method as a constructor and it takes `name` and `age` as parameters. The `__init__()` method is called the constructor and is always called when an object is created.

The `self` parameter is a reference to the current instance of the class, and is used to access variables that belongs to the class. It does not have to be named `self` , you can call it whatever you like, but it has to be the first parameter of any function in the class.

## Class and Instance Variables

Class variables are variables that are shared among all instances of a class. Class variables are defined within a class but outside any of the class's methods. Class variables are not used as frequently as instance variables are.

Instance variables are variables that are defined inside a method and belongs only to the current instance of a class.

```python
class Parrot:

    # class attribute
    species = "bird"

    # instance attribute
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # instance method
    def sing(self, song):
        return "{} sings {}".format(self.name, song)

    def dance(self):
        return "{} is now dancing".format(self.name)
```

Here, `species` is a class variable whose value is shared among all instances of a this class. This can be accessed as `Parrot.species`. Class variables can be accessed using class name or object name.

`name` and `age` are instance variables. This means that for each instance or object of the class, the `name` and `age` will be different.

## Instance Methods

Instance methods are functions that belong to a class. They are used to define the behaviors of an object. Instance methods take `self` as the first parameter.

```python
class Parrot:

    # class attribute
    species = "bird"

    # instance attribute
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # instance method
    def sing(self, song):
        return "{} sings {}".format(self.name, song)

    def dance(self):
        return "{} is now dancing".format(self.name)
```

Here, we have two instance methods. `sing()` and `dance()` both take `self` as the first parameter. The `self` parameter is a reference to the current instance of the class, and is used to access variables that belongs to the class.

## Class Methods

Class methods are methods that are bound to a class rather than its object. They have the access to the state of the class as it takes a class parameter that points to the class and not the object instance. It can modify a class state that would apply across all the instances of the class. For example, it can modify a class variable that will be applicable to all the instances.

```python
class Parrot:

    # class attribute
    species = "bird"

    # instance attribute
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # instance method
    def sing(self, song):
        return "{} sings {}".format(self.name, song)

    def dance(self):
        return "{} is now dancing".format(self.name)

    # a class method to change the species of all parrots
    @classmethod
    def change_species(cls, new_species):
        cls.species = new_species
```

Here, we have a class method `change_species()`, which takes `cls` as the first parameter. The `cls` parameter is a reference to the current class and is used to access class variables that belongs to the class. We use the `@classmethod` decorator in python to create a class method. We can access the class method using the class name or the object name.

```python
>>> Parrot.change_species("toucan")
>>> Parrot.species
'toucan'
>>> obj = Parrot("Blue", 10)
>>> obj.species
'toucan'
```

## Static Methods

Static methods are methods that are bound to a class rather than its object. They do not require a class instance creation. So, they are not dependent on the state of the object. For example, we use a static method to create a factory function.

```python
class Parrot:

    # class attribute
    species = "bird"

    # instance attribute
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # instance method
    def sing(self, song):
        return "{} sings {}".format(self.name, song)

    def dance(self):
        return "{} is now dancing".format(self.name)

    # a class method to change the species of all parrots
    @classmethod
    def change_species(cls, new_species):
        cls.species = new_species

    # a static method to check if a parrot is adult or not
    @staticmethod
    def is_adult(age):
        return age > 18
```

Here, we have a static method `is_adult()` which is not dependent on the state of the object. We use the `@staticmethod` decorator in python to create a static method. We can access the static method using the class name or the object name.

```python
>>> Parrot.is_adult(22)
True

>>> obj = Parrot("Blue", 10)
>>> obj.is_adult(22)
True
```

---

Conclusion

In this tutorial, we have learned about classes and objects in python. We have also learned about constructors, class variables, instance variables, instance methods, class methods, and static methods.
