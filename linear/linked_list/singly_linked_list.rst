==================
Singly Linked List
==================
A **Singly Linked List** is a linear data structure in which each element (called a *node*) contains two parts:
- **Data**: The actual value stored.
- **Next**: A pointer/reference to the next node in the list.

Unlike arrays, elements in a linked list are not stored in contiguous memory locations. Instead, each node points to the next, forming a chain.

Structure
---------
Each node has the following structure:
::

    +--------+--------+
    |  Data  |  Next  | ---> Points to the next node
    +--------+--------+

The last node’s `Next` is `null` (or `None` in Python), indicating the end of the list.

Operations
----------
1. **Traversal** – Visit each node from head to end.
2. **Insertion** – Add a node:
   - At the beginning
   - At the end
   - After a given node
3. **Deletion** – Remove a node:
   - By value
   - By position
4. **Search** – Find a node by its value.

Time Complexities
-----------------
- **Access**: :math:`O(n)`
- **Search**: :math:`O(n)`
- **Insertion at head**: :math:`O(1)`
- **Insertion at tail (without tail pointer)**: :math:`O(n)`
- **Deletion by value**: :math:`O(n)`

Advantages
----------
- Dynamic size (no need to define capacity ahead of time).
- Efficient insertions/deletions at the head.

Disadvantages
-------------
- No direct/indexed access to elements.
- More memory usage due to pointer storage.
- Linear time for search or access.

Use Cases
---------
- Implementing stacks and queues.
- Navigating history in web browsers.
- Undo functionality in text editors.

Example (Python)
----------------
::

    class Node:
        def __init__(self, data):
            self.data = data
            self.next = None

    class SinglyLinkedList:
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

        def print_list(self):
            current = self.head
            while current:
                print(current.data, end=" -> ")
                current = current.next
            print("None")

    # Example usage
    sll = SinglyLinkedList()
    sll.append(10)
    sll.append(20)
    sll.append(30)
    sll.print_list()

    # Output: 10 -> 20 -> 30 -> None
