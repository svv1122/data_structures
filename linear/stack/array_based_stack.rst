=================
Array-Based Stack
=================
An Array-Based Stack is a stack data structure implemented using a contiguous block of memory, typically a fixed-size array. It follows the **Last In, First Out (LIFO)** principle where the last element pushed is the first to be popped.

Key Characteristics
-------------------
- Uses a **linear array** to store elements.
- Stack operations are done at one end (called the "top").
- The size must be predefined or resized dynamically.
- Efficient for scenarios where the maximum size is known.

Stack Operations
----------------
1. **push(item)**
   - Adds an item to the top of the stack.
   - Raises an error if the stack is full (in fixed-size implementation).

2. **pop()**
   - Removes and returns the top element of the stack.
   - Raises an error if the stack is empty.

3. **peek() / top()**
   - Returns the top element without removing it.

4. **isEmpty()**
   - Checks whether the stack is empty.

5. **isFull()**
   - Checks whether the stack is full (in static arrays).

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

Space Complexity: O(n), where n is the maximum size of the array.

Advantages
----------
- Simple to implement.
- Fast access to elements (index-based).
- Memory locality leads to better cache performance.

Disadvantages
-------------
- Fixed size unless a dynamic array is used.
- Potential overflow if size limit is exceeded.

Use Cases
---------
- Parsing expressions (e.g., converting infix to postfix).
- Backtracking algorithms.
- Undo functionality in text editors.
- Balancing symbols (e.g., brackets, parentheses).

Example (Python)
----------------
::

    class ArrayStack:
        def __init__(self, capacity):
            self.stack = [None] * capacity
            self.top = -1
            self.capacity = capacity

        def push(self, item):
            if self.top == self.capacity - 1:
                raise Exception("Stack Overflow")
            self.top += 1
            self.stack[self.top] = item

        def pop(self):
            if self.top == -1:
                raise Exception("Stack Underflow")
            item = self.stack[self.top]
            self.top -= 1
            return item

        def peek(self):
            if self.top == -1:
                raise Exception("Stack is empty")
            return self.stack[self.top]

        def isEmpty(self):
            return self.top == -1

        def isFull(self):
            return self.top == self.capacity - 1
