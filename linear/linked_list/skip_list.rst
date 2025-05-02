=========
Skip List
=========
A **skip list** is a probabilistic data structure that allows fast search, insertion, and deletion operations within an ordered sequence of elements.
It is an alternative to balanced trees, offering simpler implementation with similar average time complexities.

A skip list consists of multiple layers of linked lists. The bottom layer is a standard sorted linked list, and each higher layer acts as an "express lane"
to skip over many elements in lower levels, accelerating operations like search.

Each element in the skip list appears in the bottom layer, and with a certain probability (typically 1/2), it is "promoted" to the layer above.

Advantages
----------
- Average-case time complexity:
  
  - Search: :math:`O(\log n)`
  - Insert: :math:`O(\log n)`
  - Delete: :math:`O(\log n)`

- Simpler to implement than red-black trees or AVL trees.
- Efficient for concurrent access with lock-free or fine-grained locking strategies.

Structure
---------
A skip list node typically contains:

- A key or value
- Multiple forward pointers (one per level the node appears in)

Example (ASCII Representation):
::

    Level 3:       [ ] ----> [ ] ----> [ ]
    Level 2:       [ ] ----> [ ] ----> [ ]
    Level 1: [head] ----> [1] ----> [3] ----> [5] ----> [7] ----> [9]

Applications
------------
- Databases and key-value stores (e.g., Redis)
- In-memory indexing
- Ordered maps and sets in programming libraries

References
----------
- Pugh, William. "Skip lists: a probabilistic alternative to balanced trees." *Communications of the ACM*, 1990.
- `Wikipedia: Skip list <https://en.wikipedia.org/wiki/Skip_list>`_
