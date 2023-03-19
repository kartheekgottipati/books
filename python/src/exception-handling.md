# Exception Handling

Python provides a robust exception handling mechanism that helps in identifying and handling errors that occur during program execution. Exception handling allows programmers to gracefully handle errors and avoid program crashes.

What is an Exception?

An exception is an event that occurs during the execution of a program that disrupts the normal flow of the program's instructions. Exceptions are Python objects that represent errors. When a Python script encounters a situation that it cannot cope with, it raises an exception. An exception is a Python object that represents an error.

When a Python script raises an exception, it must either handle the exception immediately otherwise it terminates and quits.

This chapter will cover the following topics:

- What is an Exception?
- Raising Exceptions
- Handling Exceptions
- The try and except Block
- The try...finally Block
- The raise Statement
- User-defined Exceptions
- Defining Clean-up Actions
- Predefined Clean-up Actions

## What is an Exception?

An exception is an event, which occurs during the execution of a program that disrupts the normal flow of the program's instructions. In general, when a Python script encounters a situation that it cannot cope with, it raises an exception. An exception is a Python object that represents an error.

When a Python script raises an exception, it must either handle the exception immediately otherwise it terminates and quits.

## Raising Exceptions

You can use the raise statement to throw an exception if a condition occurs. The statement can be complemented with a custom exception.

The syntax of the raise statement is as follows:

```python
raise [Exception [, args [, traceback]]]
```

The following example shows how to use the raise statement to throw an exception:

```python
raise NameError('HiThere')
```

## Built-in Exceptions

Python has many built-in exceptions that are raised when your program encounters an error (something in the program goes wrong). When these exceptions occur, the program stops and displays a message. The following table lists some of the exceptions that you might come across while writing Python programs.

| Exception           | Description                                                                   |
| ------------------- | ----------------------------------------------------------------------------- |
| AssertionError      | Raised in case of failure of the Assert statement                             |
| AttributeError      | Raised in case of failure of attribute reference or assignment                |
| IndexError          | Raised when an index is not found in a sequence                               |
| KeyError            | Raised when the specified key is not found in the dictionary                  |
| NotImplementedError | Raised by abstract methods                                                    |
| OSError             | Raised when system operation causes system related error                      |
| SyntaxError         | Raised by parser when syntax error is encountered                             |
| IndentationError    | Raised when there is incorrect indentation                                    |
| SystemExit          | Raised by sys.exit() function                                                 |
| TypeError           | Raised when a function or operation is applied to an object of incorrect type |

Check the [Python documentation](https://docs.python.org/3/library/exceptions.html) for a complete list of built-in exceptions.

## Handling Exceptions with try and except

The try and except block in Python is used to catch and handle exceptions. Python executes code following the try statement as a "normal" part of the program. The code that follows the except statement is the program's response to any exceptions in the preceding try clause.

The syntax of the try and except block is as follows:

```python
try:
   You do your operations here.
   ......................
except ExceptionI:
   If there is ExceptionI, then execute this block.
except ExceptionII:
   If there is ExceptionII, then execute this block.
   ......................
else:
   If there is no exception then execute this block.
```

The try statement works as follows:

- First, the try clause (the statement(s) between the try and except keywords) is executed.

- If no exception occurs, the except clause is skipped and execution of the try statement is finished.

- If an exception occurs during execution of the try clause, the rest of the clause is skipped. Then if its type matches the exception named after the except keyword, the except clause is executed, and then execution continues after the try statement.

- If an exception occurs which does not match the exception named in the except clause, it is passed on to outer try statements; if no handler is found, it is an unhandled exception and execution stops with a message as shown below.

The following example shows how to use the try and except block to handle exceptions:

```python
try:
   fh = open("testfile", "w")
   fh.write("This is my test file for exception handling!!")
except IOError:
   print("Error: can\'t find file or read data")
else:
   print("Written content in the file successfully")
   fh.close()
```

The following example shows how to use the try and except block to handle multiple exceptions:

```python
try:
   fh = open("testfile", "w")
   fh.write("This is my test file for exception handling!!")
except IOError:
   print("Error: can\'t find file or read data")
except:
   print("Error: something else went wrong")
else:
   print("Written content in the file successfully")
   fh.close()
```

## The try...finally Block

The try statement in Python can have an optional finally clause. The finally clause is executed no matter what, and is generally used to release external resources.

The syntax of the try...finally block is as follows:

```python
try:
   You do your operations here.
   ......................
   Due to any exception, this may be skipped.
finally:
   This would always be executed.
```

The following example shows how to use the try...finally block to handle exceptions:

```python
try:
   fh = open("testfile", "w")
   try:
      fh.write("This is my test file for exception handling!!")
   finally:
      print("Going to close the file")
      fh.close()
except IOError:
   print("Error: can\'t find file or read data")
```

## The raise Statement

The raise statement allows the programmer to force a specified exception to occur. For example:

```python
raise NameError('HiThere')
```

The statement can be complemented with a custom exception:

```python
raise ValueError('invalid value: %s' % s)
```

## User-defined Exceptions

Python allows you to create your own exceptions by deriving classes from the built-in exception class. The syntax of the user-defined exception is as follows:

`NOTE:` If you are not familiar with class and object-oriented programming, don't worry. Its convered in the following chapters.

```python
class MyError(Exception):
   """My own exception class

   Attributes:
      msg  -- explanation of the error
   """

   def __init__(self, msg):
      self.msg = msg

   def __str__(self):
      return self.msg
```

The following example shows how to use the user-defined exception:

```python
try:
   raise MyError(2*2)
except MyError as e:
   print('My exception occurred, value:', e.value)
```

## Defining Clean-up Actions

The finally clause is intended to define clean-up actions that must be executed under all circumstances. For example:

```python
try:
   raise KeyboardInterrupt
finally:
   print('Goodbye, world!')
```

## Predefined Clean-up Actions

The with statement allows objects like files to be used in a way that ensures they are always cleaned up promptly and correctly.

The syntax of the with statement is as follows:

```python
with expression [as variable]:
   with-block
```

The following example shows how to use the with statement:

```python
with open("test.txt", encoding = 'utf-8') as f:
   # perform file operations
```

---

Conclusion

In this tutorial, you have learned about exceptions and how to handle them in Python. You have also learned about the try and except block, the raise statement, and user-defined exceptions.
