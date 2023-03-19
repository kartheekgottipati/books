# Tuples

Tuples are immutable sequences of values. They can contain any type of value, and they can contain duplicate values. Tuples are immutable, which means that they cannot be changed after they are created.

```python
>>> a = (1, 2, 3)
>>> type(a)
<class 'tuple'>

# Change an item in a tuple
>>> a = (1, 2, 3)
>>> a[0] = 4
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment

# Delete an item from a tuple
>>> a = (1, 2, 3)
>>> del a[0]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object doesn't support item deletion

# Remove all items from a tuple
>>> a = (1, 2, 3)
>>> a.clear()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'tuple' object has no attribute 'clear'
```

---

Conclusion

In this Chapter, we learned about `tuples`. We learned that tuples are immutable sequences of values. We learned that tuples can contain any type of value, and they can contain duplicate values. We learned that tuples are immutable, which means that they cannot be changed after they are created.
