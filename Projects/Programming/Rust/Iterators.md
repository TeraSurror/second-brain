```rust
let v1 = vec![1,2,3];

let v1_iter = v1.iter(); // creates an iterator

for val in v1_iter {
	println!("Got: {}", val);
}
```

### Iterator trait
All iterators implement this trait
```rust
pub trait Iterator {
	type Item;
	fn next(&mut self) -> Option<Self::Item>;
	// additional stuff
}
```

```rust
// next() method in action
#[test] 
fn iterator_demonstration() { 
	let v1 = vec![1, 2, 3]; 
	let mut v1_iter = v1.iter(); 
	
	assert_eq!(v1_iter.next(), Some(&1)); 
	assert_eq!(v1_iter.next(), Some(&2)); 
	assert_eq!(v1_iter.next(), Some(&3)); 
	assert_eq!(v1_iter.next(), None); 
}
```

### Methods that consume the iterator

These methods use up the iterator. That's why they are called consuming adaptors.

```rust
let v1 = vec![2,4,5];
let v1_iter = v1.iter();
// calculates the sum
let total: i32 = v1_iter.sum();
// v1_iter cannot be used after this point
```

### Methods that create another iterator

These methods do not consume the iterator. They are called iterator adaptors.
```rust
// Example of map method
let v1: Vec<i32> = vec![1,2,3,4];

// map modifies each element of the iterator and returns a new iterator
// Here map function increments each element by 1.
// collect consumes the iterator and returns a collection with all the elements of the iterator
let new_v1: Vec<i32> = v1.iter().map(|x| x + 1).collect();
```


