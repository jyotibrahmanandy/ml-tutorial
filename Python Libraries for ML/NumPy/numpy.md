NumPy — Quick Notes

NumPy (Numerical Python) is an open-source Python library used for fast numerical and scientific computing. It provides a powerful N-dimensional array (ndarray) and functions for performing mathematical operations, statistical calculations, linear algebra, and data manipulation efficiently.

In simple words: NumPy helps us store and perform calculations on large collections of numerical data faster and more easily than using normal Python lists.

1. Import NumPy

import numpy as np

2. Create an Array

arr = np.array([1, 2, 3, 4, 5])

3. Check Array Properties

arr.ndim    # Number of dimensions
arr.shape   # Shape of array
arr.size    # Number of elements
arr.dtype   # Data type

4. Create Special Arrays

np.zeros(5)
np.ones(5)
np.arange(1, 10)

5. Indexing

arr[0]
arr[-1]

6. Slicing

arr[1:4]
arr[:3]
arr[2:]

7. Mathematical Operations

arr + 10
arr * 2
arr / 2
arr ** 2

8. Array-to-Array Operations

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
a + b
a - b
a * b

9. Important Statistical Functions

np.sum(arr)
np.mean(arr)
np.min(arr)
np.max(arr)
np.std(arr)

10. Reshape

Change the shape of an array.

arr = np.array([1, 2, 3, 4, 5, 6])
arr.reshape(2, 3)

11. 2D Arrays

arr = np.array([
    [1, 2, 3],
    [4, 5, 6]
])
arr[0, 1]   # 2

12. Boolean Filtering

arr = np.array([10, 20, 30, 40])
arr[arr > 20]

Output:

[30 40]

13. Sorting

np.sort(arr)

14. Random Numbers

np.random.randint(1, 100, 5)

Generates 5 random integers between 1 and 99.

15. Why NumPy?

NumPy is important because it provides:

* Fast numerical calculations
* Powerful array operations
* Matrix operations
* Data manipulation
* Foundation for Pandas, Scikit-learn, SciPy, and Machine Learning

⸻

⭐ Most Important Things to Remember

np.array()
np.zeros()
np.ones()
np.arange()
ndim
shape
size
dtype
Indexing
Slicing
Reshape
sum()
mean()
min()
max()
Boolean Filtering
Random Numbers

Learning Order

Array
  ↓
Indexing & Slicing
  ↓
Array Operations
  ↓
Statistics
  ↓
Reshape
  ↓
Filtering
  ↓
Random
  ↓
Machine Learning