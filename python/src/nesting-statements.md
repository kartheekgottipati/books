# Nested Statements

Nested statements are statements that are nested inside other statements. In this chapter, we will learn about the different types of nested statements in Python.

## Nested `if` Statements

Nested `if` statements are `if` statements that are nested inside other `if` statements. Let's look at an example:

```python
if 1 == 1:
    if 2 == 2:
        print("Both conditions are True")
```

The output of the above program is:

```text
Both conditions are True
```

In the above program, the `if` statement is nested inside another `if` statement. The inner `if` statement is executed only if the outer `if` statement is `True`. If the outer `if` statement is `False`, the inner `if` statement is not executed.

## Nested `for` Loops

Nested `for` loops are `for` loops that are nested inside other `for` loops. Let's look at an example:

```python
for i in range(3):
    for j in range(3):
        print(i, j)
```

The output of the above program is:

```text
0 0
0 1
0 2
1 0
1 1
1 2
2 0
2 1
2 2
```

In the above program, the `for` loop is nested inside another `for` loop. The inner `for` loop is executed for each iteration of the outer `for` loop.

## Nested `while` Loops

Nested `while` loops are `while` loops that are nested inside other `while` loops. Let's look at an example:

```python
i = 0
while i < 3:
    j = 0
    while j < 3:
        print(i, j)
        j += 1
    i += 1
```

The output of the above program is:

```text
0 0
0 1
0 2
1 0
1 1
1 2
2 0
2 1
2 2
```

In the above program, the `while` loop is nested inside another `while` loop. The inner `while` loop is executed for each iteration of the outer `while` loop.

---

Conclusion

In this chapter, we learned about nested statements in Python. We learned about nested `if` statements, nested `for` loops, and nested `while` loops.
