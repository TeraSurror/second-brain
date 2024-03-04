### Creating a new thread

```rust
// The following code creates a new thread
fn main() {
	thread::spwan(|| {
		for i in 1..10 {
			println!("hi number {} from the spwaned thread");
			thread::sleep(Duration::from_millis(1));
		}
	});

	for i in 1..5 {
		println!("hi number {} from the main thread");
		thread::sleep(Duration::from_millis(1));
	}
}
```

When the main thread of a Rust program completes, all the spawned threads are shut down, whether they have finished running.

### Waiting for all threads to complete 

```rust
// The following code creates a new thread
fn main() {
	// store the return value of the thread
	// thread::spwan returns JoinHandle
	// calling join on JoinHandle will ensure that the thread completes excecution.
	let handle = thread::spwan(|| {
		for i in 1..10 {
			println!("hi number {} from the spwaned thread");
			thread::sleep(Duration::from_millis(1));
		}
	});

	for i in 1..5 {
		println!("hi number {} from the main thread");
		thread::sleep(Duration::from_millis(1));
	}

	// calling join blocks the main thread and completes its execution
	handle.join().unwrap();
}
```

### Using `move` Closures with Threads
Reminder: `move` allows the closure to take ownership of the values that are passed to it

```rust
fn main() {
	let v = vec![1,2,3];

	// we need the move keyword here because the compiler does not know if the reference to v will be valid or not
	// v can be dropped by the main thread before the spawned thread completes execution
	// hence we have to pass ownership of the variable to the thread
	let handle = thread::spwan(move || {
		println!("Here's a vector: {:?}", v);
	});

	handle.join().unwrap();
}
```

### Message passing to transfer data b/w threads

Rust uses channels to accomplish message passing concurrency

```rust
fn main() {
	// creates a channel
	let (transmitter, receiver) = mpsc::channel();

	thread::spwan(move || {
		let val = String::from("hi");
		// We have used move to transfer ownership of transmitter
		// Send the string val
		// Note: the send function takes ownership of the value passed
		transmitter.send(val).unwrap();
	});

	// the recv() method blocks the other threads till it revceives a value
	let received = receiver.recv().unwrap();
	println!("Got: {}", received);
}
```

Using multiple producers
```rust
fn main() {
	let (tx, rx) = mpsc::channel()

	// create a new tranmitter
	let tx1 = tx.clone();
	
	thread::spawn(move || {
		let vals = vec![
			String::from("hi"),
			String::from("from"),
			String::from("the"),
			String::from("thread"),
		];

		for val in vals {
			tx1.send(val).unwrap();
			thread::sleep(Duration::from_secs(1));
		}
	});

	thread::spawn(move || {
		let vals = vec![
			String::from("mike"),
			String::from("cash"),
			String::from("one"),
			String::from("two"),
			String::from("three"),
		];

		for val in vals {
			tx.send(val).unwrap();
			thread::sleep(Duration::from_secs(1));
		}
	});

	// Receives values from both the transmitters
	for received in rx {
		println!("Got: {}", received);
	}
}
```


### Mutex in Rust

Mutex allows only one thread to access some data at given time.

Remember 2 rules 
1. you must attempt to acquire the lock before using the data.
2. when you are done with the data that the mutex guards, you must unlock the data, so that the other threads can acquire the lock and use it.

```rust
fn main() {
	let m: Mutex<i32> = Mutex::new(5);
	{
		// lock() method to aquire the lock on the mutex
		let mut num = m.lock().unwrap();
		*num = 6;
	}
	println!("m = {:?}", m);
}
```


#### Sharing mutex between threads

`Arc<T>` is a type that is safe to use in concurrent situations.
It is an atomic type that is safe to share across threads.

```rust
// Spins up 10 threads an increments the counter in the mutex by one
fn main() {
	
	// Arc makes it safe to share this mutex between threads
	let counter = Arc::new(Mutex::new(0));
	let mut handles = vec![];

	for _ in 0..10 {
		let handle = thread::spawn(move || {
			let counter = Arc::clone(&counter);
			let mut num = counter.lock().unwrap();
			*num += 1;
		});
		handles.push(handle);
	}

	for handle in handles {
		handle.join().unwrap();
	}

	println!("Result: {}", *counter.lock().unwrap());
}
```


### Send and Sync traits
Read this: https://doc.rust-lang.org/stable/book/ch16-04-extensible-concurrency-sync-and-send.html