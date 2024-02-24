string slice `str` type is provided by the core lib of rust
The `String` type, which is provided by Rust’s standard library rather than coded into the core language, is a growable, mutable, owned, UTF-8 encoded string type.

```rust
// Creating a new string
let mut s = String::new();
let s = "some string content".to_string();

let s = String::from("some string value"); // immutable

let mut s = String::from("foo");
s.push_str("bar"); // s = "foobar"

let s1 = String::from("Hello, "); 
let s2 = String::from("world!");
let s3 = s1 + &s2; // note s1 has been moved here and can no longer be used

let s1 = String::from("tic");
let s2 = String::from("tac");
let s3 = String::from("toe");
let s = format!("{s1}-{s2}-{s3}");

```
