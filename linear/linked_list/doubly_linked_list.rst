==================
Doubly Linked List
==================
A **Doubly Linked List (DLL)** is a type of linked list in which each node contains three parts:
- **Data**: The value held by the node.
- **Prev**: A reference to the previous node.
- **Next**: A reference to the next node.

This allows traversal in both forward and backward directions.

Structure
---------
Each node is represented as:
::

    +--------+--------+--------+
    |  Prev  |  Data  |  Next  |
    +--------+--------+--------+

The `Prev` of the head node and the `Next` of the tail node are `null` (or `None` in Python).

Operations
----------
1. **Traversal** – Forward and backward.
2. **Insertion**:
   - At the beginning.
   - At the end.
   - After or before a specific node.
3. **Deletion**:
   - Of a given node.
4. **Search** – Find a node by value.

Time Complexities
-----------------
- **Access/Search**: :math:`O(n)`
- **Insertion/Deletion** (given node reference): :math:`O(1)`
- **Insertion/Deletion** (by value): :math:`O(n)`

Advantages
----------
- Bidirectional traversal.
- Easier deletion of a given node (no need to traverse from head).

Disadvantages
-------------
- Extra memory required for the `prev` pointer.
- Slightly more complex to implement compared to singly linked list.

Use Cases
---------
- Implementing navigation systems (e.g., browser back and forward).
- Complex data structures like adjacency lists, LRU caches, etc.

Example (Python)
----------------
::

    class Node:
        def __init__(self, data):
            self.data = data
            self.prev = None
            self.next = None

    class DoublyLinkedList:
        def __init__(self):
            self.head = None

        def append(self, data):
            new_node = Node(data)
            if not self.head:
                self.head = new_node
                return
            last = self.head
            while last.next:
                last = last.next
            last.next = new_node
            new_node.prev = last

        def print_forward(self):
            current = self.head
            while current:
                print(current.data, end=" <-> ")
                last = current
                current = current.next
            print("None")

        def print_backward(self):
            current = self.head
            while current and current.next:
                current = current.next
            while current:
                print(current.data, end=" <-> ")
                current = current.prev
            print("None")

    # Example usage
    dll = DoublyLinkedList()
    dll.append(1)
    dll.append(2)
    dll.append(3)
    dll.print_forward()   # Output: 1 <-> 2 <-> 3 <-> None
    dll.print_backward()  # Output: 3 <-> 2 <-> 1 <-> None
