# Frozensets

Frozensets are immutable unordered collections of unique values. They can contain any type of value, but they cannot contain duplicate values. Frozensets are immutable, which means that they cannot be changed after they are created.

```python
>>> a = frozenset([1, 2, 3])
>>> type(a)
<class 'frozenset'>

# Add an item to a frozenset
>>> a = frozenset([1, 2, 3])
>>> a.add(4)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'frozenset' object has no attribute 'add'

# Change an item in a frozenset
>>> a = frozenset([1, 2, 3])
>>> a[0] = 4
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'frozenset' object does not support item assignment

# Delete an item from a frozenset
>>> a = frozenset([1, 2, 3])
>>> del a[0]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'frozenset' object doesn't support item deletion

# Remove all items from a frozenset
>>> a = frozenset([1, 2, 3])
>>> a.clear()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'frozenset' object has no attribute 'clear'
```

---

Conclusion

In this lesson, we learned about `frozensets`. We learned that frozensets are immutable unordered collections of unique values. We learned that frozensets can contain any type of value, but they cannot contain duplicate values. We learned that frozensets are immutable, which means that they cannot be changed after they are created.
