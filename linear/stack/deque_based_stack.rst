=================
Deque-Based Stack
=================
A Deque-Based Stack is a stack implemented using a **double-ended queue (deque)**. Though a deque supports insertion and deletion from both ends, in the context of a stack, only one end (typically the right or rear) is used for both push and pop operations.

It follows the **Last In, First Out (LIFO)** principle and offers efficient operations with dynamic sizing. Many programming languages provide a built-in deque (e.g., `collections.deque` in Python), which makes it a practical and performant choice for stack implementation.

Key Characteristics
-------------------
- Built on a double-ended queue structure.
- Dynamic size: grows and shrinks as needed.
- Efficient insertion and deletion at one or both ends.
- High performance due to low-level optimizations.

Stack Operations
----------------
1. **push(item)**
   - Appends an element to the end (usually the right) of the deque.

2. **pop()**
   - Removes and returns the element from the end of the deque.

3. **peek() / top()**
   - Returns the last element without removing it.

4. **isEmpty()**
   - Checks whether the deque is empty.

5. **size()**
   - Returns the number of elements in the deque.

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
- No need to manage resizing or capacity.
- Built-in and highly optimized in most modern languages.
- More flexible than array or linked list stacks.
- Thread-safe variants are available in some standard libraries.

Disadvantages
-------------
- Not as minimal or low-level as simple array or linked list stacks.
- Slightly more overhead than primitive stack structures.
- May not be available in extremely low-level or embedded environments.

Use Cases
---------
- Ideal when stack operations need to be efficient and dynamic.
- Commonly used in Python for algorithmic problems.
- Preferred when switching between stack and queue behavior is needed.

Example (Python)
----------------
::

    from collections import deque

    class DequeStack:
        def __init__(self):
            self.stack = deque()

        def push(self, item):
            self.stack.append(item)

        def pop(self):
            if not self.stack:
                raise Exception("Stack Underflow")
            return self.stack.pop()

        def peek(self):
            if not self.stack:
                raise Exception("Stack is empty")
            return self.stack[-1]

        def isEmpty(self):
            return len(self.stack) == 0

        def size(self):
            return len(self.stack)
