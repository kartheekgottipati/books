# Control Flow Statements

Control flow statements are used to control the flow of execution of our programs. In this chapter, we will learn about the different control flow statements available in Python. They include

- `break`
- `continue`

## break

The `break` statement is used to exit a loop. It can be used in both `for` and `while` loops. Let's look at an example:

```python
for i in range(6):
    if i == 3:
        break
    print(i)
```

The output of the above program is:

```text
0
1
2
```

In the above program, the `break` statement is used to exit the loop when the value of `i` is `3`. As soon as the value of `i` becomes `3`, the `break` statement is executed, and the loop is exited.

## continue

The `continue` statement is used to skip the current iteration of a loop. It can be used in both `for` and `while` loops. Let's look at an example:

```python
for i in range(6):
    if i == 3:
        continue
    print(i)
```

The output of the above program is:

```text
0
1
2
4
5
```

In the above program, the `continue` statement is used to skip the current iteration of the loop when the value of `i` is `3`. As soon as the value of `i` becomes `3`, the `continue` statement is executed, and the current iteration of the loop is skipped.

---

Conclusion

In this chapter, we learned about the `break` and `continue` statements, which are used to control the flow of execution of a loop. In the next chapter, we will learn about nesting statements, which are used to nest one statement inside another.
