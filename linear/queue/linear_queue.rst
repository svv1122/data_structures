============
Linear Queue
============
A **Linear Queue** is a data structure that follows the **FIFO (First In, First Out)** principle.
In this structure, elements are inserted at the **rear** end and removed from the **front** end.

Overview
--------
- **Insertion (Enqueue)**: Performed at the rear.
- **Deletion (Dequeue)**: Performed at the front.
- **Order of Processing**: The first element added is the first to be removed.

Structure
---------
The queue is typically implemented using:

1. **Arrays**:
   - Fixed size.
   - Risk of overflow if rear reaches the end, even if space is freed at the front.
2. **Linked Lists**:
   - Dynamic size.
   - No fixed capacity limit.

Operations
----------
- ``enqueue(item)``: Adds an item to the rear of the queue.
- ``dequeue()``: Removes an item from the front of the queue.
- ``isEmpty()``: Checks if the queue is empty.
- ``isFull()`` (array-based): Checks if the queue has reached maximum capacity.
- ``peek()``: Returns the front item without removing it.

Limitations
-----------
- Inefficient use of space in array implementation, as the freed front slots are not reused.
- Requires shifting elements or using a more advanced structure (like a circular queue) for optimization.

Applications
------------
- Scheduling processes in operating systems.
- Handling requests in web servers.
- Managing printer spooling.
- Breadth-First Search (BFS) in graph algorithms.

Diagram
-------
::

    Front --> [10] [20] [30] [40] <-- Rear
              ↑              ↑
           Dequeue       Enqueue

