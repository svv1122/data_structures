=====
Array
=====


Description
===========

In computer science, an array is a data structure consisting of a collection of elements (values or variables), 
of **same memory size**, each identified by at least one array index or key, a collection of which may be a tuple, 
known as an index tuple. An array is stored such that the position (memory address) of each element can be 
**computed** from its index tuple by a mathematical formula.[1][2][3] The simplest type of data structure is a 
linear array, also called a one-dimensional array.

.. Reference: https://en.wikipedia.org/wiki/Array_(data_structure)


Application
===========

* The implementation of vector, hash table, string
* The dynamic memory allocation
* To determine partial or complete control flow


Implementation
==============

.. code:: rust

    use std::fmt::Display;

    struct Array<T> {
        data: Box<[Option<T>]>,
        length: usize,
    }

    impl<T: Clone> Array<T> {
        fn new(capacity: usize) -> Self {
            let vec = vec![None; capacity];

            Array {
                data: vec.into_boxed_slice(),
                length: 0,
            }
        }

        fn insert(&mut self, value: T) -> Result<(), &str> {
            if self.length >= self.data.len() {
                return Err("Array is full");
            }

            for i in 0..self.data.len() {
                if self.data[i].is_none() {
                    self.data[i] = Some(value);
                    self.length += 1;
                    return Ok(());
                }
            }

            Err("Array is full")
        }

        fn delete(&mut self, index: usize) -> Result<(), &str> {
            if index >= self.data.len() {
                return Err("index out of range");
            }

            if self.data[index].is_some() {
                self.data[index] = None;
                self.length -= 1;
                Ok(())
            } else {
                Err("element already empty")
            }
        }

        fn get(&self, index: usize) -> Option<&T> {
            if index >= self.data.len() {
                return None;
            }

            self.data[index].as_ref()
        }

        fn display(&self)
        where
            T: Display,
        {
            for item in &self.data[..] {
                match item {
                    Some(v) => print!(" [{}] ", v),
                    None => print!(" [ ] "),
                }
            }
            println!();
        }
    }
