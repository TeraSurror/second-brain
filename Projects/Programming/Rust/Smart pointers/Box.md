Allows you to store data on the heap rather than the stack.

Use cases:
1. When you have a type whose size can't be known at compile time and you want to use a value of that type in  a context that requires an exact size.
2. When you have a large amount of data and you want to transfer ownership but ensure the data won't be copied when you do so.
3. When you want to own a value and you care only that it's a type that implements a particular trait than being of a specific type.


### Storing data on the heap
```rust
let b = Box::new(5); // stored on the heap
println!("b={}", b);
```

### Recursive types with Boxes
Think Linked Lists
```rust
struct Node<T> {
	val: T, 
	next: Option<Box<Node<T>>>
}

impl<T> Node<T> {
	fn new(data: T) -> Self {
		Node {
			val: data,
			next: None,
		}
	}
}

struct LinkedList<T> {
	head: Option<Box<Node<T>>>,
}

impl<T> LinkedList<T> {
	fn new() -> Self {
		LinkedList {
			head: None,
		}
	}
	
	fn add(&mut self, data: T) {
		let new_node = Box::new(Node::new(data));
		if let Some(ref mut head) = self.head {
			let mut current = head;
			while let Some(ref mut next) = current.next {
				current = next;
			}
			current.next = Some(new_node);
		} else {
			self.head = Some(new_node);
		}
	}
}
```