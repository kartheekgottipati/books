# Dictionaries

Dictionaries are unordered mappings of keys to values. Dictionary keys must be immutable. This means that they must be a number, string, tuple, or any other immutable type. Lists and dictionaries cannot be used as keys. Dictionary values can be any type of value.

```python
>>> a = {"a": 1, "b": 2, "c": 3}
>>> type(a)
<class 'dict'>

# Add a key-value pair to a dictionary
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["d"] = 4
>>> a
{'a': 1, 'b': 2, 'c': 3, 'd': 4}

# Change a value in a dictionary
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["a"] = 4
>>> a
{'a': 4, 'b': 2, 'c': 3}

>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["a"] = [4, 5, 6]
>>> a
{'a': [4, 5, 6], 'b': 2, 'c': 3}

>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["a"] = "Hello World"
>>> a
{'a': 'Hello World', 'b': 2, 'c': 3}

>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["a"] = True
>>> a
{'a': True, 'b': 2, 'c': 3}

>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["a"] = None
>>> a
{'a': None, 'b': 2, 'c': 3}

# Delete a key-value pair from a dictionary
>>> a = {"a": 1, "b": 2, "c": 3}
>>> del a["a"]
>>> a
{'b': 2, 'c': 3}

>>> a = {"a": 1, "b": 2, "c": 3}
>>> del a["d"]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'd'

# Remove a key-value pair from a dictionary
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a.pop("a")
1
>>> a
{'b': 2, 'c': 3}

>>> a = {"a": 1, "b": 2, "c": 3}
>>> a.pop("d")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'd'

# Remove and return a random key-value pair from a dictionary
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a.popitem()
('c', 3)
>>> a
{'a': 1, 'b': 2}

>>> a = {"a": 1, "b": 2, "c": 3}
>>> a.popitem()
('c', 3)
>>> a.popitem()
('b', 2)
>>> a.popitem()
('a', 1)
>>> a.popitem()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'popitem(): dictionary is empty'

# Remove all key-value pairs from a dictionary
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a.clear()
>>> a
{}
```

---

Conclusion

In this chapter we learned about the different dictionaries in Python. We learned how to create a dictionary, how to add, change, and delete key-value pairs from a dictionary, and how to remove all key-value pairs from a dictionary. We also learned how to remove a random key-value pair from a dictionary. We also learned about the different methods that can be used on dictionaries, that dictionaries are unordered mappings of keys to values, and that dictionary keys must be immutable. Dictionary values can be any type of value. Dictionaries themselves are mutable.
