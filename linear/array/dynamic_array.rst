=============
Dynamic Array
=============
A **dynamic array** is a data structure that provides a resizable array, 
allowing elements to be added or removed while managing memory automatically. 
Unlike static arrays, dynamic arrays can grow and shrink during runtime.

Key Features
------------
- **Resizable:** Grows or shrinks as needed to accommodate new elements.
- **Random Access:** Supports O(1) time complexity for accessing elements by index.
- **Amortized Constant Time Insertion:** Appending an element is generally O(1), 
  although resizing may take O(n) when capacity is exceeded.
- **Memory Management:** Automatically allocates and deallocates memory to optimize usage.

How It Works
------------
1. Initially, a dynamic array allocates a fixed-size internal array.
2. When the array exceeds its capacity:
   
   - A new array with larger capacity (usually double the current size) is allocated.
   - Existing elements are copied to the new array.
   - The old array is deallocated.

3. Some dynamic arrays may also shrink when a significant number of elements are removed.

Common Operations
-----------------
- **Append:** Add an element to the end of the array.
- **Insert:** Insert an element at a specific index, shifting subsequent elements.
- **Delete:** Remove an element from a specific index, shifting subsequent elements.
- **Resize:** Change the size of the underlying storage as needed.

Examples
--------
Common implementations of dynamic arrays include:

- Python's ``list``
- Java's ``ArrayList``
- C++'s ``std::vector``

Usage Example in Python::

        arr = []
        arr.append(10)
        arr.append(20)
        arr.append(30)
        print(arr[1])  # Output: 20
