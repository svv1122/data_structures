==============
Circular Queue
==============
A **Circular Queue** is a linear data structure that follows the **FIFO (First In, First Out)** principle,
but unlike a linear queue, the last position is connected back to the first to make a circle.
This structure is useful for efficiently utilizing storage by reusing freed-up spaces.

Overview
--------
- **Insertion (Enqueue)**: Performed at the `rear` position.
- **Deletion (Dequeue)**: Performed from the `front` position.
- **Wrap-around**: When the rear or front reaches the end of the array, it wraps around to the beginning.

Structure
---------
Typically implemented using an array with the following attributes:

- ``front``: Points to the front element in the queue.
- ``rear``: Points to the last element in the queue.
- ``size``: Maximum capacity of the queue.

Conditions:

- **Queue is empty**: ``front == -1``
- **Queue is full**: ``(rear + 1) % size == front``

Operations
----------
- ``enqueue(item)``:
  - If the queue is full, raise an overflow error.
  - Else, insert the element at the `rear`, and move `rear` forward in a circular manner.
- ``dequeue()``:
  - If the queue is empty, raise an underflow error.
  - Else, remove the element at the `front`, and move `front` forward in a circular manner.
- ``isEmpty()``: Returns `True` if ``front == -1``.
- ``isFull()``: Returns `True` if ``(rear + 1) % size == front``.

Advantages
----------
- Reuses space that would be wasted in a linear queue.
- Ideal for memory-limited applications.

Applications
------------
- CPU scheduling (Round Robin).
- Memory management (buffering and caching).
- IO management (circular buffers in data streams).
- Traffic management systems.

Diagram
-------
::

    Initial State (size = 5):
    [ ] [ ] [ ] [ ] [ ]
     ↑
    front, rear = -1

    After Enqueue 10, 20, 30:
    [10] [20] [30] [ ] [ ]
     ↑             ↑
    front = 0    rear = 2

    After Dequeue 10:
    [10] [20] [30] [ ] [ ]
           ↑       ↑
        front = 1  rear = 2

    After Enqueue 40, 50:
    [10] [20] [30] [40] [50]
           ↑             ↑
        front = 1      rear = 4

    After Enqueue 60 (wrap-around):
    [60] [20] [30] [40] [50]
     ↑       ↑
    rear = 0 front = 1
