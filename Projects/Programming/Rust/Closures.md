1. Anonymous function that capture their environment.
2. They capture values from the scope they are defined in.

```rust
// Examples of closures: all do the same thing and can be used in the same way
let add_one_v1 = |x: u32| -> i32 {x + 1};
let add_one_v2 = |x| {x + 1};
let add_one_v3 = |x| x + 1;

let expensive_closure = |num: u32| -> u32 {
	println!("calculating slowly...");
	thread::sleep(Duration::from_secs(2));
	num
}
```


Closures can capture values from the env in 3 ways:
1. Borrowing immutably

```rust
let list = vec![1,2,3];

let only_borrow = || println!("From closure: {:?}", list);
only_borrow();
```

2. Borrowing Mutably

```rust
let mut list = vec![1,2,3];

let mut_borrow = || list.push(4); // mutable borrow occures here
//No borrow can occur now as a mutable borrow exists
println!("{:?}", list); // This will give an error!!
mut_borrow();
```

3. Taking ownership

```rust
let list = vec![1,2,3];

thread::spawn(move || println!("From thread: {:?}", list))
	.join()
	.unwrap();
```


#### Fn Traits
The way a closure captures and handles values from the environment affects which traits the closure implements, and traits are how functions and structs can specify what kinds of closures they can use. Closures will automatically implement one, two, or all three of these Fn traits, in an additive fashion, depending on how the closure’s body handles the values:
1. FnOnce applies to closures that can be called once. All closures implement at least this trait, because all closures can be called. A closure that moves captured values out of its body will only implement FnOnce and none of the other Fn traits, because it can only be called once.
2. FnMut applies to closures that don’t move captured values out of their body, but that might mutate the captured values. These closures can be called more than once.
3. Fn applies to closures that don’t move captured values out of their body and that don’t mutate captured values, as well as closures that capture nothing from their environment. These closures can be called more than once without mutating their environment, which is important in cases such as calling a closure multiple times concurrently.