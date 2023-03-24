# Bytes

Bytes are immutable sequences of integers in the range 0 <= x < 256\. They are similar to strings, but they can only contain integers and they are immutable. Bytes are immutable, which means that they cannot be changed after they are created.

```python
>>> a = bytes(5)
>>> type(a)
<class 'bytes'>
```

## Add an item to a bytes

```python
>>> a = bytes(5)
>>> a[0] = 1
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'bytes' object does not support item assignment
```

## Change an item in a bytes

```python
>>> a = bytes(5)
>>> a[0] = 1
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'bytes' object does not support item assignment
```

## Delete an item from a bytes

```python
>>> a = bytes(5)
>>> del a[0]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'bytes' object doesn't support item deletion
```

## Remove all items from a bytes

```python
>>> a = bytes(5)
>>> a.clear()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'bytes' object has no attribute 'clear'
```

--------------------------------------------------------------------------------

Conclusion

In this lesson, we learned about `bytes`. We learned that bytes are immutable sequences of integers in the range 0 <= x < 256\. We learned that they are similar to strings, but they can only contain integers and they are immutable. We learned that bytes are immutable, which means that they cannot be changed after they are created.
