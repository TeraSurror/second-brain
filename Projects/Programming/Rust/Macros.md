#### How to make a macro
```rust
// in this example we create a simple implementation of the vec macro

#[macro_export]
macro_rules! vec {
	// ( $( $x: expr ),* ) is like a match expression
	( $( $x:expr ),* ) => {
		{
			let mut temp_vec = Vec::new();
			$(
				temp_vec.push($x);
			)
			temp_vec
		}
	};
}
```