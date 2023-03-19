# Debugging and Testing

## Debugging

Debugging is the process of finding and resolving defects or problems within a computer program that prevent correct operation of computer software or a system.

### Debugging using print statements

The simplest way to debug your code is to use `print` statements. You can use `print` statements to print the value of variables at different points in your code to see how they change over time. You can also use `print` statements to print the output of function calls to see if they return the correct values.

```python
def sum_of_squares(x, y, z):
    x_squared = x * x
    y_squared = y * y
    z_squared = z * z
    sum = x_squared + y_squared + z_squared
    return sum

result = sum_of_squares(1, 2, 3)
print(result)
```

When you run the program, it will print the result of the `sum_of_squares` function call.

```bash
14
```

### Debugging in built-in pdb debugger

Python has a built-in debugger called `pdb` that you can use to debug your code. To use the debugger, you must first import the `pdb` module and then create a `Pdb` instance. You can then set a _breakpoint_ on a line of code by calling the `set_trace()` method of the `Pdb` instance. When the program execution reaches the line with the breakpoint, it will pause and allow you to inspect the current state of the program.

```python
import pdb

x = [1, 3, 4]
y = 2
z = 3

result_one = y + z

pdb.set_trace()

result_two = y + x
```

When you run the program, it will pause at the line with the breakpoint and allow you to inspect the current state of the program. You can use the `l` (list) command to view the code on the current line and the surrounding lines. You can use the `n` (next) command to execute the next line of code. You can use the `p` (print) command to print the value of a variable. You can use the `c` (continue) command to finish debugging and continue the program execution.

```bash
> python3 debug.py
--Return--
> /home/ccuser/workspace/debug.py(10)<module>()->None
-> pdb.set_trace()
(Pdb) l
  5  	z = 3
  6
  7  	result_one = y + z
  8
  9  	pdb.set_trace()
 10  ->
 11  	result_two = y + x
[EOF]
(Pdb) n
> /home/ccuser/workspace/debug.py(11)<module>()->None
-> result_two = y + x
(Pdb) n
--Return--
> /home/ccuser/workspace/debug.py(11)<module>()->None
-> result_two = y + x
(Pdb) p x
[1, 3, 4]
(Pdb) p y
2
(Pdb) c
```

### Debugging using logging

The `logging` module in Python allows you to log messages at different levels of severity. You can use the `logging` module to log messages to a file or to the console. You can also use the `logging` module to log messages at different levels of severity, such as `DEBUG`, `INFO`, `WARNING`, `ERROR`, and `CRITICAL`.

```python
import logging

logging.basicConfig(filename='example.log', level=logging.DEBUG)
logging.debug('This message should go to the log file')
logging.info('So should this')
logging.warning('And this, too')
```

When you run the program, it will log the messages to the `example.log` file.

```bash
DEBUG:root:This message should go to the log file
INFO:root:So should this
WARNING:root:And this, too
```

## Testing

Testing is the process of running a program or application with the intent of finding software bugs. There are many different types of software testing, including unit testing, integration testing, and end-to-end testing.

### Unit testing

Unit testing is a type of software testing where individual units or components of a software are tested. The purpose of unit testing is to validate that each unit of the software performs as designed. A unit is the smallest testable part of any software. It usually has one or a few inputs and usually a single output. A unit test should focus on only one test case at a time. It is a method by which individual units of source code are tested to determine whether they are fit for use.

### Unit testing in Python

Python has a built-in `unittest` module that you can use to write unit tests. The `unittest` module provides a rich set of tools for constructing and running tests. You can use the `unittest` module to create test cases by subclassing the `unittest.TestCase` class. You can then define methods on the test case class prefixed with `test_` to define the test cases. You can use the `assertEqual()` method to assert that the expected output matches the actual output.

```python
import unittest

def sum_of_squares(x, y, z):
    x_squared = x * x
    y_squared = y * y
    z_squared = z * z
    sum = x_squared + y_squared + z_squared
    return sum

class TestSumOfSquares(unittest.TestCase):
    def test_sum_of_squares(self):
        result = sum_of_squares(1, 2, 3)
        self.assertEqual(result, 14)

if __name__ == '__main__':
    unittest.main()
```

When you run the program, it will run the unit tests and print the results.

```bash
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK
```

### Integration testing

Integration testing is a type of software testing where individual units or components are combined and tested as a group. The purpose of integration testing is to expose faults in the interaction between integrated components. Integration testing takes as its input modules that have been unit tested, groups them in larger aggregates, applies tests defined in an integration test plan to those aggregates, and delivers as its output the integrated system ready for system testing.

In python you can use the `unittest` library or third party libraries like `pytest` to write integration tests. Here's an example of how you can use the `unittest` library to write integration tests.

```python
import unittest
from my_app import Calculator

class TestCalculatorIntegration(unittest.TestCase):

    def setUp(self):
        self.calculator = Calculator()

    def test_add_and_subtract(self):
        self.calculator.add(2)
        self.calculator.add(3)
        self.calculator.subtract(3)
        result = self.calculator.value
        self.assertEqual(result, 2)

if __name__ == '__main__':
    unittest.main()
```

### End-to-end testing

End-to-end testing is a type of software testing where the software is tested as a whole. The purpose of end-to-end testing is to test whether the flow of an application from start to finish works as designed. End-to-end testing is also known as application testing, system testing, or black-box testing.

In python you can use tools like `selenium`, `playwright` or `pyppeteer` to write end-to-end tests. Here's an example of how you can use the `selenium` library to write end-to-end tests.

```python
import unittest
from selenium import webdriver

class TestWebAppEndToEnd(unittest.TestCase):

    def setUp(self):
        self.driver = webdriver.Firefox()

    def test_home_page(self):
        self.driver.get("https://www.example.com")

        # Check if the title is correct
        self.assertEqual(self.driver.title, "Example Website")

        # Check if a specific element is present
        element = self.driver.find_element_by_id("example_element")
        self.assertIsNotNone(element)

    def tearDown(self):
        self.driver.quit()

if __name__ == "__main__":
    unittest.main()
```

In this lesson, you learned about the different types of bebugging and testing techniques that you can use to debug and test your Python code. You also learned about the different types of software testing, including unit testing, integration testing, and end-to-end testing. You also learned about the different tools that you can use to write unit tests and end-to-end tests in Python.
