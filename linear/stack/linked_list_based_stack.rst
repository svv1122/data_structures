=======================
Linked List-Based Stack
=======================
A Linked List-Based Stack is a stack data structure implemented using a **singly linked list**. It adheres to the **Last In, First Out (LIFO)** principle, where insertions and deletions happen at the head (top) of the list.

Unlike array-based stacks, this implementation does not require a predefined size and can dynamically grow or shrink as elements are added or removed.

Key Characteristics
-------------------
- Built using **nodes**, each containing data and a reference to the next node.
- The **top** of the stack is the head of the linked list.
- No fixed size; memory is allocated dynamically.
- Efficient in memory usage for variable-sized data.

Stack Operations
----------------
1. **push(item)**
   - Creates a new node and links it to the current top.
   - Updates the top to point to the new node.

2. **pop()**
   - Removes the top node and returns its data.
   - Updates the top to point to the next node.

3. **peek() / top()**
   - Returns the data of the top node without removing it.

4. **isEmpty()**
   - Checks whether the top is `None`.

Time and Space Complexity
-------------------------
+----------------+-------------+
| Operation      | Complexity  |
+================+=============+
| push           | O(1)        |
+----------------+-------------+
| pop            | O(1)        |
+----------------+-------------+
| peek / top     | O(1)        |
+----------------+-------------+
| isEmpty        | O(1)        |
+----------------+-------------+

Space Complexity: O(n), where n is the number of elements in the stack.

Advantages
----------
- No pre-allocation of memory needed.
- No stack overflow (limited only by system memory).
- Dynamic sizing makes it suitable for unpredictable workloads.

Disadvantages
-------------
- Extra memory required per node (due to pointers).
- Slightly slower due to dynamic memory and pointer dereferencing.
- Not cache-friendly compared to arrays.

Use Cases
---------
- Useful in environments where dynamic memory allocation is preferred.
- Suitable for recursion-heavy applications.
- Appropriate when the maximum size of the stack is unknown.

Example (Python)
----------------
::

    class Node:
        def __init__(self, data):
            self.data = data
            self.next = None

    class LinkedListStack:
        def __init__(self):
            self.top = None

        def push(self, item):
            new_node = Node(item)
            new_node.next = self.top
            self.top = new_node

        def pop(self):
            if self.top is None:
                raise Exception("Stack Underflow")
            item = self.top.data
            self.top = self.top.next
            return item

        def peek(self):
            if self.top is None:
                raise Exception("Stack is empty")
            return self.top.data

        def isEmpty(self):
            return self.top is None
