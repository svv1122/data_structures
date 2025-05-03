=========================
Dynamic Array-Based Stack
=========================
A Dynamic Array-Based Stack is a variation of the array-based stack that uses a **resizable array**. Unlike static arrays with fixed capacity, dynamic arrays can grow or shrink during runtime to accommodate changing data sizes.

This stack follows the **Last In, First Out (LIFO)** principle and is typically implemented using dynamic array structures like Python’s `list`, Java’s `ArrayList`, or C++’s `vector`.

Key Characteristics
-------------------
- Backed by a dynamic array that resizes automatically.
- No need to specify a maximum size at initialization.
- Automatically resizes (usually doubles) when capacity is exceeded.
- Reduces memory overhead in comparison to pre-allocating large static arrays.

Stack Operations
----------------
1. **push(item)**
   - Appends an element to the end of the array.
   - Triggers array resize if the current capacity is full.

2. **pop()**
   - Removes and returns the last element from the array.
   - May trigger downsizing (optional implementation).

3. **peek() / top()**
   - Returns the last element without removing it.

4. **isEmpty()**
   - Checks if the array is empty.

5. **size()**
   - Returns the number of elements in the stack.

Time and Space Complexity
-------------------------
+----------------+-------------------------------+
| Operation      | Amortized Time Complexity     |
+================+===============================+
| push           | O(1) (amortized), O(n) worst  |
+----------------+-------------------------------+
| pop            | O(1)                          |
+----------------+-------------------------------+
| peek / top     | O(1)                          |
+----------------+-------------------------------+
| isEmpty        | O(1)                          |
+----------------+-------------------------------+

Space Complexity: O(n), where n is the number of elements.

Advantages
----------
- Automatically resizes to fit the data.
- Simpler memory management than linked lists.
- Efficient access and cache-friendly.
- Avoids stack overflow issues of fixed-size stacks.

Disadvantages
-------------
- Occasional performance hit due to resizing (during push).
- Resize operations can be costly if frequent and poorly managed.
- Not suitable for environments requiring deterministic timing (real-time systems).

Use Cases
---------
- Suitable for applications where the stack size is unpredictable.
- Useful in high-level languages with built-in dynamic arrays.
- Preferred in space-sensitive environments over static arrays.

Example (Python)
----------------
::

    class DynamicArrayStack:
        def __init__(self):
            self.stack = []

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
