# Lists

Lists are ordered sequences of values. They can contain any type of value, and they can contain duplicate values. Lists are mutable, which means that they can be changed after they are created.

```python
>>> a = [1, 2, 3]
>>> type(a)
<class 'list'>

# Add an item to a list
>>> a = [1, 2, 3]
>>> a.append(4)
>>> a
[1, 2, 3, 4]

# Change an item in a list
>>> a = [1, 2, 3]
>>> a[0] = 4
>>> a
[4, 2, 3]

>>> a = [1, 2, 3]
>>> a[0] = [4, 5, 6]
>>> a
[[4, 5, 6], 2, 3]

>>> a = [1, 2, 3]
>>> a[0] = "Hello World"
>>> a
['Hello World', 2, 3]

>>> a = [1, 2, 3]
>>> a[0] = True
>>> a
[True, 2, 3]

>>> a = [1, 2, 3]
>>> a[0] = None
>>> a
[None, 2, 3]

# Delete an item from a list
>>> a = [1, 2, 3]
>>> del a[0]
>>> a
[2, 3]

>>> a = [1, 2, 3]
>>> del a[0:2]
>>> a
[3]

# Remove an item from a list
>>> a = [1, 2, 3]
>>> a.remove(2)
>>> a
[1, 3]

>>> a = [1, 2, 3]
>>> a.remove(4)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: list.remove(x): x not in list

# Pop an item from a list. Remove and return item at index (default last).
>>> a = [1, 2, 3]
>>> a.pop()
3
>>> a
[1, 2]

# Remove and return item at index 0 (first item).
>>> a = [1, 2, 3]
>>> a.pop(0)
1

>>> a = [1, 2, 3]
>>> a.pop(4)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: pop index out of range
```

---

Conclusion

In this lesson, you learned about lists. You learned that lists are ordered sequences of values. You learned that lists can contain any type of value, and they can contain duplicate values. You learned that lists are mutable, which means that they can be changed after they are created.
