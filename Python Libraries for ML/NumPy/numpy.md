# 📘 NumPy Quick Notes — BTech Edition

> **NumPy** (Numerical Python) is a core Python library for numerical computing. It provides a powerful N-dimensional array object and mathematical functions to operate on them efficiently.

---

## 1. 🔧 Installation & Import

```bash
pip install numpy
```

```python
import numpy as np
```

---

## 2. 📦 NumPy Array (`ndarray`)

The fundamental data structure in NumPy. Faster and more memory-efficient than Python lists.

```python
a = np.array([1, 2, 3])          # 1D array
b = np.array([[1, 2], [3, 4]])   # 2D array

print(a.shape)   # (3,)
print(b.shape)   # (2, 2)
print(b.ndim)    # 2
print(b.dtype)   # int64
```

---

## 3. 🏗️ Array Creation Functions

| Function | Description |
|---|---|
| `np.zeros((r,c))` | All zeros |
| `np.ones((r,c))` | All ones |
| `np.eye(n)` | Identity matrix |
| `np.arange(start, stop, step)` | Like `range()` |
| `np.linspace(start, stop, n)` | n evenly spaced values |
| `np.random.rand(r,c)` | Random floats [0,1) |

```python
np.zeros((2, 3))          # [[0,0,0],[0,0,0]]
np.arange(0, 10, 2)       # [0, 2, 4, 6, 8]
np.linspace(0, 1, 5)      # [0.0, 0.25, 0.5, 0.75, 1.0]
```

---

## 4. 🔢 Array Indexing & Slicing

```python
a = np.array([10, 20, 30, 40, 50])

a[0]       # 10  (indexing)
a[1:4]     # [20, 30, 40]  (slicing)
a[-1]      # 50  (last element)

b = np.array([[1,2,3],[4,5,6]])
b[1, 2]    # 6   (row 1, col 2)
b[:, 1]    # [2, 5]  (all rows, col 1)
```

---

## 5. 🔄 Reshaping & Flattening

```python
a = np.arange(1, 7)       # [1,2,3,4,5,6]

a.reshape(2, 3)            # [[1,2,3],[4,5,6]]
a.reshape(3, 2)            # [[1,2],[3,4],[5,6]]
a.flatten()                # [1,2,3,4,5,6]  (copy)
a.ravel()                  # [1,2,3,4,5,6]  (view)
```

---

## 6. ➕ Array Operations (Element-wise)

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

a + b       # [5, 7, 9]
a * b       # [4, 10, 18]
a ** 2      # [1, 4, 9]
a + 10      # [11, 12, 13]  (broadcasting scalar)
```

---

## 7. 📡 Broadcasting

Allows operations on arrays of **different shapes** by automatically expanding the smaller array.

```python
a = np.array([[1, 2, 3],
              [4, 5, 6]])   # shape (2,3)

b = np.array([10, 20, 30])  # shape (3,)  → broadcast to (2,3)

a + b
# [[11, 22, 33],
#  [14, 25, 36]]
```

---

## 8. 📊 Aggregate / Statistical Functions

```python
a = np.array([[1, 2, 3], [4, 5, 6]])

np.sum(a)          # 21
np.sum(a, axis=0)  # [5, 7, 9]   (column-wise)
np.sum(a, axis=1)  # [6, 15]     (row-wise)

np.mean(a)         # 3.5
np.max(a)          # 6
np.min(a)          # 1
np.std(a)          # standard deviation
np.argmax(a)       # index of max element (flattened)
```

---

## 9. 🔗 Stacking & Splitting

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

np.hstack((a, b))           # [1,2,3,4,5,6]  (horizontal)
np.vstack((a, b))           # [[1,2,3],[4,5,6]]  (vertical)

x = np.arange(1, 7)
np.split(x, 3)              # [array([1,2]), array([3,4]), array([5,6])]
```

---

## 10. 🧮 Linear Algebra (`np.linalg`)

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

np.dot(A, B)          # Matrix multiplication
A @ B                 # Same (Python 3.5+)
np.linalg.det(A)      # Determinant → -2.0
np.linalg.inv(A)      # Inverse matrix
np.linalg.eig(A)      # Eigenvalues & eigenvectors
```

---

## 11. 🎭 Boolean Masking & Fancy Indexing

```python
a = np.array([10, 25, 5, 40, 15])

mask = a > 15          # [False, True, False, True, False]
a[mask]                # [25, 40]  (filter)
a[a % 2 == 0]          # [10, 40]  (even elements)

# Fancy indexing
a[[0, 2, 4]]           # [10, 5, 15]
```

---

## 12. 💾 Save & Load Arrays

```python
a = np.array([1, 2, 3])

np.save('data.npy', a)          # Save single array
np.load('data.npy')             # Load back

np.savetxt('data.csv', a, delimiter=',')   # Save as CSV
np.loadtxt('data.csv', delimiter=',')      # Load CSV
```

---

## 📝 Summary

| Concept | Key Takeaway |
|---|---|
| `ndarray` | Core data structure; fast & memory-efficient |
| Array creation | `zeros`, `ones`, `arange`, `linspace` |
| Indexing | 0-based; supports slicing & boolean masks |
| Reshape | Change shape without changing data |
| Element-wise ops | `+`, `-`, `*`, `/` all work directly |
| Broadcasting | Auto-expand smaller arrays for operations |
| Aggregation | `sum`, `mean`, `max`, `std` with axis control |
| Linear Algebra | `np.linalg` for matrix ops |
| Save/Load | `.npy` for binary, `.csv` for text |

> 💡 **Tip:** Always prefer NumPy over plain Python loops for numerical tasks — it's backed by C, making it **10–100x faster**.