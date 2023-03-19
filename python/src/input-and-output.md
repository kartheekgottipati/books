# Input and Output

In programming, input and output are the two most important things. In this chapter, we will learn how to take input from the user and display output to the user, how to read from a file and write to a files.

## Taking Input from the User

In Python, we can take input from the user using the `input()` function. The `input()` function takes a string as an argument and displays it to the user. The user can then enter a value and press the Enter key. The value entered by the user is returned by the `input()` function.

```python
name = input("Enter your name: ")
>>> Enter your name: John
print("Hello, " + name)
>>> Hello, John
```

The `input()` function always returns a string. If you want to take an integer as input, you have to convert it to an integer using the `int()` function.

```python
age = int(input("Enter your age: "))
>>> Enter your age: 20
print("You are " + age + " years old.")
>>> You are 20 years old.
```

## Displaying Output to the User

In Python, we can display output to the user using the `print()` function. The `print()` function takes a string as an argument and displays it to the user.

```python
print("Hello, World!")
>>> Hello, World!
```

### Displaying Output on the Same Line

By default, the `print()` function displays the output on a new line. If you want to display the output on the same line, you can use the `end` parameter of the `print()` function.

```python
print("Hello", end = " ")
print("World")
>>> Hello World
```

### Displaying Output With a Separator

By default, the `print()` function displays the output with a space between each argument. If you want to display the output with a different separator, you can use the `sep` parameter of the `print()` function.

```python
print("Hello", "World", sep = "-")
>>> Hello-World
```

### Displaying Output With flush

By default, the `print()` function displays the output in the buffer. If you want to display the output immediately, you can use the `flush` parameter of the `print()` function.

```python
print("Hello", flush = True)
>>> Hello
```

## Reading from a File

In Python, we can read from a file using the `open()` function. The `open()` function takes two arguments: the name of the file and the mode. The mode can be either `r` for reading, `w` for writing, or `a` for appending. The `open()` function returns a file object, also called a handle, as it is used to read or modify the file accordingly.

```python
file = open("file.txt", "r")
```

### Reading the Entire File

To read the entire file, we can use the `read()` method of the file object.

```python
file = open("file.txt", "r")
file.read()
```

### Reading a Single Line

To read a single line from the file, we can use the `readline()` method of the file object.

```python
file = open("file.txt", "r")
file.readline()
```

### Reading Multiple Lines

To read multiple lines from the file, we can use the `readlines()` method of the file object.

```python
file = open("file.txt", "r")
file.readlines()
```

### Reading a File Line by Line

To read a file line by line, we can use a for loop. In this case, we don't have to call the `readline()` method explicitly. The for loop automatically calls the `readline()` method to get the next line.

```python
file = open("file.txt", "r")
for line in file:
    print(line)
```

### Reading a File with encoding

To read a file with encoding, we can use the `encoding` parameter of the `open()` function.

```python
file = open("file.txt", "r", encoding="utf-8")

file.read()
```

## Writing to a File

In Python, we can write to a file using the `open()` function. The `open()` function takes two arguments: the name of the file and the mode. The mode can be either `r` for reading, `w` for writing, or `a` for appending. The `open()` function returns a file object, also called a handle, as it is used to read or modify the file accordingly.

```python
file = open("file.txt", "w")

file.write("Hello, World!")
```

### Writing Multiple Lines

To write multiple lines to the file, we can use the `writelines()` method of the file object.

```python
file = open("file.txt", "w")

file.writelines(["Hello, World!", "Hello, World!"])
```

### Writing a File with encoding

To write to a file with encoding, we can use the `encoding` parameter of the `open()` function.

```python
file = open("file.txt", "w", encoding="utf-8")

file.write("Hello, World!")
```

## Appending to a File

In Python, we can append to a file using the `open()` function. The `open()` function takes two arguments: the name of the file and the mode. The mode can be either `r` for reading, `w` for writing, or `a` for appending. The `open()` function returns a file object, also called a handle, as it is used to read or modify the file accordingly.

```python
file = open("file.txt", "a")

file.write("Hello, World!")
```

### Appending Multiple Lines

To append multiple lines to the file, we can use the `writelines()` method of the file object.

```python
file = open("file.txt", "a")

file.writelines(["Hello, World!", "Hello, World!"])
```

### Appending a File with encoding

To append to a file with encoding, we can use the `encoding` parameter of the `open()` function.

```python
file = open("file.txt", "a", encoding="utf-8")

file.write("Hello, World!")
```

## Closing a File

In Python, we can close a file using the `close()` method of the file object.

```python
file = open("file.txt", "r")

file.close()
```

## Handling Exceptions

In Python, we can handle exceptions using the `try` and `except` keywords. The `try` block lets you test a block of code for errors. The `except` block lets you handle the error. The `finally` block lets you execute code, regardless of the result of the try- and except blocks.

```python
try:
    file = open("file.txt", "r")
except FileNotFoundError:
    print("File not found.")
except PermissionError:
    print("You don't have permission to access this file.")
except IOError:
    print("An I/O error occurred.")
except ValueError:
    print("Invalid value.")
except:
    print("An unexpected error occurred.")
finally:
    file.close()
```

## Context Managers

In Python, we can use context managers to automatically close a file after we are done using it. The `with` statement automatically closes the file after the nested block of code is executed.

```python
with open("file.txt", "r", encoding="utf-8") as file:
    file.read()
```

---

Conclusion

In this tutorial, we learned taking input from user, display output to the user, how to read and write to files in Python. We also learned how to handle exceptions and use context managers.
