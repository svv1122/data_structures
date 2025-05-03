==================
Double-Ended Queue
==================
A **Double-Ended Queue (Deque)** is a generalized version of a queue where insertion and deletion of elements
can be performed at **both ends** — the front and the rear. This provides more flexibility than a standard queue or stack.

Overview
--------
- Supports both **FIFO** (queue-like) and **LIFO** (stack-like) behavior.
- Insertions and deletions are allowed at:
  - **Front**
  - **Rear**

Structure
---------
A deque can be implemented using:

- **Array**:
  - Fixed size.
  - Requires careful index management for front/rear.
- **Doubly Linked List**:
  - Dynamic size.
  - Easier insertion/deletion at both ends.

Types of Deques
---------------
1. **Input-Restricted Deque**
   - Insertion is allowed only at one end (usually rear).
   - Deletion is allowed at both ends.

2. **Output-Restricted Deque**
   - Insertion is allowed at both ends.
   - Deletion is allowed only at one end (usually front).

Operations
----------
- ``insertFront(item)``: Inserts an item at the front.
- ``insertRear(item)``: Inserts an item at the rear.
- ``deleteFront()``: Removes an item from the front.
- ``deleteRear()``: Removes an item from the rear.
- ``getFront()``: Retrieves the front element without removing it.
- ``getRear()``: Retrieves the rear element without removing it.
- ``isEmpty()``: Checks if the deque is empty.
- ``isFull()`` (array-based): Checks if the deque is full.

Advantages
----------
- Greater flexibility for implementing algorithms that require access at both ends.
- Can function as both a queue and a stack.

Applications
------------
- Palindrome checking.
- Undo/Redo operations in software.
- Task scheduling.
- Sliding window problems in competitive programming.
- Expression evaluation.

Diagram
-------
::

    Initial State (size = 5):
    [ ] [ ] [ ] [ ] [ ]
     ↑               ↑
    front          rear

    After insertRear(10), insertRear(20):
    [10] [20] [ ] [ ] [ ]
     ↑     ↑
    front rear

    After insertFront(5):
    [5] [10] [20] [ ] [ ]
     ↑           ↑
    front       rear

    After deleteRear():
    [5] [10] [20] [ ] [ ]
     ↑     ↑
    front rear

    After deleteFront():
    [5] [10] [20] [ ] [ ]
           ↑   ↑
         front rear
