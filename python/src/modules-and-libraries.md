# Modules and Libraries

## What are modules and why are they important?

Modules are files that contain Python code. They can be imported into other files to make use of the code contained within them. Modules are important because they allow you to reuse code that you have already written. This is especially useful when you are working on a large project and need to use the same code in multiple places.

### Importing and using modules

To import a module, use the `import` keyword. For example, to import the `math` module, you would write:

```python
import math
```

This will import the `math` module and allow you to use it in your code. To use a function from the `math` module, you would write:

```python
math.sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

### Importing specific functions from a module

You can also import specific functions from a module. For example, to import the `sqrt` function from the `math` module, you would write:

```python
from math import sqrt
```

This will import the `sqrt` function from the `math` module and allow you to use it in your code. To use the `sqrt` function, you would write:

```python
sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

### Importing all functions from a module

You can also import all functions from a module. For example, to import all functions from the `math` module, you would write:

```python
from math import *
```

This will import all functions from the `math` module and allow you to use them in your code. To use a function from the `math` module, you would write:

```python
sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

### Importing a module using an alias

You can also import a module using an alias. For example, to import the `math` module using the alias `m`, you would write:

```python
import math as m
```

This will import the `math` module and allow you to use it in your code. To use a function from the `math` module, you would write:

```python
m.sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

### Importing a module using a relative path

You can also import a module using a relative path. For example, if you have a file called `main.py` and a file called `math.py` in the same directory, you can import the `math` module into the `main` module using the following code:

```python
from . import math
```

This will import the `math` module and allow you to use it in your code. To use a function from the `math` module, you would write:

```python
math.sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

### Importing a module using an absolute path

You can also import a module using an absolute path. For example, if you have a file called `main.py` and a file called `math.py` in the same directory, you can import the `math` module into the `main` module using the following code:

```python
from main import math
```

This will import the `math` module and allow you to use it in your code. To use a function from the `math` module, you would write:

```python
math.sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

### Importing a module using a relative path and an alias

You can also import a module using a relative path and an alias. For example, if you have a file called `main.py` and a file called `math.py` in the same directory, you can import the `math` module into the `main` module using the following code:

```python
from . import math as m
```

This will import the `math` module and allow you to use it in your code. To use a function from the `math` module, you would write:

```python
m.sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

### Importing a module using an absolute path and an alias

You can also import a module using an absolute path and an alias. For example, if you have a file called `main.py` and a file called `math.py` in the same directory, you can import the `math` module into the `main` module using the following code:

```python
from main import math as m
```

This will import the `math` module and allow you to use it in your code. To use a function from the `math` module, you would write:

```python
m.sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

## What are libraries and why are they important?

Libraries are collections of modules. They are important because they allow you to reuse code that you have already written. This is especially useful when you are working on a large project and need to use the same code in multiple places.

Examples of libraries include:

- [NumPy](https://numpy.org/)
- [Pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/)
- [SciPy](https://www.scipy.org/)

### Importing and using libraries

To import a library, use the `import` keyword. For example, to import the `numpy` library, you would write:

```python
import numpy
```

This will import the `numpy` library and allow you to use it in your code. To use a function from the `numpy` library, you would write:

```python
numpy.sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

### Importing specific functions from a library

You can also import specific functions from a library. For example, to import the `sqrt` function from the `numpy` library, you would write:

```python
from numpy import sqrt
```

This will import the `sqrt` function from the `numpy` library and allow you to use it in your code. To use the `sqrt` function, you would write:

```python
sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

### Importing all functions from a library

You can also import all functions from a library. For example, to import all functions from the `numpy` library, you would write:

```python
from numpy import *
```

This will import all functions from the `numpy` library and allow you to use them in your code. To use a function from the `numpy` library, you would write:

```python
sqrt(4)
```

This will return `2.0`, which is the square root of `4`.

In this section, you learned about modules and libraries. You also learned how to import modules and libraries into your code.

## Commonly used modules and libraries in Python

In this section, you will learn about some of the most commonly used modules in Python.

- [Math](#math)
- [Random](#random)
- [Datetime](#datetime)
- [OS](#os)
- [Sys](#sys)
- [Re](#re)

In this section, you will learn about some of the most commonly used libraries in Python.

- [NumPy](#numpy)
- [Pandas](#pandas)
- [Matplotlib](#matplotlib)
- [SciPy](#scipy)

## Creating modules and packages

In this section, you will learn how to create your own modules and packages.

### Creating a module

To create a module, you need to create a file with the `.py` extension. For example, to create a module called `math`, you would create a file called `math.py`.

### Creating a package

To create a package, you need to create a directory with the `__init__.py` file inside it. For example, to create a package called `math`, you would create a directory called `math` and add a file called `__init__.py` inside it.

In this section, you learned about modules and libraries. You also learned how to import modules and libraries into your code. You also learned how to create your own modules and packages.
