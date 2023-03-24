# Sets

Sets are a data structure that is used to store a collection of unique items. Sets are unordered, so you cannot access items using an index. Sets are mutable, meaning the content of a set can be altered.

```python
>>> a = {1, 2, 3}
```

```python
>>> type(a)
<class 'set'>
```

## Add an item to a set

```python
>>> a = {1, 2, 3}
>>> a.add(4)
```

```python
>>> a
{1, 2, 3, 4}
```

```python
>>> a = {1, 2, 3}
>>> a.add(1)
```

```python
>>> a
{1, 2, 3}
```

## Remove an item from a set

```python
>>> a = {1, 2, 3}
>>> a.remove(2)
```

```python
>>> a
{1, 3}
```

```python
>>> a = {1, 2, 3}
>>> a.remove(4)
Traceback (most recent call last): File "<stdin>", line 1, in <module>
KeyError: 4</module></stdin>
```

## Remove and return an arbitrary item from a set

```python
>>> a = {1, 2, 3}
>>> a.pop()
1
```

```python
>>> a
{2, 3}
```

```python
>>> a = {1, 2, 3}
```

```python
>>> a.pop()
1
```

```python
>>> a.pop()
2
```

```python
>>> a.pop()
3
```

```python
>>> a.pop()
Traceback (most recent call last): File "<stdin>", line 1, in <module>
KeyError: 'pop from an empty set'</module></stdin>
```

### Remove all items from a set

```python
>>> a = {1, 2, 3}
```

```python
>>> a.clear()
```

```python
>>> a
set()
```

--------------------------------------------------------------------------------

Conclusion

In this article, we learned about `sets` in Python. We learned about the different methods that can be used to manipulate sets. We also learned about the different operations that can be performed on sets. We also learned that sets are unordered, so you cannot access items using an index. sets are mutable, meaning the content of a set can be altered.
