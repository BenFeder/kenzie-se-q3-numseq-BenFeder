<img src="https://www.leafcutterdesigns.com/wp-content/uploads/2016/11/tiny-packages-unopened.jpg" height="120px" />

## Overview - Creating Packages
In this assignment, you will use TDD methodolgy to create several modules for computing various mathematical sequences. The modules will then be grouped into a hierarchical package structure with a top-level package name of `numseq`. This assignment has a set of tests already written for you, contained in the `tests` folder. **You do not need to modify or create your own tests**.

For this assignment, you will **not** be running your code directly from python. You will be using the `unittest` framework, which will import your `numseq` package and run your functions as part of its *test suite*.  Therefore, your `numseq` modules should not contain any `print()` statements, and your modules should not execute any of their own functions. That is, **don't call any of your own functions** from within your modules &mdash; just define them. If you call them, the unittest framework may run into problems when it tries to import your package for testing.

### Part A: `numseq`
Create a package folder named `numseq` with the structure shown below.

Packages allow us to organize and group modules (or python files). Python requires a specific structure for package definitions. The directory name is the name of the package used in an import statement (e.g., `import package_name`). The submodules can be access as attributes of the package, as in `package_name.submodule_name`. In the example below, if you wanted to access functions contained in the `geo` module, you would use `numseq.geo` as your package path.

```bash
├── numseq
│   ├── __init__.py
│   ├── fib.py
│   ├── geo.py
│   ├── prime.py
```

**`__init__.py`**

> The `__init__.py` file is a special placeholder file that designates a directory as 
> a "python package". This prevents directories with a common
> name, such as 'string', from unintentionally hiding valid modules that occur later
> on the module search path. In the simplest case, `__init__.py` can just be an
> empty file, but it can also execute initialization code for the package or
> set an `__all__` variable.  For more about the special `__init__.py` file, see [Python Packages](https://docs.python.org/3/tutorial/modules.html#packages)


### Part B: `fib`
Within the `numseq` package, create a module named `fib.py`. Within the `fib` module, define a single function, `fib(n)`, that returns the nth Fibonacci number. The first 10 terms of the Fibonacci sequence are

`[0, 1, 1, 2, 3, 5, 8, 13, 21, 34 ...]`

Make sure that your `fib(n)` function correctly handles values of n <= 0. If you choose to implement `fib(n)` as a recursive function, your code will have problems if it does not handle values of n <= 0.

### Part C: `geo`
Within the `numseq` package, create a module named `geo.py`. Within this `geo` module, define 3 functions:
 - `square(n)`: Returns the nth term of the numbers that can be arranged into square geometric shapes `[1, 4, 9, 16, 25 ... ]`
 <br><img height="120px" src="https://i1.wp.com/www.stnicholasstlaurence.dorset.sch.uk/wp-content/uploads/2013/11/Square-Numbers.png" /><br>

 - `triangle(n)` : Returns the nth term of the numbers that can be arranged in triangular geometric shapes `[1, 3, 6, 10, 15, 21, 28, 36, 45, 55 ... ]` 
 <br><img height="120px" src="https://www.101computing.net/wp/wp-content/uploads/trinagular-number-sequence.png" /><br>

 - `cube(n)`: Returns the nth term of the numbers that can be arranged as symmetric cube shapes `[1, 8, 27, 64 ...]`
 <br><img height="180px" src="https://static.memrise.com/img/400sqf/from/uploads/course_photos/4974064000131215125138.gif" /><br>

### Part D: `prime`
Finally, create a module named `prime.py` within the `numseq` package. Within this `prime` module, define the following functions:
 - `primes(n)`:  Returns a list of all prime numbers less than n
 - `is_prime(m)`: Returns a boolean indicating whether `m` is a prime number

## Testing
 - *NOTE*: The tests are provided in this assignment. You do **not** have to modify any of the tests or move test files or folders, even if they have some "TODOs" inside (Those comments are for our curriculum devs!).
 - Try out the VS Code built-in test discovery feature to run and debug individual tests. Please read [this article](https://code.visualstudio.com/docs/python/testing) to enable this feature in your VS Code. You can view the test output in the `OUTPUT` tab of your integrated terminal window by selecting the `Python Test Log` dropdown.
 - Alternately, you can run the tests from the command line. To discover and run all tests:

 >`% python -m unittest discover`

 - To run only one test (in this case, the `prime` test):

 >`% python -m unittest test_numseq.TestNumseq.test_prime`

 - Performance timing test: A test that ensures the performance of your `prime` module's `primes()` function (`test_prime_time`) is included in the test suite, but your solution is not required to pass it. Consider it to be a "stretch goal" to see if you can write a *performant* algorithm.

 - Your solution should pass all of the non timing-related tests, including the docstring test (`test_doc_strings`).
