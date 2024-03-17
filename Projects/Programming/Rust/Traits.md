Describes functionality a particular type has and can share with other types
They are like interfaces

```rust
// trait definition
pub trait Summary {
	fn summarize(&self) -> String;
}

pub struct NewsArticle {
	pub headline: String,
	pub location: String,
	pub author: String,
	pub content: String,
}

impl Summary for NewsArticle {
	fn summarize(&self) -> String {
		format!("{}, by {} ({})", self.headline, self.author, self.location)
	}
} 

pub struct Tweet {
	pub username: String;
	pub content: String;
	pub reply: bool;
	pub retweet: bool;
}

impl Summary for Tweet {
	fn summarize(&self) -> String {
		format!("{}: {}", self.username, self.content)
	}
}
```

Default Implementation
```rust
pub trait Summary{
	fn summarize(&self) -> String {
		String::from("(Read more...)")
	}
}
```

Traits as Parameters
```rust
// Here item can be any type that implements the Summary trait
// Note: the & means borrowed value, you can do without it
pub fn notify(item: &impl Summary) {
	println!("Breaking new! {item.summarize()}");
}

// trait bound syntax
pub fn notify<T: Summary>(item: &T) {
	println!("Breaking new! {item.summarize()}");
}

// this example allows item1 and item2 to have different types
fn notify(item1: &impl Summary, item2: &impl Summary) {
	// Here item1 can be of type Tweet
	// item2 can be of type NewsArticle
	// both types implement Summary
}

// This forces item1 and item2 to have the same type
fn notify<T: Summary> (item1: &T, item2: &T) {
	// snippet...
}
```


Multiple Traits
```rust
pub fn notify(item: &(impl Summary + Display)) {
	// snippet...
}

// Same as above
pub fn notify<T: Summary + Display>(item: &T) {
	// snippet...
}
```

### where clauses for clearer trait bounds

```rust
fn some_function<T: Display + Clone, U: Clone + Debug>(t: &T, u: &U) -> i32 {
	// snippet...
}

// same as above
fn some_function<T, U>(t: &T, u: &U) -> i32
where
	T: Display + Clone
	U: Clone + Debug
{
	// snippet...
}
```

### Conditionally implement methods using trait bounds
```rust
struct Pair<T> {
	x: T,
	y: T,
}

impl<T> Pair<T> {
	fn new(x: T, y: T) -> Self {
		Self {x, y}
	}
}

// only Pair structs with T that implement PartialOrd and Display can call this method
impl<T: Display + PartialOrd> Pair<T> {
	fn cmp_display(&self) {
		if self.x >= self.y {
			println!("The largest member is x = {}", self.x);
		} else {
			println!("The largest number is y = {}", self.y);
		}
	}
}
```
