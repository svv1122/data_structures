==============
Priority Queue
==============
A **Priority Queue** is an abstract data structure similar to a regular queue or stack,
but where each element is associated with a **priority**, and elements are served according to their priority.

Overview
--------
- Unlike FIFO in normal queues, elements with **higher priority are dequeued before lower-priority ones**.
- If two elements have the same priority, they are processed according to their order in the queue (usually FIFO).

Structure
---------
Internally, a priority queue can be implemented using:

1. **Unsorted List or Array**:
   - Insertion: O(1)
   - Deletion (finding highest priority): O(n)

2. **Sorted List or Array**:
   - Insertion (at correct position): O(n)
   - Deletion (from front or rear): O(1)

3. **Heap (Binary Heap, Fibonacci Heap, etc.)**:
   - Both insertion and deletion: O(log n)
   - Efficient and commonly used implementation.

Operations
----------
- ``insert(item, priority)``: Inserts an item with a given priority.
- ``delete()`` or ``extractMax()`` / ``extractMin()``:
  - Removes and returns the element with the **highest** (or lowest) priority.
- ``peek()``:
  - Returns the highest priority element without removing it.
- ``isEmpty()``: Checks whether the queue is empty.
- ``changePriority(item, new_priority)``: Updates the priority of an existing item (in some implementations).

Types of Priority Queues
------------------------
1. **Min-Priority Queue**
   - The item with the **lowest** priority value is served first.
   - Used in algorithms like Dijkstra's shortest path.

2. **Max-Priority Queue**
   - The item with the **highest** priority value is served first.
   - Common in job scheduling where higher numbers mean more important.

Advantages
----------
- Supports advanced scheduling and resource management.
- Efficient when implemented with heaps.

Applications
------------
- Task/job scheduling in operating systems.
- Dijkstra’s and A* shortest path algorithms.
- Bandwidth management in networking.
- Event-driven simulation systems.
- Data compression (e.g., Huffman coding).

Diagram
-------
::

    Inserted Elements with Priorities:
    [ (A, 3), (B, 1), (C, 2) ]

    Min-Priority Queue (serve lowest number first):
    → B (priority 1), then C (2), then A (3)

    Max-Priority Queue (serve highest number first):
    → A (priority 3), then C (2), then B (1)
