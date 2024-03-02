### Hello world
```rust
fn main() {
	println!("Hello, world"); // The println! is a macro
}
```

### Cargo
Create project: `cargo new`
Build project: `cargo build`
Run project: `cargo run`
Build project without exe: `cargo check`
Build for release: `cargo build --release`
Install binaries: `cargo install`

### Variables and Mutability

Variables are immutable by default
```rust
let var_name = 5; // immutable variable
let mut var_name_1 = 5; // mutable variable
const VAR_NAME = "some value"; // constant in rust
```

### Compound Types
```rust
// Tuples
let tup: (i32, f64, u8) = (500, 10.1, 1);
let (x, y, z) = tup;
let tup1: (i32, f64, u8) = (500, 10.1, 1);
let five_hundo = tup1.0;


// Arrays
let a: [i32; 5] = [1, 2, 3, 4, 5];
let a = [3; 5] // same as [3, 3, 3, 3, 3]

```

### Loops
```rust
loop {
	println!("again");
}

// returning values in loop
let a = loop {
	counter += 1;
	if counter == 10 {
		break counter * 2; // return value
	}
} // a will have the value of counter

// while loops
let mut number = 3;
while number != 0 {
	println("{number}");
	number -= 1;
}

// for loops
let a = [1, 2, 3, 4, 5];
for element in a {
	println!("the value is: {element}");
}

(1..4) // generates numbers 1,2,3 - start inclusive and end non inclusive
```

