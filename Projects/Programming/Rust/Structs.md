Define structs
```rust
struct User {
	active: bool,
	username: String,
	email: String,
	sign_in_count: u64,
}
```

using structs
```rust
let mut user = User { // here, the entire instance is mutable, every field
	active: true, 
	username: String::from("someusername"),
	email: String::from("someusername@gmail.com"),
	sign_in_count: 1,
}

user.email = String::from("some@gmail.com");
```

structs from other structs
```rust
let user2 = User {
	email: String::from("user2@gmail.com"),
	..user1
} // same as the javascript syntax
```

Tuple structs
```rust
struct Color(i32, i32, i32);
struct Point(i32, i32);

fn main() {
	let black = Color(0, 0, 0);
	let origin = Point(0, 0);
}
```


Unit-like structs
```rust
struct AlwaysEqual;

fn main() {
	let subject = AlwaysEqual;
}
```


Methods in Rust
```rust
#[derive(Debug)]
struct Rectangle {
    width: u32,
    height: u32,
}

impl Rectangle {
    fn area(&self) -> u32 {
        self.width * self.height
    }
}

fn main() {
    let rect1 = Rectangle {
        width: 30,
        height: 50,
    };

    println!(
        "The area of the rectangle is {} square pixels.",
        rect1.area()
    );
}
```

Associated functions
```rust
impl Rectangle {
	fn square(size: i32) -> Self {
		Self {
			width: size,
			height: size,
		}
	}
}

let square = Rectangle::square(10); // call an associated fn
```