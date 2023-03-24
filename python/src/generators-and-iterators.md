# Generators and Iterators

In this section, we'll cover the following topics:

- [Generators](#generators)
- [Iterators](#iterators)

## Generators

Generators are a special kind of function that return an iterable set of items, one at a time, in a special way. Generators are a simple way of creating iterators. All the work we mentioned above are automatically handled by generators in Python.

Here's an example of a generator function:

```python
def countdown():
    i = 5
    while i > 0:
        yield i
        i -= 1
```

```python
for i in countdown():
    print(i)
```

The output of the above code is:

```bash
5
4
3
2
1
```

The `yield` keyword is used like `return`, except the function will return a generator.

## Iterators

An iterator is an object that contains a countable number of values. An iterator is an object that can be iterated upon, meaning that you can traverse through all the values.

Technically, in Python, an iterator is an object which implements the iterator protocol, which consist of the methods `__iter__()` and `__next__()`.

Lists, tuples, dictionaries, and sets are all iterable objects. They are iterable containers which you can get an iterator from.

All these objects have a `iter()` method which is used to get an iterator:

```python
mytuple = ("apple", "banana", "cherry")
myit = iter(mytuple)
```

```python
print(next(myit))
print(next(myit))
print(next(myit))
```

The output of the above code is:

```bash
apple
banana
cherry
```

Even strings are iterable objects, and can return an iterator:

```python
mystr = "banana"
myit = iter(mystr)
```

```python
print(next(myit))
print(next(myit))
print(next(myit))
print(next(myit))
print(next(myit))
print(next(myit))
```

The output of the above code is:

```bash
b
a
n
a
n
a
```

Strings are iterable objects, which contain a sequence of characters:

```python
for x in "banana":
  print(x)
```

The output of the above code is:

```bash
b
a
n
a
n
a
```

In Python, the `for` loop actually creates an iterator object and executes the `next()` method for each loop.

To create an object/class as an iterator you have to implement the methods `__iter__()` and `__next__()` to your object.

As you have learned in the Python Classes/Objects chapter, all classes have a function called `__init__()`, which allows you do some initializing when the object is being created.

The `__iter__()` method acts similar, you can do operations (initializing etc.), but must always return the iterator object itself.

The `__next__()` method also allows you to do operations, and must return the next item in the sequence.

To prevent the iteration to go on forever, we can use the `StopIteration` statement.

In the `__next__()` method, we can add a terminating condition to raise an error if the iteration is done a specified number of times:

```python
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def __next__(self):
    x = self.a
    self.a += 1
    if x > 4:
      raise StopIteration
    return x
```

```python
myclass = MyNumbers()
myiter = iter(myclass)
```

```python
print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
```

The output of the above code is:

```bash
1
2
3
4

Traceback (most recent call last):
  File "main.py", line 18, in <module>
    print(next(myiter))
```

In this section, we have learned about generators and iterators in Python. We have also learned how to create our own iterators using classes and how to use them in for loops.
