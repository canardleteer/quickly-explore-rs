# Clean up whatever changes you made (if any)

You can do some quick formatting and linting stuff:

```text
# will automatically clean up your code, where it can
cargo fmt

# will helpfully bark at you as you learn Rust patterns
cargo clippy
```

These are two tools are useful as pipeline steps for code
hygiene verification, but also **EXTREMELY USEFUL FOR
LEARNING AS YOU GO.**

Neither step above should make any changes on the default files in this
repository. It's just good to know they are there and work. `cargo fmt`,
by default, will format code on disk. If you don't wish to do that,
you'd want to use `cargo fmt --check`.
