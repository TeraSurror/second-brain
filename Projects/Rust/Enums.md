enums give a way of saying that a value is one set of possible values

```rust
enum IpAddrKind {
	V4,
	V6,
}

let four = IpAddrKind::V4;
let six = IpAddrKind::V6;
```

Enums can also contain values
```rust
enum IpAddrKind {
	V4(String),
	V6(String),
}

let ip_4 = IpAddrKind::V4(String::from("127.0.0.1"));
```

We can define methods on enums
```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    ChangeColor(i32, i32, i32),
}
struct QuitMessage; // unit struct
struct MoveMessage {
    x: i32,
    y: i32,
}
struct WriteMessage(String); // tuple struct
struct ChangeColorMessage(i32, i32, i32); // tuple struct

impl Message {
	fn call(&self) {
		// some method call
	}
}

let m = Message::Write(String::from("hello"));
m.call();
```


Option Enum
```rust
enum Option<T> {
	None,
	Some(T)
}
```

### Match
```rust
#[derive(Debug)]
enum UsState { Alabama, Alaska, // --snip-- }

enum Coin {
	Penny,
	Nickel,
	Dime,
	Quarter(UsState),
}

fn value_in_cents(coin: Coin) -> u8 {
	match coin {
		Coin::Penny => 1,
		Coin::Nickel => 5,
		Coin::Dime => 10,
		Coin::Quarter(state) => {
			println!("State quarter from {:?}!", state);
			25
		},
	}
}
```

Catch all pattern
```rust
let dice_roll = 9;
match dice_roll {
 3 => add_fancy_hat(),
 7 => remove_fancy_hat(),
 other => move_player(other), // we can use _ ,instead of other, if we don't want to use the other value
}
```

### If let
```rust
let config_max = Some(3u8);
if let Some(max) = config_max {
	println!("The max is configured to be {}", max);
}
```