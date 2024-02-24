### panic!

Sometimes, bad things happen in your code, and there’s nothing you can do about it. In these cases, Rust has the `panic!` macro. 

There are two ways to cause a panic in practice: by taking an action that causes our code to panic (such as accessing an array past the end) or by explicitly calling the `panic!` macro. In both cases, we cause a panic in our program. 

By default, these panics will print a failure message, unwind, clean up the stack, and quit. 

Via an environment variable, you can also have Rust display the call stack when a panic occurs to make it easier to track down the source of the panic.


### Recoverable errors with Result
```rust
enum Result<T, E> {
	Ok(T),
	Err(E),
}
```

Example:
```rust
use std::fs::File;

fn main() {
    let greeting_file_result = File::open("hello.txt");

    let greeting_file = match greeting_file_result {
        Ok(file) => file,
        Err(error) => match error.kind() { 
	        ErrorKind::NotFound => match File::create("hello.txt") { 
		        Ok(fc) => fc, 
		        Err(e) => panic!("Problem creating the file: {:?}", e), 
		    }, 
		    other_error => { panic!("Problem opening the file: {:?}", other_error); 
		    } 
		},
    };
}
```

Unwrap and expect
```rust
let greeting_file = File::open("hello.txt").unwrap();

let greeting_file = File::open("hello.txt")
					.expect("hello.txt should be included in this project");
```