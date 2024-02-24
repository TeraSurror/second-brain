They are like lists in other languages

```rust
let v: Vec<i32> = Vec::new(); // create an empty vector
let v1 = vec![1, 2, 3, 4, 5, 6];

// Updating a vector
let mut v = Vec::new();
v.push(5);
v.push(9);

// reading elements of a vector
let v = vec![1, 2 ,3];
let third: &i32 = &v[2]; // third value in the vector 
let third: Option<&i32> = v.get(2); // same as above
match third {
	Some(third) => println!("The third element is {third}"),
	None => println!("invalid index");
}
```