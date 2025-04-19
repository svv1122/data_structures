=====
Stack
=====


Description
===========

In computer science, a stack is an abstract data type that serves as a collection 
of elements with two main operations:

    Push, which adds an element to the collection, and
    Pop, which removes the most recently added element.

Additionally, a peek operation can, without modifying the stack, return the value 
of the last element added. The name stack is an analogy to a set of physical items 
stacked one atop another, such as a stack of plates.

The order in which an element added to or removed from a stack is described as **last 
in, first out**, referred to by the acronym **LIFO**.[nb 1] As with a stack of physical objects, 
this structure makes it easy to take an item off the top of the stack, but accessing a 
datum deeper in the stack may require removing multiple other items first.[1]

Considered a sequential collection, a stack has one end which is the only position at which 
the push and pop operations may occur, the top of the stack, and is fixed at the other end, 
the bottom. A stack may be implemented as, for example, a singly linked list with a pointer 
to the top element.

A stack may be implemented to have a bounded capacity. If the stack is full and does not contain 
enough space to accept another element, the stack is in a state of **stack overflow**. 

Reference: `https://en.wikipedia.org/wiki/Stack_(abstract_data_type)`


Application
===========

* The back/forward in web browser
* The memory management of threads
* The backtracking algorithm


Implementation
==============

.. code:: rust

    struct Stack<T> {
        elements: Vec<T>,
        capacity: usize,
    }

    impl<T> Stack<T> {
        fn new(capacity: usize) -> Self {
            Stack {
                elements: Vec::with_capacity(capacity),
                capacity,
            }
        }

        fn push(&mut self, item: T) -> Result<(), &str> {
            if self.elements.len() < self.capacity {
                self.elements.push(item);
                Ok(())
            } else {
                Err("Stack overflow")
            }
        }

        fn pop(&mut self) -> Option<T> {
            self.elements.pop()
        }

        fn peek(&self) -> Option<&T> {
            self.elements.last()
        }

        fn is_empty(&self) -> bool {
            self.elements.is_empty()
        }

        fn size(&self) -> usize {
            self.elements.len()
        }
    }
