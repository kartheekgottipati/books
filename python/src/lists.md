# Lists

Lists are ordered sequences of values. They can contain any type of value, and they can contain duplicate values. Lists are mutable, which means that they can be changed after they are created.

## Creating a list

```python
>>> a = [1, 2, 3]
```

```python
>>> type(a)
<class 'list'>
```

## Updating a list

### Add an item to a list

```python
>>> a = [1, 2, 3]
>>> a.append(4)
```

```python
>>> a
[1, 2, 3, 4]
```

### Change an item in a list

```python
>>> a = [1, 2, 3]
>>> a[0] = 4
```

```python
>>> a
[4, 2, 3]
```

```python
>>> a = [1, 2, 3]
>>> a[0] = [4, 5, 6]
```

```python
>>> a
[[4, 5, 6], 2, 3]
```

```python
>>> a = [1, 2, 3]
>>> a[0] = "Hello World"
```

```python
>>> a
['Hello World', 2, 3]
```

```python
>>> a = [1, 2, 3]
>>> a[0] = True
```

```python
>>> a
[True, 2, 3]
```

```python
>>> a = [1, 2, 3]
>>> a[0] = None
```

```python
>>> a
[None, 2, 3]
```

# Delete an item from a list

```python
>>> a = [1, 2, 3]
>>> del a[0]
```

```python
>>> a
[2, 3]
```

```python
>>> a = [1, 2, 3]
>>> del a[0:2]
```

```python
>>> a
[3]
```

## Remove an item from a list

```python
>>> a = [1, 2, 3]
>>> a.remove(2)
```

```python
>>> a
[1, 3]
```

```python
>>> a = [1, 2, 3]
>>> a.remove(4)
```

```python
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: list.remove(x): x not in list
```

### Pop an item from a list. Remove and return item at index (default last).

```python
>>> a = [1, 2, 3]
>>> a.pop()
3
```

```python
>>> a
[1, 2]
```

### Remove and return item at index 0 (first item).

```python
>>> a = [1, 2, 3]
>>> a.pop(0)
1
```

```python
>>> a = [1, 2, 3]
>>> a.pop(4)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: pop index out of range
```

--------------------------------------------------------------------------------

Conclusion

In this lesson, you learned about lists. You learned that lists are ordered sequences of values. You learned that lists can contain any type of value, and they can contain duplicate values. You learned that lists are mutable, which means that they can be changed after they are created.
