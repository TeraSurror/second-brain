
```rust
// Program to find the largest in a list
fn largest<T: std::cmp::PartialOrd>(list: &[T]) -> &T {
	let mut largest = &list[0];

	for item in list {
		if item > largest {
			largest = item;	
		}
	}

	largest
}
```

```rust
// Generics in struts
struct Point<T> {
	x: T,
	y: T,
}

// Generics on methods 
impl<T> Point<T> {
	fn x(&self) -> &T {
		&self.x
	}
} 
// In this code, we imply that x and y have the same typing
// If we initialize x and y with different types, the code will not compile

// Different types
struct Point<T, U> {
	x: T,
	y: U,
}
```

```rust
enum Option<T> {
	Some(T),
	None,
}

enum Result<T, E> {
	Ok(T),
	Err(E),
}
```