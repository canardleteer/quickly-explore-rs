# Run the new version

You can declare a whole lot more with `clap`, like commands, sub-commands, etc. But we're not going to do any of that.

- Build it:

```shell
cargo build
```

- Run it this way `./target/debug/quickly-explore-rs --help`:

```shell
-> ./target/debug/quickly-explore-rs --help
Usage: quickly-explore-rs [OPTIONS]

Options:
  -n, --name <NAME>  Name of the person to greet [env: HELLO_WORLD_NAME=] [default: "Rust Learning Person"]
  -h, --help         Print help
  -V, --version      Print version
```

Wow, we got a whole lot out of the box from that, and in general those add-ons do what you expect them to.

- Let's try it two ways:

```shell
-> ./target/debug/quickly-explore-rs --name "Some Real Name"
Hello, Some Real Name!

-> HELLO_WORLD_NAME="Some Real Name" ./target/debug/quickly-explore-rs
Hello, Some Real Name!
```
