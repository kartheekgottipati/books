# Inheritance

Inheritance is a way of creating a new class for using details of an existing class without modifying it. The newly formed class is a derived class (or child class). Similarly, the existing class is a base class (or parent class).

```python
class Bird:

    def __init__(self):
        print("Bird is ready")

    def whoisThis(self):
        print("Bird")

    def swim(self):
        print("Swim faster")


class Penguin(Bird):

        def __init__(self):
            # call super() function
            super().__init__()
            print("Penguin is ready")

        def whoisThis(self):
            print("Penguin")

        def run(self):
            print("Run faster")

peggy = Penguin()

>>> Bird is ready
>>> Penguin is ready

peggy.whoisThis()
>>> Penguin

peggy.swim()
>>> Swim faster
```

Here, we have two classes `Bird` and `Penguin`. We are deriving `Penguin` from `Bird`. So, `Penguin` is the derived class and `Bird` is the base class.

The `__init__()` method of `Penguin` class is used to initialize the `Penguin` class. We use the `super()` function inside `__init__()` method. This is used to give access to the methods and properties of a parent or sibling class.

The `super()` function returns an object that represents the parent class.

## Types of Inheritance supported in Python

- Single Inheritance
- Multiple Inheritance
- Multilevel Inheritance
- Hierarchical Inheritance
- Hybrid Inheritance

### Single Inheritance

In single inheritance, a child class inherits from only one parent class. The syntax for single inheritance is as follows:

```python
class BaseClass:
    Body of base class

class DerivedClass(BaseClass):
    Body of derived class
```

The following is an example of single inheritance:

```python
class Bird:

    def __init__(self):
        print("Bird is ready")

    def whoisThis(self):
        print("Bird")

    def swim(self):
        print("Swim faster")


class Penguin(Bird):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Penguin is ready")

    def whoisThis(self):
        print("Penguin")

    def run(self):
        print("Run faster")

```

### Multiple Inheritance

In multiple inheritance, a child class inherits from multiple parent classes. The syntax for multiple inheritance is as follows:

```python
class BaseClass1:
    Body of base class 1

class BaseClass2:
    Body of base class 2

class DerivedClass(BaseClass1, BaseClass2):
    Body of derived class
```

The following is an example of multiple inheritance:

```python
class Animal:
    def __init__(self):
        print("Animal is ready")

    def whoisThis(self):
        print("Animal")

    def swim(self):
        print("Swim faster")


class Bird:
    def __init__(self):
        print("Bird is ready")

    def whoisThis(self):
        print("Bird")

    def run(self):
        print("Run faster")


class Penguin(Animal, Bird):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Penguin is ready")

    def whoisThis(self):
        print("Penguin")

    def fly(self):
        print("Fly faster")


peggy = Penguin()
>>> Animal is ready
>>> Penguin is ready

peggy.whoisThis()
>>> Penguin

peggy.swim()
>>> Swim faster
```

Order of inheritance matters in multiple inheritance. If the same method is present in both the base classes, the method in the first base class will be called. In the above example, the `__init__()` method of `Animal` class is called, not the `__init__()` method of `Bird` class.

In the above example the `__init__()` method of `Animal` class is called, not the `__init__()` method of `Bird` class.

The `whoisThis()` method is present in both the base classes. So, the `whoisThis()` method of `Animal` class is called, not the `whoisThis()` method of `Bird` class.

The `swim()` method is present in `Animal` class only. So, the `swim()` method of `Animal` class is called.

The `run()` method is present in `Bird` class only. So, the `run()` method of `Bird` class is called.

The `fly()` method is present in `Penguin` class only. So, the `fly()` method of `Penguin` class is called.

### Multilevel Inheritance

In multilevel inheritance, we have a child and grandchild relationship between classes. The syntax for multilevel inheritance is as follows:

```python
class BaseClass:
    Body of base class

class DerivedClass(BaseClass):
    Body of derived class

class SubDerivedClass(DerivedClass):
    Body of sub derived class
```

The following is an example of multilevel inheritance:

```python
class Animal:
    def __init__(self):
        print("Animal is ready")

    def whoisThis(self):
        print("Animal")

    def swim(self):
        print("Swim faster")


class Bird(Animal):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Bird is ready")

    def whoisThis(self):
        print("Bird")

    def run(self):
        print("Run faster")


class Penguin(Bird):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Penguin is ready")

    def whoisThis(self):
        print("Penguin")

    def fly(self):
        print("Fly faster")


peggy = Penguin()
>>> Animal is ready
>>> Bird is ready
>>> Penguin is ready

peggy.whoisThis()
>>> Penguin

peggy.swim()
>>> Swim faster

peggy.run()
>>> Run faster

peggy.fly()
>>> Fly faster
```

Order of inheritance matters in multilevel inheritance. If the same method is present in both the base classes, the method in the first base class will be called. In the above example, the `__init__()` method of `Animal` class is called, not the `__init__()` method of `Bird` class.

In the above example the `__init__()` method of `Animal` class is called, not the `__init__()` method of `Bird` class.

The `whoisThis()` method is present in both the base classes. So, the `whoisThis()` method of `Animal` class is called, not the `whoisThis()` method of `Bird` class.

The `swim()` method is present in `Animal` class only. So, the `swim()` method of `Animal` class is called.

