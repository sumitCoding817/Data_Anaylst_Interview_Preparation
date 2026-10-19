# NumPy Interview Questions and Answers for Freshers

A beginner-friendly NumPy interview guide for Python fresher roles. Each
answer includes a simple definition, key features, a code example, a
real-world example, purpose, and when to use it.

> **How to use this README:** Practise explaining the definition in your
> own words, run the examples, and then explain the real-world use case.
> Examples assume `import numpy as np`.

## Table of Contents

1.  [What is NumPy?](#1-what-is-numpy)
2.  [What are the key features of
    NumPy?](#2-what-are-the-key-features-of-numpy)
3.  [Why is NumPy faster than Python
    lists?](#3-why-is-numpy-faster-than-python-lists)
4.  [What is an ndarray?](#4-what-is-an-ndarray)
5.  [How do you create a NumPy
    array?](#5-how-do-you-create-a-numpy-array)
6.  [What is the difference between a list and an
    array?](#6-what-is-the-difference-between-a-list-and-an-array)
7.  [What are array dimensions, shape, size, and
    dtype?](#7-what-are-array-dimensions-shape-size-and-dtype)
8.  [What is the difference between zeros, ones, and
    empty?](#8-what-is-the-difference-between-zeros-ones-and-empty)
9.  [What are arange and linspace?](#9-what-are-arange-and-linspace)
10. [How do you change an array's data
    type?](#10-how-do-you-change-an-arrays-data-type)
11. [What is reshaping?](#11-what-is-reshaping)
12. [What is flattening an array?](#12-what-is-flattening-an-array)
13. [What is the difference between reshape and
    resize?](#13-what-is-the-difference-between-reshape-and-resize)
14. [What is indexing?](#14-what-is-indexing)
15. [What is slicing?](#15-what-is-slicing)
16. [What is Boolean indexing?](#16-what-is-boolean-indexing)
17. [What is fancy indexing?](#17-what-is-fancy-indexing)
18. [What are vectorized
    operations?](#18-what-are-vectorized-operations)
19. [What is broadcasting?](#19-what-is-broadcasting)
20. [What are universal functions
    (ufuncs)?](#20-what-are-universal-functions-ufuncs)
21. [How do you perform aggregation
    operations?](#21-how-do-you-perform-aggregation-operations)
22. [What is the axis parameter?](#22-what-is-the-axis-parameter)
23. [How do you sort and find unique
    values?](#23-how-do-you-sort-and-find-unique-values)
24. [How do you join and split
    arrays?](#24-how-do-you-join-and-split-arrays)
25. [What is a copy versus a view?](#25-what-is-a-copy-versus-a-view)
26. [How do you handle missing or invalid
    values?](#26-how-do-you-handle-missing-or-invalid-values)
27. [How do you generate random
    numbers?](#27-how-do-you-generate-random-numbers)
28. [What is a NumPy matrix and how is it different from an
    array?](#28-what-is-a-numpy-matrix-and-how-is-it-different-from-an-array)
29. [How do you perform matrix
    multiplication?](#29-how-do-you-perform-matrix-multiplication)
30. [What is a transpose?](#30-what-is-a-transpose)
31. [What is broadcasting versus
    looping?](#31-what-is-broadcasting-versus-looping)
32. [How do you save and load NumPy
    arrays?](#32-how-do-you-save-and-load-numpy-arrays)
33. [What are common NumPy statistical
    functions?](#33-what-are-common-numpy-statistical-functions)
34. [How do you find minimum and maximum values and their
    positions?](#34-how-do-you-find-minimum-and-maximum-values-and-their-positions)
35. [What is `np.where()`?](#35-what-is-npwhere)
36. [What is `np.concatenate()`?](#36-what-is-npconcatenate)
37. [What is the difference between `*` and
    `@`?](#37-what-is-the-difference-between--and-)
38. [How can you improve NumPy performance and memory
    use?](#38-how-can-you-improve-numpy-performance-and-memory-use)
39. [What are common NumPy errors?](#39-what-are-common-numpy-errors)
40. [How is NumPy used in data science and machine
    learning?](#40-how-is-numpy-used-in-data-science-and-machine-learning)
41. [Quick revision: common
    functions](#41-quick-revision-common-functions)
42. [Interview practice tips](#42-interview-practice-tips)

------------------------------------------------------------------------

## 1. What is NumPy?

**Simple definition:** NumPy (Numerical Python) is a Python library used
for fast numerical calculations and working with arrays.

**Key features** - Provides the multidimensional `ndarray` data
structure. - Supports vectorized calculations and broadcasting. -
Includes mathematical, statistical, and linear algebra functions. -
Works with other Python data-science libraries such as pandas,
Matplotlib, and scikit-learn.

**Example**

``` python
import numpy as np

marks = np.array([75, 82, 91, 68])
print(marks.mean())  # 79.0
```

**Real-world example:** Calculate the average marks of students without
writing a loop.

**Purpose:** Make numerical code shorter, clearer, and often faster.

**When to use:** When working with numeric data, scientific
calculations, datasets, images, or machine-learning features.

## 2. What are the key features of NumPy?

**Simple definition:** NumPy provides tools for storing and processing
numerical data efficiently.

**Key features** - Multidimensional arrays. - Fast element-wise
operations. - Broadcasting between compatible shapes. - Mathematical and
statistical functions. - Random-number generation. - Linear algebra
operations. - Array indexing, slicing, and reshaping.

**Example**

``` python
import numpy as np

a = np.array([1, 2, 3])
print(a * 10)       # [10 20 30]
print(np.sqrt(a))   # square roots
```

**Real-world example:** Scale sensor readings, calculate averages, and
prepare data for a machine-learning model.

**Purpose:** Provide a common, efficient foundation for numerical work
in Python.

**When to use:** When data is mostly numeric and array-based operations
are useful.

## 3. Why is NumPy faster than Python lists?

**Simple definition:** NumPy operations are often faster because arrays
store compatible values in a compact form and many operations run in
optimized compiled code.

**Key features** - Less per-element overhead for homogeneous numeric
arrays. - Vectorized operations avoid many Python-level loops. -
Optimized routines can use efficient low-level implementations.

**Example**

``` python
import numpy as np

a = np.arange(1_000_000)
result = a * 2
```

**Real-world example:** Processing millions of temperature readings with
one array operation instead of a Python loop.

**Purpose:** Improve speed and memory efficiency for large numerical
workloads.

**When to use:** For large numeric collections and repeated
calculations. Small tasks may not benefit noticeably, and performance
depends on the operation and data size.

## 4. What is an ndarray?

**Simple definition:** `ndarray` is NumPy's main array type. It stores
elements of a common data type in one or more dimensions.

**Key features** - Can be one-dimensional, two-dimensional, or
higher-dimensional. - Has attributes such as `shape`, `ndim`, `size`,
and `dtype`. - Supports slicing, vectorized math, and reshaping.

**Example**

``` python
import numpy as np

a = np.array([[1, 2, 3], [4, 5, 6]])
print(type(a))    # <class 'numpy.ndarray'>
print(a.ndim)     # 2
print(a.shape)    # (2, 3)
```

**Real-world example:** Represent a grayscale image as a 2D array of
pixel intensities.

**Purpose:** Store and operate on numerical data in a structured way.

**When to use:** Whenever data naturally fits a regular numeric grid or
sequence.

## 5. How do you create a NumPy array?

**Simple definition:** Use `np.array()` to convert a list or another
sequence into an array.

**Key features** - Can create 1D, 2D, and higher-dimensional arrays. -
NumPy usually infers a suitable data type. - Arrays can also be created
with helper functions such as `zeros`, `ones`, and `arange`.

**Example**

``` python
import numpy as np

one_d = np.array([10, 20, 30])
two_d = np.array([[1, 2], [3, 4]])
print(one_d)
print(two_d)
```

**Real-world example:** Convert a list of product prices into an array
before calculating discounts.

**Purpose:** Turn sequence data into an object that supports NumPy's
array operations.

**When to use:** When you have numeric values in a list or need to
construct an array directly.

## 6. What is the difference between a list and an array?

**Simple definition:** A Python list is a general-purpose collection; a
NumPy array is designed for efficient numerical and multidimensional
operations.

**Key differences** - Lists can freely mix types; a standard NumPy array
generally uses one dtype. - `list * 2` repeats a list, while `array * 2`
multiplies each element by two. - NumPy arrays support vectorized math
and multidimensional shapes. - Lists are convenient for general
collections; arrays are useful for numeric computation.

**Example**

``` python
import numpy as np

print([1, 2, 3] * 2)           # [1, 2, 3, 1, 2, 3]
print(np.array([1, 2, 3]) * 2) # [2 4 6]
```

**Real-world example:** Use a list for a mixed collection of names; use
an array for thousands of exam scores.

**Purpose:** Choose the right data structure for the task.

**When to use:** Choose lists for flexible general-purpose data and
NumPy arrays for numeric calculations.

## 7. What are array dimensions, shape, size, and dtype?

**Simple definition:** These attributes describe an array's structure
and storage.

-   `ndim`: number of dimensions.
-   `shape`: length along each dimension.
-   `size`: total number of elements.
-   `dtype`: data type of the elements.

**Example**

``` python
import numpy as np

a = np.array([[1, 2, 3], [4, 5, 6]])
print(a.ndim)   # 2
print(a.shape)  # (2, 3)
print(a.size)   # 6
print(a.dtype)  # typically int64 or int32, depending on platform
```

**Real-world example:** Check that an image has the expected height and
width before processing it.

**Purpose:** Understand and validate an array's structure.

**When to use:** When debugging shape mismatches, preparing model input,
or checking memory and data types.

## 8. What is the difference between zeros, ones, and empty?

**Simple definition:** These functions create arrays with a chosen shape
but different initial contents.

**Key features** - `np.zeros(shape)`: fills with zeros. -
`np.ones(shape)`: fills with ones. - `np.empty(shape)`: allocates an
array without initializing its values, so the contents are unspecified.

**Example**

``` python
import numpy as np

print(np.zeros((2, 3)))
print(np.ones((2, 2)))
scratch = np.empty(3)  # Do not assume its values are zero
```

**Real-world example:** Create a zero-filled score table before
populating it with calculated results.

**Purpose:** Allocate arrays of a required size.

**When to use:** Use `zeros` or `ones` when initial values matter. Use
`empty` only when every element will be overwritten before being read.

## 9. What are arange and linspace?

**Simple definition:** Both create sequences of numbers, but they define
the sequence differently.

**Key features** - `np.arange(start, stop, step)` uses a step size and
excludes `stop`. - `np.linspace(start, stop, num)` returns a specified
number of evenly spaced values and includes the endpoint by default.

**Example**

``` python
import numpy as np

print(np.arange(0, 10, 2))       # [0 2 4 6 8]
print(np.linspace(0, 1, 5))      # [0.   0.25 0.5  0.75 1.  ]
```

**Real-world example:** Use `arange` for integer time steps and
`linspace` to sample points across a mathematical interval.

**Purpose:** Generate predictable numeric sequences.

**When to use:** Use `arange` when the step is important; use `linspace`
when the number of samples is important, especially with floating-point
values.

## 10. How do you change an array's data type?

**Simple definition:** Use `astype()` to create an array converted to
another data type.

**Key features** - Supports types such as `int`, `float`, and `bool`. -
Conversion may lose information, such as decimal parts when converting
floats to integers. - The original array is not changed by the usual
`astype()` call.

**Example**

``` python
import numpy as np

a = np.array([1.8, 2.4, 3.9])
b = a.astype(int)
print(b)  # [1 2 3], decimals are truncated
```

**Real-world example:** Convert numeric values read as floating-point
numbers into integer category codes when appropriate.

**Purpose:** Control storage and make data compatible with a calculation
or API.

**When to use:** When a required dtype is known and the conversion is
safe for the data.

## 11. What is reshaping?

**Simple definition:** Reshaping changes an array's dimensions without
changing its element count.

**Key features** - Use `reshape()`. - The new shape must contain the
same total number of elements. - A reshape may return a view when
possible, otherwise a copy.

**Example**

``` python
import numpy as np

a = np.arange(6)
b = a.reshape(2, 3)
print(b)
# [[0 1 2]
#  [3 4 5]]
```

**Real-world example:** Convert 12 monthly values into a 3-by-4 table
for analysis.

**Purpose:** Arrange data into the shape expected by an operation or
model.

**When to use:** When the data is correct but its dimensions need to
change.

## 12. What is flattening an array?

**Simple definition:** Flattening converts a multidimensional array into
a one-dimensional array.

**Key features** - `flatten()` returns a copy. - `ravel()` returns a
flattened view when possible, otherwise a copy.

**Example**

``` python
import numpy as np

a = np.array([[1, 2], [3, 4]])
print(a.flatten())  # [1 2 3 4]
```

**Real-world example:** Turn a small image's pixel grid into one feature
vector for a simple model.

**Purpose:** Convert multidimensional data into a single sequence.

**When to use:** When an API or calculation expects 1D input. Preserve
the original shape if row and column meaning matters.

## 13. What is the difference between reshape and resize?

**Simple definition:** `reshape()` changes the shape while preserving
the number of elements; `resize()` can change the element count as well.

**Key features** - `reshape()` raises an error if the requested shape
has a different number of elements. - `np.resize(a, new_shape)` returns
a new array and repeats values if needed. - `a.resize(new_shape)`
modifies the array in place under its own constraints.

**Example**

``` python
import numpy as np

a = np.array([1, 2, 3, 4])
print(a.reshape(2, 2))
print(np.resize(a, (3, 2)))  # repeats values to fill the shape
```

**Real-world example:** Reshape a fixed batch of values into rows and
columns; use resizing only when repeating or truncating values is
genuinely intended.

**Purpose:** Control array dimensions or output length.

**When to use:** Prefer `reshape()` for ordinary dimension changes. Be
cautious with resizing because it may repeat or discard data.

## 14. What is indexing?

**Simple definition:** Indexing accesses a particular element by its
position. NumPy uses zero-based indexing.

**Key features** - First element has index `0`. - Negative indexes count
from the end. - Multidimensional arrays can be indexed by row and
column.

**Example**

``` python
import numpy as np

a = np.array([[10, 20], [30, 40]])
print(a[0, 1])  # 20
print(a[-1, -1])  # 40
```

**Real-world example:** Read the value of a particular pixel or the
score of a particular student.

**Purpose:** Access individual values in an array.

**When to use:** When you know the position of the data you need.

## 15. What is slicing?

**Simple definition:** Slicing selects a range of array elements using
`start:stop:step`.

**Key features** - The `stop` position is excluded. - Slicing often
returns a view for basic NumPy slicing, so changes may affect the
original array. - Multidimensional arrays can be sliced across rows and
columns.

**Example**

``` python
import numpy as np

a = np.array([10, 20, 30, 40, 50])
print(a[1:4])  # [20 30 40]
print(a[::2])  # [10 30 50]
```

**Real-world example:** Select readings from a particular section of a
time series.

**Purpose:** Extract a subset without manually looping through every
element.

**When to use:** When selecting a continuous range, every nth value, or
a region of a multidimensional array.

## 16. What is Boolean indexing?

**Simple definition:** Boolean indexing selects elements using a
condition that produces `True` or `False` values.

**Key features** - Conditions can be applied to an entire array. -
Multiple conditions can be combined with `&` (and), `|` (or), and `~`
(not). - Put each comparison in parentheses when combining conditions.

**Example**

``` python
import numpy as np

marks = np.array([35, 72, 88, 41, 95])
print(marks[marks >= 60])  # [72 88 95]
```

**Real-world example:** Filter products whose prices are below a budget
or students whose marks exceed a threshold.

**Purpose:** Filter data by a rule.

**When to use:** When you need only values that satisfy one or more
conditions.

## 17. What is fancy indexing?

**Simple definition:** Fancy indexing selects elements using integer
index arrays or lists of positions.

**Key features** - Can select non-adjacent positions. - The result is
generally a copy rather than a view. - Index order determines result
order.

**Example**

``` python
import numpy as np

a = np.array([10, 20, 30, 40, 50])
print(a[[0, 2, 4]])  # [10 30 50]
```

**Real-world example:** Select a few specific customer records or
columns from a numeric dataset.

**Purpose:** Retrieve scattered positions in one operation.

**When to use:** When the required indexes are not one continuous slice.

## 18. What are vectorized operations?

**Simple definition:** Vectorization means applying an operation to an
entire array without writing an explicit Python loop.

**Key features** - Makes code concise and readable. - Often runs faster
for numeric work. - Works naturally with arithmetic and many NumPy
functions.

**Example**

``` python
import numpy as np

prices = np.array([100, 200, 300])
discounted = prices * 0.9
print(discounted)  # [ 90. 180. 270.]
```

**Real-world example:** Apply a discount to thousands of product prices
at once.

**Purpose:** Express calculations directly over collections of values.

**When to use:** When the same calculation must be applied to many array
elements.

## 19. What is broadcasting?

**Simple definition:** Broadcasting lets NumPy perform operations on
arrays with compatible shapes, even when their shapes are different.

**Key rules** - Compare dimensions from right to left. - Dimensions are
compatible if they are equal or one of them is `1`. - If dimensions are
incompatible, NumPy raises a shape-related error.

**Example**

``` python
import numpy as np

prices = np.array([100, 200, 300])
print(prices + 10)  # [110 210 310]
```

**Real-world example:** Add a fixed tax amount to every item or
normalize each column of a data table.

**Purpose:** Apply operations across compatible shapes without manually
repeating values.

**When to use:** When combining arrays with a scalar, row vector, column
vector, or other compatible shape. Check shapes carefully.

## 20. What are universal functions (ufuncs)?

**Simple definition:** Universal functions, or ufuncs, are NumPy
functions designed to operate element by element on arrays.

**Key features** - Support vectorized operations. - Common examples
include `np.sqrt`, `np.exp`, `np.sin`, `np.add`, and `np.maximum`. -
Usually work with broadcasting.

**Example**

``` python
import numpy as np

a = np.array([1, 4, 9, 16])
print(np.sqrt(a))  # [1. 2. 3. 4.]
```

**Real-world example:** Calculate square roots, exponentials, or
trigonometric values for a batch of scientific measurements.

**Purpose:** Apply common mathematical functions efficiently to array
data.

**When to use:** When the same supported mathematical operation is
needed for many values.

## 21. How do you perform aggregation operations?

**Simple definition:** Aggregation reduces many values to one or more
summary values.

**Key features** - `sum()`, `mean()`, `min()`, `max()`, and `std()` are
common methods. - Functions can operate on the entire array or along a
chosen axis. - Empty arrays and missing values may need special
handling.

**Example**

``` python
import numpy as np

sales = np.array([100, 150, 200])
print(np.sum(sales))   # 450
print(np.mean(sales))  # 150.0
print(np.max(sales))   # 200
```

**Real-world example:** Calculate total sales, average marks, or the
highest sensor reading.

**Purpose:** Summarize numeric data.

**When to use:** When you need totals, averages, ranges, or other
summary statistics.

## 22. What is the axis parameter?

**Simple definition:** `axis` specifies the dimension along which a
NumPy operation is performed.

For a 2D array: - `axis=0` operates down rows, producing one result per
column. - `axis=1` operates across columns, producing one result per
row. - `axis=None` usually operates across all elements.

**Example**

``` python
import numpy as np

a = np.array([[1, 2, 3], [4, 5, 6]])
print(a.sum(axis=0))  # [5 7 9], column totals
print(a.sum(axis=1))  # [ 6 15], row totals
print(a.sum())        # 21
```

**Real-world example:** Find each student's total across subjects
(`axis=1`) or each subject's total across students (`axis=0`).

**Purpose:** Choose how a multidimensional array is reduced.

**When to use:** When summarizing rows or columns. A useful trick is to
check which dimension disappears from the output shape.

## 23. How do you sort and find unique values?

**Simple definition:** Sorting orders values; `unique()` returns the
distinct values in an array.

**Key features** - `np.sort(a)` returns a sorted copy. - `a.sort()`
sorts the array in place. - `np.unique(a)` returns sorted unique values
by default.

**Example**

``` python
import numpy as np

a = np.array([3, 1, 3, 2, 1])
print(np.sort(a))    # [1 1 2 3 3]
print(np.unique(a))  # [1 2 3]
```

**Real-world example:** List distinct product IDs or sort scores before
reporting results.

**Purpose:** Organize data and identify repeated values.

**When to use:** When ordering values, deduplicating categories, or
checking which values occur in a dataset.

## 24. How do you join and split arrays?

**Simple definition:** Joining combines arrays; splitting divides an
array into multiple parts.

**Key features** - `np.concatenate()` joins arrays along an existing
axis. - `np.vstack()` stacks arrays vertically. - `np.hstack()` stacks
arrays horizontally. - `np.split()` requires equal divisions;
`np.array_split()` allows uneven divisions.

**Example**

``` python
import numpy as np

a = np.array([1, 2])
b = np.array([3, 4])
print(np.concatenate((a, b)))  # [1 2 3 4]

parts = np.array_split(np.array([1, 2, 3, 4, 5]), 2)
print(parts)
```

**Real-world example:** Combine sales data from two days or divide a
dataset into chunks for processing.

**Purpose:** Assemble or partition arrays.

**When to use:** When merging compatible datasets or processing a large
array in smaller sections.

## 25. What is a copy versus a view?

**Simple definition:** A copy owns separate data; a view shares data
with another array.

**Key features** - Basic slicing often returns a view. - Fancy indexing
and `flatten()` return copies. - `copy()` explicitly creates independent
data.

**Example**

``` python
import numpy as np

a = np.array([10, 20, 30])
view = a[1:]
view[0] = 99
print(a)  # [10 99 30]

b = a.copy()
b[0] = 0
print(a)  # original remains unchanged
```

**Real-world example:** Use a copy before editing a subset when the
original dataset must remain unchanged.

**Purpose:** Understand whether edits can affect other arrays and manage
memory correctly.

**When to use:** Use views for efficient access when shared data is
intended; use copies when independent data is required.

## 26. How do you handle missing or invalid values?

**Simple definition:** NumPy commonly represents missing numeric values
with `np.nan`, a special floating-point value.

**Key features** - `np.isnan(a)` identifies NaN values. -
`np.nanmean(a)` calculates a mean while ignoring NaNs. -
`np.nan_to_num(a)` can replace NaN and infinite values. - NaN is not
equal to itself, so use `np.isnan`, not `== np.nan`.

**Example**

``` python
import numpy as np

a = np.array([10.0, np.nan, 30.0])
print(np.isnan(a))       # [False  True False]
print(np.nanmean(a))     # 20.0
```

**Real-world example:** Calculate an average temperature when one sensor
reading is missing.

**Purpose:** Detect and manage missing numeric values.

**When to use:** When numeric datasets contain NaNs. Decide whether to
ignore, replace, or investigate missing values based on the meaning of
the data.

## 27. How do you generate random numbers?

**Simple definition:** NumPy provides tools to generate random samples
for simulations, testing, and machine learning.

**Key features** - Prefer `np.random.default_rng()` for new code. - A
seed makes results reproducible. - Methods include `random()`,
`integers()`, and `choice()`.

**Example**

``` python
import numpy as np

rng = np.random.default_rng(42)
print(rng.integers(1, 7, size=5))  # five values from 1 through 6
```

**Real-world example:** Simulate dice rolls, create test data, or
shuffle samples for an experiment.

**Purpose:** Generate random or pseudorandom values.

**When to use:** For simulations, sampling, and reproducible
experiments. Do not use NumPy's random generator for passwords, tokens,
or security-sensitive randomness.

## 28. What is a NumPy matrix and how is it different from an array?

**Simple definition:** `np.matrix` is a legacy 2D matrix class. In
modern NumPy code, ordinary `ndarray` objects are generally recommended.

**Key features** - `ndarray` supports any number of dimensions. -
`np.matrix` is restricted to 2D. - The `*` operator behaves differently:
element-wise multiplication for arrays, matrix multiplication for
`np.matrix`. - Use `@` for matrix multiplication with arrays.

**Example**

``` python
import numpy as np

a = np.array([[1, 2], [3, 4]])
print(a * a)  # element-wise multiplication
print(a @ a)  # matrix multiplication
```

**Real-world example:** Represent feature data as arrays and use `@` for
linear algebra.

**Purpose:** Understand why ordinary arrays are the standard choice.

**When to use:** Prefer `ndarray` for new projects. Learn about
`np.matrix` mainly to understand older code.

## 29. How do you perform matrix multiplication?

**Simple definition:** Matrix multiplication combines rows of one matrix
with columns of another.

**Key features** - Use the `@` operator or `np.matmul()`. - Inner
dimensions must match. - `np.dot()` is also used, but its behavior
depends on input dimensions.

**Example**

``` python
import numpy as np

a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
print(a @ b)
# [[19 22]
#  [43 50]]
```

**Real-world example:** Matrix multiplication is used in neural-network
layers and transformations in computer graphics.

**Purpose:** Perform linear algebra calculations.

**When to use:** When the mathematical operation is matrix
multiplication, not simple element-by-element multiplication.

## 30. What is a transpose?

**Simple definition:** Transposing swaps an array's axes. For a 2D
array, it turns rows into columns and columns into rows.

**Key features** - Use `a.T` or `np.transpose(a)`. - A transpose often
returns a view. - For higher-dimensional arrays, axes are rearranged
rather than just rows and columns.

**Example**

``` python
import numpy as np

a = np.array([[1, 2, 3], [4, 5, 6]])
print(a.T)
# [[1 4]
#  [2 5]
#  [3 6]]
```

**Real-world example:** Change a table from rows of observations to
columns of observations when an API expects the other orientation.

**Purpose:** Rearrange axes without manually rebuilding the data.

**When to use:** When a matrix or dataset has the wrong orientation for
a calculation.

## 31. What is broadcasting versus looping?

**Simple definition:** Broadcasting lets NumPy apply compatible
operations across arrays without explicitly looping through each value
in Python.

**Key features** - Often shorter and faster than a Python loop. - Avoids
manually copying a scalar or compatible smaller array. - Requires
compatible shapes and can still allocate a large result array.

**Example**

``` python
import numpy as np

values = np.array([1, 2, 3, 4])
result = values + 5
print(result)  # [6 7 8 9]
```

**Real-world example:** Add a fixed offset to all readings from a
sensor.

**Purpose:** Apply the same operation across a collection of values.

**When to use:** Use broadcasting for compatible array calculations. A
loop may still be clearer for complex logic or when each item requires a
different procedure.

## 32. How do you save and load NumPy arrays?

**Simple definition:** NumPy can store arrays in binary `.npy` files or
multiple arrays in `.npz` archives.

**Key features** - `np.save()` and `np.load()` work with `.npy`. -
`np.savez()` stores multiple named arrays in one archive. -
`np.savetxt()` and `np.loadtxt()` can handle simple text files. - Only
load files you trust when using formats that allow pickled Python
objects.

**Example**

``` python
import numpy as np

a = np.array([10, 20, 30])
np.save("scores.npy", a)
loaded = np.load("scores.npy")
print(loaded)
```

**Real-world example:** Save a processed numeric dataset so it can be
reused without repeating the preparation step.

**Purpose:** Persist array data between program runs.

**When to use:** Use `.npy` for one array, `.npz` for multiple arrays,
or text formats when human-readable interchange is required.

## 33. What are common NumPy statistical functions?

**Simple definition:** Statistical functions describe the center,
spread, or distribution of numeric values.

**Key features** - `mean()` calculates the arithmetic average. -
`median()` returns the middle value after ordering. - `std()` measures
standard deviation. - `var()` measures variance. - `percentile()` and
`quantile()` calculate thresholds in a distribution.

**Example**

``` python
import numpy as np

marks = np.array([50, 60, 70, 80, 90])
print(np.mean(marks))       # 70.0
print(np.median(marks))     # 70.0
print(np.std(marks))        # population standard deviation
print(np.percentile(marks, 75))
```

**Real-world example:** Compare average marks and score variability
across classes.

**Purpose:** Summarize and understand numerical distributions.

**When to use:** During exploratory data analysis, quality checks, and
scientific reporting. Remember that NumPy's default `std()` uses
`ddof=0`, the population-style calculation.

## 34. How do you find minimum and maximum values and their positions?

**Simple definition:** `min()` and `max()` return extreme values;
`argmin()` and `argmax()` return the positions of those values.

**Key features** - Use `np.min()` and `np.max()` for values. - Use
`np.argmin()` and `np.argmax()` for flattened positions by default. -
With `axis`, the result gives positions along the selected axis.

**Example**

``` python
import numpy as np

a = np.array([12, 45, 23, 9])
print(np.max(a))     # 45
print(np.argmax(a))  # 1
```

**Real-world example:** Find the highest sales day and its position in a
daily sales array.

**Purpose:** Identify extremes and their locations.

**When to use:** When you need the largest or smallest value and where
it occurs.

## 35. What is `np.where()`?

**Simple definition:** `np.where()` can return indexes where a condition
is true or choose values based on a condition.

**Key features** - With one argument, it returns index arrays for true
positions. - With three arguments, it selects from the second or third
argument according to the condition. - The chosen arrays must be
broadcast-compatible.

**Example**

``` python
import numpy as np

marks = np.array([35, 65, 82])
print(np.where(marks >= 60, "Pass", "Fail"))
# ['Fail' 'Pass' 'Pass']
```

**Real-world example:** Label sales as "Target met" or "Below target"
based on a threshold.

**Purpose:** Perform conditional selection in array code.

**When to use:** When you need to replace an `if/else` decision across
many values or locate condition matches.

## 36. What is `np.concatenate()`?

**Simple definition:** `np.concatenate()` joins two or more arrays along
an existing axis.

**Key features** - Arrays must match in all dimensions except the
joining axis. - For 1D arrays, it appends values in sequence. - For
vertical or horizontal stacking, `vstack()` and `hstack()` may be more
readable.

**Example**

``` python
import numpy as np

a = np.array([1, 2])
b = np.array([3, 4])
print(np.concatenate((a, b)))  # [1 2 3 4]
```

**Real-world example:** Merge today's readings with yesterday's
readings.

**Purpose:** Combine arrays into one dataset.

**When to use:** When datasets have compatible shapes and should be
joined along a particular dimension.

## 37. What is the difference between `*` and `@`?

**Simple definition:** For NumPy arrays, `*` performs element-wise
multiplication, while `@` performs matrix multiplication.

**Example**

``` python
import numpy as np

a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])

print(a * b)
# [[ 5 12]
#  [21 32]]

print(a @ b)
# [[19 22]
#  [43 50]]
```

**Real-world example:** Use `*` to multiply each price by its
corresponding quantity; use `@` for a linear algebra calculation.

**Purpose:** Distinguish element-wise arithmetic from matrix algebra.

**When to use:** Use `*` when matching elements should be multiplied and
`@` when multiplying matrices or compatible vectors.

## 38. How can you improve NumPy performance and memory use?

**Simple definition:** Use NumPy's optimized array operations and avoid
unnecessary copies or oversized intermediate arrays.

**Key features** - Prefer vectorized operations where clear and
appropriate. - Choose a suitable dtype, such as `float32` when its
precision is sufficient. - Reuse arrays when safe. - Use views when
shared data is acceptable. - Consider chunking data that is too large to
fit comfortably in memory.

**Example**

``` python
import numpy as np

# Vectorized calculation rather than a Python loop
values = np.arange(1_000_000, dtype=np.float32)
scaled = values * 0.5
print(scaled[:3])
```

**Real-world example:** Process a large sensor dataset while controlling
memory consumption.

**Purpose:** Reduce execution time and memory overhead.

**When to use:** When profiling shows numeric operations or array memory
use is a bottleneck. Measure before optimizing, because the best
approach depends on the workload.

## 39. What are common NumPy errors?

**Simple definition:** NumPy errors often happen when shapes, indexes,
data types, or values do not match the operation's requirements.

**Common examples** - `IndexError`: an index is outside the valid
range. - `ValueError` from broadcasting: shapes are incompatible. -
`ValueError` from reshape: the requested shape has a different element
count. - Unexpected results from dtype conversion: information may be
truncated or overflow. - NaN results: inputs may contain missing or
invalid numeric values.

**Example**

``` python
import numpy as np

a = np.array([1, 2, 3])
# a.reshape(2, 2)  # ValueError: 3 elements cannot fill a 2x2 shape

b = np.array([1, 2, 3])
c = np.array([10, 20])
# b + c  # ValueError: shapes (3,) and (2,) are not broadcast-compatible
```

**Real-world example:** A machine-learning model rejects input because
the feature array has the wrong shape.

**Purpose:** Debug calculations and validate data before processing.

**When to use:** Whenever an operation fails or results look incorrect.
Inspect `shape`, `dtype`, and sample values first.

## 40. How is NumPy used in data science and machine learning?

**Simple definition:** NumPy provides the array and numerical-computing
foundation used by many data-science and machine-learning workflows.

**Key features** - Stores numeric features and labels in arrays. -
Supports normalization and mathematical transformations. - Provides
statistics and linear algebra. - Works with pandas, Matplotlib, SciPy,
and scikit-learn.

**Example**

``` python
import numpy as np

features = np.array([[10.0, 100.0], [20.0, 200.0], [30.0, 300.0]])
column_means = features.mean(axis=0)
centered = features - column_means
print(centered)
```

**Real-world example:** Center numeric features before training a model
or summarize a dataset before visualizing it.

**Purpose:** Prepare and calculate with numeric data efficiently.

**When to use:** When working with scientific data, analytics, image
arrays, or machine-learning inputs. In production ML, use the
preprocessing rules learned from training data to avoid data leakage.

------------------------------------------------------------------------

## 41. Quick revision: common functions

  -----------------------------------------------------------------------
  Function / attribute                What it does
  ----------------------------------- -----------------------------------
  `np.array()`                        Creates an array

  `np.zeros()`                        Creates an array filled with zeros

  `np.ones()`                         Creates an array filled with ones

  `np.empty()`                        Allocates an uninitialized array

  `np.arange()`                       Creates values using a step

  `np.linspace()`                     Creates a fixed number of evenly
                                      spaced values

  `reshape()`                         Changes dimensions while preserving
                                      element count

  `flatten()`                         Returns a flattened copy

  `ravel()`                           Returns a flattened view when
                                      possible

  `astype()`                          Converts the array dtype

  `mean()`                            Calculates the average

  `sum()`                             Calculates a total

  `min()` / `max()`                   Finds minimum / maximum

  `argmin()` / `argmax()`             Finds positions of minimum /
                                      maximum

  `sort()` / `np.sort()`              Sorts values in place / returns a
                                      sorted copy

  `np.unique()`                       Finds distinct values

  `np.where()`                        Conditional selection or index
                                      lookup

  `np.concatenate()`                  Joins arrays

  `np.isnan()`                        Detects NaN values

  `np.nanmean()`                      Calculates a mean while ignoring
                                      NaNs

  `np.random.default_rng()`           Creates a random number generator

  `np.save()` / `np.load()`           Saves / loads `.npy` arrays

  `np.dot()` / `@`                    Performs dot or matrix
                                      multiplication depending on input
                                      dimensions
  -----------------------------------------------------------------------

## 42. Interview practice tips

1.  Start with a one- or two-sentence definition.

2.  Explain the purpose in plain language.

3.  Write a small example and predict its output.

4.  Give a practical example from marks, sales, sensors, images, or data
    analysis.

5.  Be ready to explain `shape`, `ndim`, `dtype`, `axis`, broadcasting,
    and copy versus view.

6.  If asked about speed, say NumPy is often faster for large numerical
    operations, but actual performance depends on data size and the
    operation.

7.  Run the examples in a Python environment. Install NumPy if needed:

    ``` bash
    python -m pip install numpy
    ```

8.  Practise these short comparisons:

    -   List vs array
    -   `arange()` vs `linspace()`
    -   `reshape()` vs `flatten()`
    -   Copy vs view
    -   `axis=0` vs `axis=1`
    -   `*` vs `@`
    -   `np.nanmean()` vs `np.mean()`

------------------------------------------------------------------------

**Good luck with your NumPy interview preparation!** Keep the answers
simple, understand the examples, and focus on explaining *why* you would
use each feature.

