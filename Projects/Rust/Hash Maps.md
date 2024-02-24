
```rust
// Creating a HashMap
use std::collections::HashMap;

let mut scores = HashMap::new();

// Inserting values in hashmap
scores.insert(String::from("Blue"), 10);
scores.insert(String::from("Yellow"), 50);

// Updating values in hashmap
scores.insert(String::from("Blue"), 20); // overriding the value
scores.entry(String::from("Blue")).or_insert(20); // only update if key not present
let text = "hello world wonderful world"; 
let mut map = HashMap::new(); 
for word in text.split_whitespace() { 
	let count = map.entry(word).or_insert(0); // returns a mutable reference 
	*count += 1; 
}

// accessing hashmap values
let team_name = String::from("Blue");
let score = scores.get(&team_name).copied().unwrap_or(0);

// Iterating over a hashmap
for (key, value) in &scores {
	println!("{key}: {value}");
}
```