The `run()` method is present in `Bird` class only. So, the `run()` method of `Bird` class is called.

The `fly()` method is present in `Penguin` class only. So, the `fly()` method of `Penguin` class is called.

### Hierarchical Inheritance

In hierarchical inheritance, we have multiple child classes that inherit from a single parent class. The syntax for hierarchical inheritance is as follows:

```python
class BaseClass:
    Body of base class

class DerivedClass1(BaseClass):
    Body of derived class 1

class DerivedClass2(BaseClass):
    Body of derived class 2
```

The following is an example of hierarchical inheritance:

```python
class Animal:
    def __init__(self):
        print("Animal is ready")

    def whoisThis(self):
        print("Animal")

    def swim(self):
        print("Swim faster")


class Bird(Animal):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Bird is ready")

    def whoisThis(self):
        print("Bird")

    def run(self):
        print("Run faster")


class Penguin(Bird):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Penguin is ready")

    def whoisThis(self):
        print("Penguin")

    def fly(self):
        print("Fly faster")


class Snake(Animal):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Snake is ready")

    def whoisThis(self):
        print("Snake")

    def climb(self):
        print("Climb faster")


peggy = Penguin()
>>> Animal is ready
>>> Bird is ready
>>> Penguin is ready

peggy.whoisThis()
>>> Penguin

peggy.swim()
>>> Swim faster

peggy.run()
>>> Run faster

peggy.fly()
>>> Fly faster

kaa = Snake()
>>> Animal is ready

kaa.whoisThis()
>>> Snake

kaa.swim()
>>> Swim faster

kaa.climb()
>>> Climb faster
```

Order of inheritance matters in hierarchical inheritance. If the same method is present in both the base classes, the method in the first base class will be called. In the above example, the `__init__()` method of `Animal` class is called, not the `__init__()` method of `Bird` class.

In the above example the `__init__()` method of `Animal` class is called, not the `__init__()` method of `Bird` class.

The `whoisThis()` method is present in both the base classes. So, the `whoisThis()` method of `Animal` class is called, not the `whoisThis()` method of `Bird` class.

The `swim()` method is present in `Animal` class only. So, the `swim()` method of `Animal` class is called.

The `run()` method is present in `Bird` class only. So, the `run()` method of `Bird` class is called.

The `fly()` method is present in `Penguin` class only. So, the `fly()` method of `Penguin` class is called.

The `climb()` method is present in `Snake` class only. So, the `climb()` method of `Snake` class is called.

### Hybrid Inheritance

In hybrid inheritance, we have multiple inheritance combined with other forms of inheritance. The syntax for hybrid inheritance is as follows:

```python
class BaseClass1:
    Body of base class 1

class BaseClass2:
    Body of base class 2

class DerivedClass(BaseClass1, BaseClass2):
    Body of derived class
```

The following is an example of hybrid inheritance:

```python
class Animal:
    def __init__(self):
        print("Animal is ready")

    def whoisThis(self):
        print("Animal")

    def swim(self):
        print("Swim faster")


class Bird(Animal):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Bird is ready")

    def whoisThis(self):
        print("Bird")

    def run(self):
        print("Run faster")


class Penguin(Bird):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Penguin is ready")

    def whoisThis(self):
        print("Penguin")

    def fly(self):
        print("Fly faster")


class Snake(Animal):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Snake is ready")

    def whoisThis(self):
        print("Snake")

    def climb(self):
        print("Climb faster")


class Parrot(Bird, Snake):
    def __init__(self):
        # call super() function
        super().__init__()
        print("Parrot is ready")

    def whoisThis(self):
        print("Parrot")

    def fly(self):
        print("Fly faster")

    def swim(self):
        print("Swim faster")


peggy = Penguin()
>>> Animal is ready
>>> Bird is ready
>>> Penguin is ready

peggy.whoisThis()
>>> Penguin

peggy.swim()
>>> Swim faster

peggy.run()
>>> Run faster

peggy.fly()
>>> Fly faster

jim = Parrot()
>>> Animal is ready

jim.whoisThis()
>>> Parrot

jim.swim()
>>> Swim faster

jim.run()
>>> Run faster

jim.fly()
>>> Fly faster

jim.climb()
>>> Climb faster
```

In the above example, the `__init__()` method of `Animal` class is called, not the `__init__()` method of `Bird` class.

The `whoisThis()` method is present in both the base classes. So, the `whoisThis()` method of `Animal` class is called, not the `whoisThis()` method of `Bird` class.

The `swim()` method is present in `Animal` class only. So, the `swim()` method of `Animal` class is called.

The `run()` method is present in `Bird` class only. So, the `run()` method of `Bird` class is called.

The `fly()` method is present in `Penguin` class only. So, the `fly()` method of `Penguin` class is called.

The `climb()` method is present in `Snake` class only. So, the `climb()` method of `Snake` class is called.

The `fly()` method is present in `Parrot` class only. So, the `fly()` method of `Parrot` class is called.

The `swim()` method is present in `Parrot` class only. So, the `swim()` method of `Parrot` class is called.

---

Conclusion

In this tutorial, you have learned about inheritance in Python. You have also learned about the different types of inheritance in Python. You have also learned about the syntax for inheritance.
