### Heap vs Stack memory
Heap: Data with unknown size is stored here
Stack: Data with known size is stored here

Accessing data on the stack is faster than accessing data on the heap

In the stack, a fixed memory is allotted to the variable and it is directly stored on the stack.

With heaps, an arbitrary amount of memory is chosen and the pointer to the memory space is stored on the stack. So, variables who are allotted in heap memory usually refer to the pointer in the stack.

### Ownership rules
1. Every value in Rust has a owner
2. There is only one owner at a time
3. Is the owner goes out of scope, the value is dropped 

