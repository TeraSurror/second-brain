#### match Arms
```rust
match VALUE {
	PATTERN => EXPRESSION,
	PATTERN => EXPRESSION,
	PATTERN => EXPRESSION,
	PATTERN => EXPRESSION,
}

// Matching literals
let x = 1;
match x {
	1 => println!("one");
	2 => println!("two");
	3 => println!("three");
	_ => println!("any other number");
}


// Multiple patterns
let x = 1;
match x {
	1 | 2 => println!("one or two"),
	3..=5 => println!("3 through 5"),
	_ => println!("Anything"),
}

// Destructuring structs
let p = Point {x: 0, y: 7};

match p {
	Point{x, y: 0} => println!("on the x axis at {x}"),
	Point{x: 0, y} => println!("on the y axis at {y}"),
	Point {x, y} => println!("Not on either axis"),
}

// Destructing Eums
enum Color {
    Rgb(i32, i32, i32),
    Hsv(i32, i32, i32),
}

enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    ChangeColor(Color),
}

fn main() {
    let msg = Message::ChangeColor(Color::Hsv(0, 160, 255));

    match msg {
        Message::ChangeColor(Color::Rgb(r, g, b)) => {
            println!("Change color to red {r}, green {g}, and blue {b}");
        }
        Message::ChangeColor(Color::Hsv(h, s, v)) => {
            println!("Change color to hue {h}, saturation {s}, value {v}")
        }
        _ => (),
    }
}


// Match Guard
let num = Some(4);

match num {
	Some(x) => if x % 2 == 0 => println!("The number {} is even"),
	Some(x) => println!("Number is odd"),
	None => println!("How does someone even reach here?");
}

// @ bindings
// Lets us hold a value while we are pattern matching it
enum Message {
	Hello {id: i32},
}

let msg = Message::Hello { id: 5 },

match msg {
	Message::Hello {
		id: id_variable @ 3..=7,
	} => println!("Found an id in range: {}", id_variable),
	Message::Hello { id: 10..=12 } => {
		println!("Found an id in another range")
	}
	Message::Hello { id } => println!("Found some other id: {}", id),
}

```

#### `if let` statements
```rust
fn main() {
	let favorite_color: Option<&str> = None;
	if let Some(color) = favorite_color {
		println!("Your favorite color is {}", color);
	} else {
		println!("You do not have a favorite color :(");
	}
}
```

#### `while let` statements
```rust
let mut stack = Vec::new();
stack.push(1);
stack.push(2);
stack.push(4);

while let Some(top) = stack.pop() {
	println!("Current top: {}", top);
}
```

#### `for` Loops
```rust
let v = vec![1, 2, 3, 4];

for (index, value) in v.iter().enumerate(){
	println!("{} exists at index {}", value, index);
}
```
