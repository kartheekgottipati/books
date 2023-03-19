# bytearrays

Bytearrays are mutable sequences of integers in the range 0 <= x < 256. They are similar to lists, but they can only contain integers and they are immutable. Bytearrays are mutable, which means that they can be changed after they are created.

```python
>>> a = bytearray(5)
>>> type(a)
<class 'bytearray'>

# Add an item to a bytearray
>>> a = bytearray(5)
>>> a[0] = 1
>>> a
bytearray(b'\x01\x00\x00\x00\x00')

>>> a = bytearray(5)
>>> a[0] = 256
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: byte must be in range(0, 256)

# Change an item in a bytearray
>>> a = bytearray(5)
>>> a[0] = 1
>>> a[0] = 2
>>> a
bytearray(b'\x02\x00\x00\x00\x00')

# Delete an item from a bytearray
>>> a = bytearray(5)
>>> del a[0]
>>> a
bytearray(b'\x00\x00\x00\x00')

# Remove all items from a bytearray
>>> a = bytearray(5)
>>> a.clear()
>>> a
bytearray(b'')
```

---

Conclusion

In this chapter, we learned about bytearrays. Bytearrays are mutable sequences of integers in the range 0 <= x < 256. They are similar to lists, but they can only contain integers and they are immutable. Bytearrays are mutable, which means that they can be changed after they are created.
