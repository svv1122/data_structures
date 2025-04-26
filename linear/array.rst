=====
Array
=====

Descripation
============
The **array** is the most commonly used and basic data structure, which stores 
elements **linearly** in the heap. Elements can be accessed by their index and 
size, and they usually have the same size, like 1 byte (char) or 4 bytes (int) 
on a 64-bit machine. Then, because the virtual memory address ranges from 0x00000000 
to 0x7fffffff, they are also stored physically in memory linearly, which leads 
to efficient element access.

+--------+--------+--------+-----+-------------+
| arr[0] | arr[1] | arr[2] | ... |   arr[n]    |
+--------+--------+--------+-----+-------------+
| 0x100  | 0x104  | 0x108  |     | 0x100 + 4*n |
+--------+--------+--------+-----+-------------+

Category
========
One Dimensional Array
---------------------
* A simple linear array accessed with a singal index.

Two Dimensional Array
---------------------
* A **matrix-like** array with rows and columns.

Dynamic Array
-------------
* An array that resizee the capacity at **runtime**, such as Pythin's 'list'.

Dense Array
-----------
* A multi-dimensional array where all elements are stored in contiguous memory
  locations, with **no** empty or unused space.

Sparse Array
------------
* An array where **most of** the elements are empty(e.g., zero or null), and only 
  non-empty elements are stored to save memory.

Circular Array
--------------
* An array with a fixed size that **wraps around** when elements are accessed beyond 
  the last index, often used for implementing circular queues.

Jagged Array
------------
* An array of arrays where each sub-array can have **different** size, creating a 
  non-rectangular structure.

Bit Array
---------
* An array of bits (0s or 1s) used to efficiently store boolean values or flags in
  memory.

Application
===========
Implementation of Other Data Structures
---------------------------------------
* Arrays form the basic for many other data structures, includeing: stack, queue, heap, 
  hash table, graph and string.
Image Processing
----------------
