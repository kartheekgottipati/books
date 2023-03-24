# Dictionaries

Dictionaries are unordered mappings of keys to values. Dictionary keys must be immutable. This means that they must be a number, string, tuple, or any other immutable type. Lists and dictionaries cannot be used as keys. Dictionary values can be any type of value.

```python
>>> a = {"a": 1, "b": 2, "c": 3}
```

```python
>>> type(a)
<class 'dict'>
```

## Add a key-value pair to a dictionary

```python
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["d"] = 4
```

```python
>>> a
{'a': 1, 'b': 2, 'c': 3, 'd': 4}
```

## Change a value in a dictionary

```python
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["a"] = 4
```

```python
>>> a
{'a': 4, 'b': 2, 'c': 3}
```

```python
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["a"] = [4, 5, 6]
```

```python
>>> a
{'a': [4, 5, 6], 'b': 2, 'c': 3}
```

```python
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["a"] = "Hello World"
```

```python
>>> a
{'a': 'Hello World', 'b': 2, 'c': 3}
```

```python
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["a"] = True
```

```python
>>> a
{'a': True, 'b': 2, 'c': 3}
```

```python
>>> a = {"a": 1, "b": 2, "c": 3}
>>> a["a"] = None
```

```python
>>> a
{'a': None, 'b': 2, 'c': 3}
```

## Delete a key-value pair from a dictionary

```python
>>> a = {"a": 1, "b": 2, "c": 3}
>>> del a["a"]
```

```python
>>> a
{'b': 2, 'c': 3}
```

```python
>>> a = {"a": 1, "b": 2, "c": 3}
```

```python
>>> del a["d"]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'd'
```

## Remove a key-value pair from a dictionary

```python
>>> a = {"a": 1, "b": 2, "c": 3}
```

```python
>>> a.pop("a")
1
```

```python
>>> a
{'b': 2, 'c': 3}
```

```python
>>> a = {"a": 1, "b": 2, "c": 3}
```

```python
a.pop("d")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'd'
```

## Remove and return a random key-value pair from a dictionary

```python
>>> a = {"a": 1, "b": 2, "c": 3}
```

```python
>>> a.popitem()
('c', 3)
```

```python
>>> a
{'a': 1, 'b': 2}
```

```python
>>> a = {"a": 1, "b": 2, "c": 3}
```

```python
>>> a.popitem()
('c', 3)
```

```python
>>> a.popitem()
('b', 2)
```

```python
>>> a.popitem()
('a', 1)
```

```python
>>> a.popitem()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'popitem(): dictionary is empty'
```

## Remove all key-value pairs from a dictionary

```python
>>> a = {"a": 1, "b": 2, "c": 3}
```

```python
>>> a.clear()
>>> a
{}
```

--------------------------------------------------------------------------------

Conclusion

In this chapter we learned about the different dictionaries in Python. We learned how to create a dictionary, how to add, change, and delete key-value pairs from a dictionary, and how to remove all key-value pairs from a dictionary. We also learned how to remove a random key-value pair from a dictionary. We also learned about the different methods that can be used on dictionaries, that dictionaries are unordered mappings of keys to values, and that dictionary keys must be immutable. Dictionary values can be any type of value. Dictionaries themselves are mutable.
