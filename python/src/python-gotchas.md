# python Gotchas

In this article, you will learn about some of the most common Python gotchas. You will also learn how to avoid these gotchas.

## What is a Python Gotcha?

A Python gotcha is a subtle bug in Python that can cause your program to behave unexpectedly. Python gotchas are often caused by the way Python handles certain types of objects. For example, Python gotchas can occur when you use mutable objects as default arguments.

Some of the most common Python gotchas includes:

- Using mutable objects as default arguments
- Integer division
- Variable scoping
- Late binding closures
- String immutability

## Using Mutable Objects as Default Arguments

Python gotchas can occur when you use mutable objects as default arguments. For example, the following code will not work as expected.

```python
def my_function(my_list=[]):
    my_list.append(1)
    print(my_list)

my_function()
my_function()
```

The output of the above code will be:

```python
[1]
[1, 1]
```

This is because the default argument is only evaluated once. This means that the same list object is used every time the function is called. You can avoid this problem by using the `None` keyword as a default argument.

```python
def my_function(my_list=None):
    if my_list is None:
        my_list = []
    my_list.append(1)
    print(my_list)

my_function()
my_function()
```

The output of the above code will be:

```python
[1]
[1]
```

## Integer Division

Python gotchas can also occur when you perform integer division. For example, the following code will not work as expected.

```python
print(5 / 2)
```

The output of the above code will be:

```python
2.5
```

This is because Python 3 performs true division. This means that the `/` operator always returns a float. You can avoid this problem by using the `//` operator.

```python
print(5 // 2)
```

The output of the above code will be:

```python
2
```

## Variable Scoping

Variables defines inside a loop or comprehension can leak into surrounding scopes. For example, the following code will not work as expected.

```python
x = 1

for x in range(5):
    pass

print(x)
```

The output of the above code will be:

```python
4
```

This is because the variable `x` is defined inside the loop. This means that the variable `x` is defined in the surrounding scope. You can avoid this problem by using a different variable name.

```python
x = 1

for y in range(5):
    pass

print(x)
```

The output of the above code will be:

```python
1
```

## Late Binding Closures

In python closures capture the value of variables by name not by value. For example, the following code will not work as expected.

```python
def create_multipliers():
    return [lambda x : i * x for i in range(5)]

for multiplier in create_multipliers():
    print(multiplier(2))
```

The output of the above code will be:

```python
8
8
8
8
8
```

This is because the variable `i` is captured by name. This means that the variable `i` is captured by reference. You can avoid this problem by using a default argument.

```python
def create_multipliers():
    return [lambda x, i=i : i * x for i in range(5)]

for multiplier in create_multipliers():
    print(multiplier(2))
```

The output of the above code will be:

```python
0
2
4
6
8
```

## String Immutability

Strings are immutable in Python. For example, the following code will not work as expected.

```python
my_string = "Hello World"
my_string[0] = "J"
```

The output of the above code will be:

```python
TypeError: 'str' object does not support item assignment
```

This is because strings are immutable. This means that you cannot change the value of a string. You can avoid this problem by using a list instead.

```python
my_string = list("Hello World")
my_string[0] = "J"
print("".join(my_string))
```

The output of the above code will be:

```python
Jello World
```

## Conclusion

In this chapter, you learned about some of the most common Python gotchas. You also learned how to avoid these gotchas.
