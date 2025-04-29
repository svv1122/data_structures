==============
Circular Array
==============
A **circular array** is a data structure that uses a single, fixed-size buffer 
as if it were connected end-to-end. This structure treats the array as 
circular, meaning that when the end of the array is reached, the next element 
accessed is the beginning of the array.

Key Characteristics
-------------------
- **Fixed Size:** The array has a pre-defined, constant size.
- **Wrapping Around:** Insertion or access operations wrap around 
  to the start when the end is reached.
- **Efficient Use of Space:** Ideal for problems requiring a buffer 
  that reuses memory, such as in circular queues or buffering streaming data.
- **Indexing:** Index calculations often use modular arithmetic:
  ::

    index = (start + offset) % size

Common Applications
-------------------
- Implementing queues (especially circular queues)
- Scheduling tasks in round-robin fashion
- Buffering real-time data streams
- Handling overflow scenarios where overwriting old data is acceptable

Example
-------
Suppose we have an array of size 5:
::

    [0, 1, 2, 3, 4]

If we are at index 4 and move forward by 1, instead of going to index 5 
(out of bounds), we wrap around to index 0.

Visualization
-------------
::

    0 -> 1 -> 2 -> 3 -> 4
    ^                   |
    |___________________|


