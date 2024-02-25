A test in Rust is a function that is annotated with the `test` attribute

Example test in Rust

```rust
#[cfg(test)]
mod tests {
	#[test]
	fn it_works() {
		let result = 2 + 2;
		assert_eq!(result, 4); // checks for equality
		assert_ne!(result, 10); // checks for not equal
	}

	// Test with the Result enum
	#[test]
	fn it_works() -> Result<(), String> {
		if 2 + 2 == 4 {
			Ok(())
		} else {
			Err(String::from("two plus twp does not equal four"));
		}
	}
}
```

Run test synchronously: `cargo test -- -test-threads=1`
 
Show standard o/p when running tests: `cargo test -- -show-output`

Running test by name: `cargo test one_hundred`

Running ignored tests: `cargo test -- -ignored`

