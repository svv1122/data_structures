====================
Circular Linked List
====================
A **Circular Linked List (CLL)** is a variation of a singly linked list where the last node's `next` pointer points back to the head node, forming a circle.

Unlike a standard singly linked list, there is no `null` at the end; traversal continues infinitely unless explicitly stopped.

Structure
---------
Each node looks like this:
::

    +--------+--------+
    |  Data  |  Next  | ---> Points to the next node
    +--------+--------+
                          ↑
                          |
                     Head node

The `next` pointer of the last node points back to the first node.

Types
-----
- **Singly Circular Linked List**: Each node has only a `next` pointer, and the last node links to the head.
- **Doubly Circular Linked List**: Each node has both `next` and `prev` pointers, and links form a closed loop in both directions.

Operations
----------
1. **Traversal** – Loop through the list until you return to the head.
2. **Insertion**:
   - At the beginning.
   - At the end.
   - After a specific node.
3. **Deletion** – Remove a node by value or position.
4. **Search** – Locate a node by value.

Time Complexities
-----------------
- **Access/Search**: :math:`O(n)`
- **Insertion/Deletion**:
  - At beginning/end: :math:`O(n)` (or :math:`O(1)` if tail pointer is maintained)

Advantages
----------
- Can be efficiently used in applications where the list is repeatedly traversed.
- No need to reset pointers manually for circular operations.

Disadvantages
-------------
- Requires extra care to avoid infinite loops during traversal.
- Slightly more complex than linear singly linked lists.

Use Cases
---------
- CPU scheduling (round-robin).
- Multiplayer games (turn-based rotation).
- Streaming data buffers (circular queues).

Example (Python)
----------------
::

    class Node:
        def __init__(self, data):
            self.data = data
            self.next = None

    class CircularLinkedList:
        def __init__(self):
            self.head = None

        def append(self, data):
            new_node = Node(data)
            if not self.head:
                self.head = new_node
                new_node.next = self.head
                return
            current = self.head
            while current.next != self.head:
                current = current.next
            current.next = new_node
            new_node.next = self.head

        def print_list(self):
            if not self.head:
                return
            current = self.head
            while True:
                print(current.data, end=" -> ")
                current = current.next
                if current == self.head:
                    break
            print("(head)")

    # Example usage
    cll = CircularLinkedList()
    cll.append(10)
    cll.append(20)
    cll.append(30)
    cll.print_list()

    # Output: 10 -> 20 -> 30 -> (head)
