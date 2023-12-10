# Lint the changed code

- Let's see if the code smells right via `cargo clippy`:

```shell
-> cargo clippy
    Checking quickly-explore-rs v0.1.0 (/home/canardleteer/dev/quickly-explore-rs)
warning: unused variable: `name`
  --> src/main.rs:22:9
   |
22 |     let name = args.name.clone();
   |         ^^^^ help: if this is intentional, prefix it with an underscore: `_name`
   |
   = note: `#[warn(unused_variables)]` on by default

warning: `quickly-explore-rs` (bin "quickly-explore-rs") generated 1 warning (run `cargo clippy --fix --bin "quickly-explore-rs"` to apply 1 suggestion)
    Finished dev [unoptimized + debuginfo] target(s) in 0.09s
```

Oh yeah, I guess we aren't using `name`. Go ahead and delete that line, or
follow the linters suggestion of prefixing it with an underscore if you want
to use it for something else.

There are 4 other options, which would be to disable linting of that specific rule (`unused_variables`) for:

- That line
- That function
- That module
- The whole package

But I won't go into that. The linter isn't always right, but often is. You
have many options that don't involve disabling the linter completely. Don't
disable the linter completely. Not using the linter at all is not a reasonable
5th option.

- Run `cargo clippy` again:

```shell
-> cargo clippy
    Checking quickly-explore-rs v0.1.0 (/home/canardleteer/dev/quickly-explore-rs)
    Finished dev [unoptimized + debuginfo] target(s) in 0.12s
```

That's it! You are now ready to ship your customizable Hello World experience to the world.
