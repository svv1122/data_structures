=====================
Two Dimensional Array
=====================

A two-dimensional array is a data structure that stores elements in a grid format, organized by rows and columns.
Each element in the array can be accessed using two indices: one for the row and one for the column.

Key Characteristics
--------------------
- **Organization**: Elements are arranged in a matrix (grid) of rows and columns.
- **Access**: Each element is accessed by specifying two indices, usually as `array[row][column]`.
- **Use Cases**:
  
  - Representing tables or spreadsheets
  - Storing images (pixel grids)
  - Modeling game boards (e.g., chess)

Example
-------
Here's a basic example of a 2x3 two-dimensional array:
::

    array = [
        [1, 2, 3],
        [4, 5, 6]
    ]

In this example:
- array[0][0] is 1
- array[1][2] is 6

Visualization
--------------
::

    Row 0: [1, 2, 3]
    Row 1: [4, 5, 6]

Summary
-------
A two-dimensional array is ideal when data naturally forms a table-like structure. It enables organized data storage and efficient retrieval by specifying two dimensions.
