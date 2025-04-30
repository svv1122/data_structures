=======================
Multi-Dimensional Array
=======================
A **multi-dimensional array** is an array of arrays, where data is organized in two or more dimensions. It is an extension of one-dimensional and two-dimensional arrays, commonly used to represent data in a grid, cube, or higher-dimensional format.

Key Characteristics
-------------------
- **Structured Data Representation**: Useful for modeling data with multiple axes (e.g., rows, columns, depth).
- **Indexed Access**: Accessed using multiple indices (e.g., `array[i][j][k]` for a 3D array).
- **Memory Layout**: Typically stored in row-major or column-major order in memory.

Use Cases
---------
- Image processing (e.g., RGB image stored as 3D array: height × width × channels)
- Scientific simulations (e.g., 3D grids in physics models)
- Tensor operations in machine learning and deep learning

Example
-------
A 3×3×2 array (3D array):
::

   array = [
       [[1, 2], [3, 4], [5, 6]],
       [[7, 8], [9, 10], [11, 12]],
       [[13, 14], [15, 16], [17, 18]]
   ]

Here, `array[0][1][1]` gives the value `4`.

Comparison to Other Arrays
--------------------------
- One-dimensional: Linear sequence of elements.
- Two-dimensional: Matrix-like structures.
- Multi-dimensional: Generalization to any number of axes.
