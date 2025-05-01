===========================
Circular Doubly Linked List
===========================
A **Circular Doubly Linked List (CDLL)** is a variation of a doubly linked list where:

- The `next` pointer of the last node points to the head node.
- The `prev` pointer of the head node points to the last node.

This creates a bidirectional circular structure where traversal can occur forward or backward from any node.

Structure
---------
Each node contains three parts:
::

    +--------+--------+--------+
    |  Prev  |  Data  |  Next  |
    +--------+--------+--------+

In a CDLL:

- `head.prev` points to the tail node.
- `tail.next` points to the head node.

Operations
----------
1. **Traversal** – Forward and backward, with wrap-around.
2. **Insertion**:
   - At the beginning.
   - At the end.
   - After or before a specific node.
3. **Deletion**:
   - Of a node by value or reference.
4. **Search** – Find a node with a given value.

Time Complexities
-----------------
- **Access/Search**: :math:`O(n)`
- **Insertion/Deletion** (with node reference): :math:`O(1)`
- **Insertion/Deletion** (by value): :math:`O(n)`

Advantages
----------
- Allows bidirectional and circular traversal.
- No need to reset pointers manually when cycling through the list.
- Efficient insertion and deletion at both ends.

Disadvantages
-------------
- Slightly more complex to implement.
- Requires extra memory for `prev` pointers.

Use Cases
---------
- Music playlists (looping).
- Game players' turn rotation.
- Browser tab switching.

Example (Python)
----------------
::

    class Node:
        def __init__(self, data):
            self.data = data
            self.prev = None
            self.next = None

    class CircularDoublyLinkedList:
        def __init__(self):
            self.head = None

        def append(self, data):
            new_node = Node(data)
            if not self.head:
                self.head = new_node
                new_node.next = new_node
                new_node.prev = new_node
                return
            tail = self.head.prev
            tail.next = new_node
            new_node.prev = tail
            new_node.next = self.head
            self.head.prev = new_node

        def print_forward(self):
            if not self.head:
                return
            current = self.head
            while True:
                print(current.data, end=" <-> ")
                current = current.next
                if current == self.head:
                    break
            print("(head)")

        def print_backward(self):
            if not self.head:
                return
            current = self.head.prev
            while True:
                print(current.data, end=" <-> ")
                current = current.prev
                if current == self.head.prev:
                    break
            print("(tail)")

    # Example usage
    cdll = CircularDoublyLinkedList()
    cdll.append(1)
    cdll.append(2)
    cdll.append(3)
    cdll.print_forward()   # Output: 1 <-> 2 <-> 3 <-> (head)
    cdll.print_backward()  # Output: 3 <-> 2 <-> 1 <-> (tail)
