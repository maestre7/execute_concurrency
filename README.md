# execute_concurrency

This module provides a function ``execute_concurrency`` that allows executing a list of functions in parallel using the specified concurrency type.

### Function Signature
```python
def execute_concurrency(
    functions: List[Union[callable, Tuple[callable, tuple]]],
    concurrency_type: str = 'threads',
    max_concurrency: int = None
    ) -> List[Any]:
    ...
```

### Parameters
 - ``functions`` (List[Union[callable, Tuple[callable, tuple]]]): A list of functions to be executed.
 - ``concurrency_type`` (str, optional): The type of concurrency to use: 'threads' or 'processes'. Defaults to 'threads'.
 - ``max_concurrency`` (int, optional): The maximum number of threads or processes to use. Defaults to None.

### Returns
 - ``List[Any]``: A list of results obtained by executing the functions in parallel.

### execute_in_threads
This module also includes a function ``execute_in_threads`` which is used by ``execute_concurrency`` to execute functions in parallel using threads.

### Function Signature
```python
def execute_in_threads(
    functions: List[Union[callable, Tuple[callable, tuple]]],
    max_threads: int = None
) -> List[Any]:
    ...
```

### Parameters
 - ``functions`` (List[Union[callable, Tuple[callable, tuple]]]): A list of functions to be executed in parallel or tuples of function and arguments.
 - ``max_threads`` (int, optional): The maximum number of threads to use. If not specified, the number of CPU cores is used.

### Returns
 - ``List[Any]``: A list of results obtained by executing the functions in parallel.

### execute_in_processes
This module also includes a function ``execute_in_processes`` which is used by ``execute_concurrency`` to execute functions in parallel using multiple processes.

### Function Signature
```python
def execute_in_processes(
    functions: List[Union[callable, Tuple[callable, tuple]]],
    max_processes: int = None
) -> List[Any]:
    ...
```

### Parameters
 - ``functions`` (List[Union[callable, Tuple[callable, tuple]]]): A list of functions to be executed.
 - ``max_processes`` (int, optional): The maximum number of processes to use. Defaults to None.

### Returns
 - ``List[Any]``: A list of results obtained by executing the functions in parallel.

## Usage
To use the ``execute_concurrency`` function, provide a list of functions to be executed in parallel. Specify the desired concurrency type (either 'threads' or 'processes') and the maximum number of threads or processes to use (optional).

```python
functions = [func1, (func2, (arg1, arg2)), func3]
results = execute_concurrency(functions, concurrency_type='threads', max_concurrency=4)
```

The function will return a list of results obtained by executing the functions in parallel.

Note: Ensure that the necessary dependencies (``concurrent.futures``, ``ThreadPoolExecutor``, ``ProcessPoolExecutor``) are imported before using the execute_concurrency function.