# Concurrency and Parallelism

Concurrency is the ability of a program to run multiple tasks at the same time. In Python, concurrency is achieved through the use of threads. A thread is a sequence of instructions that can run independently of other code.

## What is a Thread?

A thread is a sequence of instructions that can run independently of other code. Threads are a part of a process. A process is an instance of a program that is being executed. A process can have one or more threads. Threads are lightweight processes. They share the same memory space and global variables. This makes it easier to share data between threads.

## Why Use Threads?

Threads are useful when you have a task that takes a long time to complete. For example, if you are downloading a file from the internet, you can use a thread to display a progress bar while the download is happening. This way, the user can see the progress of the download without having to wait for it to finish.

## What is Parallelism?

Parallelism is the ability of a program to run multiple tasks at the same time. Parallelism is achieved through the use of multiple cores. A core is a processor that can run multiple threads at the same time. A computer with multiple cores can run multiple threads at the same time. This is called parallelism.

## Difference Between Concurrency and Parallelism

Concurrency is the ability of a program to run multiple tasks at the same time. Parallelism is the ability of a program to run multiple tasks at the same time. Concurrency is achieved through the use of threads. Parallelism is achieved through the use of multiple cores. A thread is a sequence of instructions that can run independently of other code. A core is a processor that can run multiple threads at the same time. Threads are lightweight processes. They share the same memory space and global variables. This makes it easier to share data between threads. A computer with multiple cores can run multiple threads at the same time. This is called parallelism.

## Whats unique about Concurrency in Python?

Python has a Global Interpreter Lock (GIL) that prevents multiple threads from executing Python code at the same time. This means that only one thread can be in a state of execution at any given time. This is why Python threads are not truly concurrent. However, threads can still be useful in Python because they allow you to run multiple tasks at the same time. This is especially useful when you are performing I/O operations such as downloading files from the internet.

## How to Create a Thread in Python

To create a thread in Python, you can use the `threading` module. The `threading` module provides a `Thread` class that represents a thread of execution. You can create a `Thread` object by passing a target function to the constructor. The target function will be executed when the thread starts.

```python
import threading
```

```python
def task():
    print('Hello World')
```

```python
thread = threading.Thread(target=task)
thread.start()
```

## How to Create a Thread Using a Class

You can also create a thread by subclassing the `Thread` class. This is useful if you want to pass arguments to the thread. You can also override the `run()` method to customize the behavior of the thread.

```python
import threading
```

```python
class MyThread(threading.Thread):
    def __init__(self, name):
        super().__init__()
        self.name = name

    def run(self):
        print('Hello', self.name)
```

```python
thread = MyThread('World')
thread.start()
```

## How to Create a Thread Using a Lambda Function

You can also create a thread using a lambda function. This is useful if you want to pass arguments to the thread.

```python
import threading
```

```python
thread = threading.Thread(target=lambda: print('Hello World'))
thread.start()
```

## How to Create a Process in Python

To create a process in Python, you can use the `multiprocessing` module. The `multiprocessing` module provides a `Process` class that represents a process. You can create a `Process` object by passing a target function to the constructor. The target function will be executed when the process starts.

```python
import multiprocessing
```

```python
def task():
    print('Hello World')
```

```python
process = multiprocessing.Process(target=task)
process.start()
```

## How to Create a Process Using a Class

You can also create a process by subclassing the `Process` class. This is useful if you want to pass arguments to the process. You can also override the `run()` method to customize the behavior of the process.

```python
import multiprocessing
```

```python
class MyProcess(multiprocessing.Process):
    def __init__(self, name):
        super().__init__()
        self.name = name

    def run(self):
        print('Hello', self.name)
```

```python
process = MyProcess('World')
process.start()
```

## Multiprocessing vs Threading

Multiprocessing                                  | Threading
------------------------------------------------ | --------------------------------------------
Uses multiple processes                          | Uses multiple threads
Each process has its own memory space            | All threads share the same memory space
Processes are heavyweight                        | Threads are lightweight
Processes are independent of each other          | Threads are dependent of each other
Processes can run in parallel                    | Threads can run in parallel
Processes can run on different cores             | Threads can run on the same core
Processes can run on different CPUs              | Threads can run on the same CPU
Processes can run on different machines          | Threads can run on the same machine
Processes can run on different operating systems | Threads can run on the same operating system
Processes can run on different architectures     | Threads can run on the same architecture
Processes can run on different platforms         | Threads can run on the same platform
Processes can run on different devices           | Threads can run on the same device

## How to Create a Pool of Threads in Python

To create a pool of threads in Python, you can use the `concurrent.futures` module. The `concurrent.futures` module provides a `ThreadPoolExecutor` class that represents a pool of worker threads. You can create a `ThreadPoolExecutor` object by passing the number of threads to the constructor. You can then use the `map()` method to execute a function on each item in an iterable. The `map()` method will block until all the results are returned.

```python
import concurrent.futures
```

```python
def task(n):
    return n * n
```

```python
with concurrent.futures.ThreadPoolExecutor(5) as executor:
    print(list(executor.map(task, range(10))))
```

## How to Create a Pool of Processes in Python

To create a pool of processes in Python, you can use the `multiprocessing` module. The `multiprocessing` module provides a `Pool` class that represents a pool of worker processes. You can create a `Pool` object by passing the number of processes to the constructor. You can then use the `map()` method to execute a function on each item in an iterable. The `map()` method will block until all the results are returned.

### Using multiprocessing

```python
import multiprocessing
```

```python
def task(n):
    return n * n
```

```python
with multiprocessing.Pool(5) as pool:
    print(pool.map(task, range(10)))
```

### Using concurrent.futures

```python
import concurrent.futures
```

```python
def task(n):
    return n * n
```

```python
with concurrent.futures.ProcessPoolExecutor(5) as executor:
    print(list(executor.map(task, range(10))))
```

In this article, we learned about concurrency and parallelism in Python. We also learned how to create threads and processes in Python. We also learned how to create a pool of threads and processes in Python.
