# Conditional Statements

Conditional statements are used to control the flow of execution of a program. They allow us to execute a block of code only if a certain condition is met. In Python, we have the following conditional statements:

- `if` statement
- `if-else` statement
- `if-elif-else` statement

## if Statement

The `if` statement is used to execute a block of code only if a certain condition is met. The syntax of the `if` statement is as follows:

```python
if condition:
    # block of code
```

The `condition` is a boolean expression that evaluates to either `True` or `False`. If the `condition` evaluates to `True`, the block of code inside the `if` statement is executed. If the `condition` evaluates to `False`, the block of code inside the `if` statement is skipped.

Let's look at an example:

```python
if 5 > 2:
    print("Five is greater than two!")
```

The output of the above program is:

```text
Five is greater than two!
```

## if-else Statement

The `if-else` statement is used to execute a block of code if a certain condition is met. If the condition is not met, another block of code is executed. The syntax of the `if-else` statement is as follows:

```python
if condition:
    # block of code
else:
    # block of code
```

The `condition` is a boolean expression that evaluates to either `True` or `False`. If the `condition` evaluates to `True`, the block of code inside the `if` statement is executed. If the `condition` evaluates to `False`, the block of code inside the `else` statement is executed.

Let's look at an example:

```python
if 5 > 2:
    print("Five is greater than two!")
else:
    print("Five is not greater than two!")
```

The output of the above program is:

```text
Five is greater than two!
```

## if-elif-else Statement

The `if-elif-else` statement is used to execute a block of code if a certain condition is met. If the condition is not met, another block of code is executed. The syntax of the `if-elif-else` statement is as follows:

```python
if condition:
    # block of code
elif condition:
    # block of code
else:
    # block of code
```

The `condition` is a boolean expression that evaluates to either `True` or `False`. If the `condition` evaluates to `True`, the block of code inside the `if` statement is executed. If the `condition` evaluates to `False`, the block of code inside the `elif` statement is executed. If none of the conditions evaluate to `True`, the block of code inside the `else` statement is executed.

Let's look at an example:

```python
if 5 > 2:
    print("Five is greater than two!")
elif 5 == 2:
    print("Five is equal to two!")
else:
    print("Five is not greater than two!")
```

The output of the above program is:

```text
Five is greater than two!
```

---

Conclusion

In this section, we learned about the different control structures available in Python. We learned about the `if`, `if-else`, and `if-elif-else` statements.
