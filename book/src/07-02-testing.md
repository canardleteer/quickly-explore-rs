# Testing

Unit/Integration testing is built into Rust, and [it's in the book](https://doc.rust-lang.org/book/ch11-00-testing.html). Use it before digging into frameworks that extend this functionality.

If you want, *as an extremely simple example*, you can add the following to the bottom of `src/main.rs`:

```rust
#[test]
fn some_test() {
    assert!(1==1);
}
```

Then run `cargo test`:

```shell
-> cargo test
   Compiling quickly-explore-rs v0.1.0 (/home/canardleteer/dev/quickly-explore-rs)
    Finished test [unoptimized + debuginfo] target(s) in 0.27s
     Running unittests src/main.rs (target/debug/deps/quickly_explore_rs-42636154716fb90c)

running 1 test
test some_test ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s
```

There's a lot more in this space available than that.
