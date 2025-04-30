===========
Dense Array
===========
A **dense array** is a data structure that stores all elements of a multi-dimensional array explicitly, including default or zero values. This format is typically used when most of the elements contain meaningful data, making it efficient for direct access and processing.

Key Characteristics
-------------------
- **Direct Access**: All elements are stored and can be accessed using regular indexing.
- **Uniform Memory Usage**: Every element occupies a fixed space in memory.
- **Optimal for Data-Rich Arrays**: Preferred when the array contains few or no default (e.g., zero) values.

Use Cases
---------
- Image processing (pixel data)
- Audio signal processing
- Scientific computations involving fully populated datasets
- Matrix operations where most values are non-zero

Example
-------
A 3×3 dense matrix:
::

   [1, 2, 3]
   [4, 5, 6]
   [7, 8, 9]

Stored in memory exactly as shown, with every element represented explicitly.

Comparison to Sparse Arrays
---------------------------
- Dense arrays consume more memory when many elements are zero or redundant.
- Faster for operations that require regular, indexed access to all elements.
- Not suitable for large datasets with few non-zero entries, where sparse arrays are more efficient.
