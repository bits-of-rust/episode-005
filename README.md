# episode-005
Where we discover immutabillity

## Setup
The following needs to be prepared

* A project with name `immutabillity`
* A variable `subject` with value `moon`
* A `println!` statement

## Script
We used a variable to reuse value multiple times.

```rust
let subject = "world";

println!("Hello, {}!", subject);
println!("Goodbye, {}!", subject);
```

If we want to greet the world and the moon, we could try to copy the `println!` statements and reassign the `subject` variable.

```rust
let subject = "world";


println!("Hello, {}!", subject);
println!("Goodbye, {}!", subject);

subject = "moon";

println!("Hello, {}!", subject);
println!("Goodbye, {}!", subject);
```

But [Rust][rust-lang] won't let us. Instead it reports a compile error

```
main.rs:7:5: 7:21 error: re-assignment of immutable variable `subject` [E0384]
main.rs:7     subject = "moon";
              ^~~~~~~~~~~~~~~~
main.rs:2:6: 2:13 note: prior assignment occurs here
main.rs:2 	let subject = "world";
          	    ^~~~~~~
error: aborting due to previous error
Could not compile `immutabillity`.

To learn more, run the command again with --verbose.
``` 

When we define a variable in [Rust][rust-lang] the default is to make the variable immutable. That means that we are not allowed to change the binding. This is what [Rust][rust-lang] complains about.

It could seems strange to make variable immutable by default, but it is a blessing in disguise. Immutability makes it easier to reason about programs.

If we really want to change a variable binding, [Rust][rust-lang] allows us if we tell if we declare our intent before hand. 

```rust
let mut subject = "world";
```

We can use the `mut` keyword when we define the variable to signal [Rust][rust-lang] that we might want to rebind the variable later in the program.

And there you have it, we discovered immutability.

[rust-lang]: https://www.rust-lang.org/
