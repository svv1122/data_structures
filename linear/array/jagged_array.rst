============
Jagged Array
============
A **jagged array**, also known as a **ragged array** or an **array of arrays**, is a data structure where each element of the main array can hold a sub-array of varying lengths. Unlike a two-dimensional array where each row has the same number of columns, a jagged array allows each row (or sub-array) to have a different number of elements.

Key Characteristics
-------------------
- Each row in the jagged array can have a different length.
- It is implemented as an array of arrays.
- It is commonly used when dealing with irregular tabular data.

Example (in Python):
::

    jagged_array = [
        [1, 2, 3],
        [4, 5],
        [6, 7, 8, 9]
    ]

    # Accessing an element
    print(jagged_array[0][1])  # Output: 2

Advantages
----------
- Flexible memory usage, as it allocates memory only as needed.
- Efficient when dealing with datasets of varying lengths.

Use Cases
---------
- Representing data like a list of students with a different number of test scores.
- Sparse matrix representations.
- Storing hierarchical or grouped data structures with non-uniform structure.
