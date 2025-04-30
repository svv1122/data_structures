============
Sparse Array
============
A **sparse array** is a data structure that represents an array in which most of the elements have default or zero values. Instead of storing every element explicitly, sparse arrays store only the non-default elements along with their corresponding indices. This can lead to significant memory savings and performance improvements when working with large arrays that contain very few non-zero elements.

Key Characteristics
-------------------
- **Memory Efficient**: Only non-zero or non-default values are stored.
- **Faster Computation**: Operations can be faster by avoiding unnecessary calculations on zero/default elements.
- **Use Cases**:
  - Machine learning (e.g., one-hot encoding, text vectorization)
  - Graph representations (adjacency matrices)
  - Scientific computing (e.g., simulations with large grids)

Common Implementations
-----------------------
Sparse arrays can be implemented using various data structures, such as:

- Dictionary of keys (DOK)
- Compressed sparse row (CSR)
- Compressed sparse column (CSC)
- List of tuples (index, value)

Example
-------
A dense 5×5 matrix:
::

   [0, 0, 0, 0, 0]
   [0, 0, 1, 0, 0]
   [0, 0, 0, 0, 0]
   [0, 0, 0, 0, 2]
   [0, 0, 0, 0, 0]

Sparse representation (list of tuples):
::

   sparse = {
       (1, 2): 1,
       (3, 4): 2
   }
