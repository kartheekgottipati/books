# Polymorphism, Encapsulation and Abstraction

## Polymorphism

Polymorphism is an ability (in OOP) to use a common interface for multiple forms (data types). For example, let's assume that we need to color a shape, there are multiple shape options (rectangle, square, circle). However we could use the same method to color any shape. This concept is called Polymorphism.

In Python, Polymorphism lets us define methods in the child class with the same name as defined in their parent class.

### Polymorphism with a Function

Let's see an example of polymorphism with a function:

```python
def add(x, y, z = 0):
    return x + y + z

print(add(2, 3))

print(add(2, 3, 4))
```

In the above example, we have defined the `add()` function that takes two parameters, `x` and `y`. However, we have also defined a default value of `z` as `0`. This means that the `add()` function can take 2 or 3 parameters. This is an example of polymorphism. Polymorphism allows us to define the same method in different ways.

### Polymorphism with a Class

Let's see an example of polymorphism with a class:

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def talk(self):
        raise NotImplementedError("Subclass must implement abstract method")

class Cat(Animal):
    def talk(self):
        return 'Meow!'

class Dog(Animal):
    def talk(self):
        return 'Woof! Woof!'

animals = [Cat('Missy'),
           Cat('Mr. Mistoffelees'),
           Dog('Lassie')]

for animal in animals:
    print(animal.name + ': ' + animal.talk())

# Output:
# Missy: Meow!
# Mr. Mistoffelees: Meow!
# Lassie: Woof! Woof!
```

In the above example, we have defined the `talk()` method in the parent class, `Animal`. However, we have redefined the `talk()` method in the child classes, `Cat` and `Dog`. This is also an example of polymorphism.

## Encapsulation

Encapsulation is an ability to restrict access to methods and variables. This can prevent the data from direct modification which is called encapsulation. In Python, we denote private attributes using underscore as the prefix i.e single `_` or double `__` .

### Single Underscore

Let's see an example of single underscore:

```python
class Car:
    def __init__(self):
        self._brand = None
        self._updateSoftware()

    def drive(self):
        print('driving')

    def _updateSoftware(self):
        print('updating software')

    def get_brand(self):
        return self._brand

    def set_brand(self, brand):
        self._brand = brand

car = Car()
>>> updating software

car.drive()
>>> driving

car.set_brand('Audi')

car.get_brand()
>>> Audi
```

In the above example, we have defined the `_brand` attribute as private. This means that we cannot access it directly. We have to use the `get_brand()` and `set_brand()` methods to access it.

python does not have a concept of private variables. However, by using single underscore, we can achieve the same result. This is just a convention that should be followed by programmers while coding.

### Double Underscore

Let's see an example of double underscore:

```python
class Car:
    def __init__(self):
        self.__brand = None
        self._updateSoftware()

    def drive(self):
        print('driving')

    def _updateSoftware(self):
        print('updating software')

    def get_brand(self):
        return self.__brand

    def set_brand(self, brand):
        self.__brand = brand

car = Car()
>>> updating software

car.drive()
>>> driving

car.set_brand('Audi')

car.get_brand()
>>> Audi

car.__brand
>>> AttributeError: 'Car' object has no attribute '__brand'
```

In the above example, we have defined the `__brand` attribute as private. This means that we cannot access it directly. We have to use the `get_brand()` and `set_brand()` methods to access it.

python does not have a concept of private variables. However, by using double underscore, we can achieve the same result. This is just a convention that should be followed by programmers while coding.

## Abstraction

Abstraction is an ability to hide the internal details and show only functionalities. In Python, we can achieve abstraction by using abstract classes and interfaces.

### Abstract Class

Let's see an example of abstract class:

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def move(self):
        pass

class Human(Animal):

    def move(self):
        print("I can walk and run")

class Snake(Animal):
    pass

raj = Human()
raj.move()

kaa = Snake()
>>> TypeError: Can't instantiate abstract class Snake with abstract methods move
```

In the above example, we have defined the `Animal` class as abstract. This means that we cannot create an instance of `Animal` class. We have to create a child class and implement the abstract methods in it.

---

Conclusion

In this article, we have learned about Polymorphism, Encapsulation and Abstraction in Python.
