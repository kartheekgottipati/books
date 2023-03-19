# Loops

Loops are a fundamental concept in programming, allowing you to execute a block of code multiple times. In Python, there are two main types of loops:

- `for` loop
- `while` loop

## for Loop

The `for` loop is used to iterate over a sequence (e.g. a list, a tuple, a dictionary, a set, or a string). The syntax of the `for` loop is as follows:

```python
for item in sequence:
    # block of code
```

The `sequence` is a collection of items (e.g. a list, a tuple, a dictionary, a set, or a string). The `item` is the variable that we use to refer to the items inside the sequence. In each iteration, the `item` takes the value of the next item in the sequence. The block of code inside the `for` loop is executed for each item in the sequence.

Let's look at an example:

```python
for x in [1, 2, 3]:
    print(x)
```

The output of the above program is:

```text
1
2
3
```

```python
for x in "banana":
    print(x)
```

The output of the above program is:

```text
b
a
n
a
n
a
```

```python
for x in range(6):
    print(x)
```

The output of the above program is:

```text
0
1
2
3
4
5
```

## while Loop

The `while` loop is used to execute a block of code as long as a certain condition is met. The syntax of the `while` loop is as follows:

```python
while condition:
    # block of code
```

The `condition` is a boolean expression that evaluates to either `True` or `False`. As long as the `condition` evaluates to `True`, the block of code inside the `while` loop is executed. If the `condition` evaluates to `False`, the block of code inside the `while` loop is skipped.

Let's look at an example:

```python
i = 1
while i < 6:
    print(i)
    i += 1
```

The output of the above program is:

```text
1
2
3
4
5
```

---

Conclusion

In this chapter, we learned about the `for` and `while` loops in Python. We also learned about the `range()` function, which is used to generate a sequence of numbers. In the next chapter, we will learn about the `break` and `continue` statements, which are used to control the flow of execution of a loop.
