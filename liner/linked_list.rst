===========
Linked list
===========


Description
===========

In computer science, a linked list is a linear collection of data elements whose order is not 
given by their physical placement in memory. Instead, each element points to the next. It is 
a data structure consisting of a collection of nodes which together represent a sequence. In 
its most basic form, each node contains data, and a reference (in other words, a link) to the 
next node in the sequence. This structure allows for efficient insertion or removal of elements 
from any position in the sequence during iteration. More complex variants add additional links, 
allowing more efficient insertion or removal of nodes at arbitrary positions. A drawback of linked 
lists is that data access time is linear in respect to the number of nodes in the list. Because nodes 
are serially linked, accessing any node requires that the prior node be accessed beforehand (which 
introduces difficulties in pipelining). Faster access, such as random access, is not feasible. Arrays 
have better cache locality compared to linked lists.

Linked lists are among the simplest and most common data structures. They can be used to implement 
several other common abstract data types, including lists, stacks, queues, associative arrays, and 
S-expressions, though it is not uncommon to implement those data structures directly without using 
a linked list as the basis.

The principal benefit of a linked list over a conventional array is that the list elements can be easily 
inserted or removed without reallocation or reorganization of the entire structure because the data items 
do not need to be stored contiguously in memory or on disk, while restructuring an array at run-time is a 
much more expensive operation. Linked lists allow insertion and removal of nodes at any point in the list, 
and allow doing so with a constant number of operations by keeping the link previous to the link being added 
or removed in memory during list traversal.

On the other hand, since simple linked lists by themselves do not allow random access to the data or any form 
of efficient indexing, many basic operations—such as obtaining the last node of the list, finding a node that 
contains a given datum, or locating the place where a new node should be inserted—may require iterating through 
most or all of the list elements.

.. Reference: https://en.wikipedia.org/wiki/Linked_list


Application
===========

* The implementation of tree
* The base of the virtual memory


Implementation
==============

.. code:: rust

    use std::fmt;

    #[derive(Debug)]
    struct Node<T> {
        value: T,
        next: Option<Box<Node<T>>>,
    }

    #[derive(Debug)]
    struct LinkedList<T> {
        head: Option<Box<Node<T>>>,
    }

    impl<T> LinkedList<T> {
        fn new() -> Self {
            LinkedList { head: None }
        }

        fn push(&mut self, value: T) {
            let new_node = Box::new(Node {
                value,
                next: self.head.take(),
            });
            self.head = Some(new_node);
        }

        fn pop(&mut self) -> Option<T> {
            self.head.take().map(|node| {
                self.head = node.next;
                node.value
            })
        }

        fn peek(&self) -> Option<&T> {
            self.head.as_ref().map(|node| &node.value)
        }
    }

    impl<T: fmt::Display> fmt::Display for LinkedList<T> {
        fn fmt(&self, f: &mut fmt::Formatter<'_>) -> fmt::Result {
            let mut current = &self.head;
            write!(f, "[");
            while let Some(node) = current {
                write!(f, "{}", node.value)?;
                current = &node.next;
                if current.is_some() {
                    write!(f, " -> ");
                }
            }
            write!(f, "]")
        }
    }
