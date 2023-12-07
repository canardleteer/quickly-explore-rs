
# Learning the Rust tools

## First Steps

The [upstream documentation](https://doc.rust-lang.org/cargo/getting-started/installation.html) is going to be better than mine.

- Start by going to [rustup.rs](https://rustup.rs/) to download the installer.
  - You are welcome to audit the shell script beforehand, since I don't
    recommend randomly piping curl to a shell, but that seems to be the
    way people do things now?
  - This sometimes fails for people. There's enough info in the shell script
    to manually do it.

```shell
# Take a look at what ya got:
rustup show

# Where did a bunch of stuff land?
rustup which cargo

# Install the Rust Formatter
rustup component add rustfmt

# Install the Rust Linter
rustup component add clippy
```

You are now setup with everything you should need.

If you want to:

- Learn more about the package manager (Cargo), I recommend starting with the [Cargo Book](https://doc.rust-lang.org/cargo/getting-started/)
- Learn more about writing Rust, I recommend starting with the [Rust Book](https://doc.rust-lang.org/book/)
- Just learn some basics... Keep reading.

### Historical Anchor

For reference, I'm writing this document against this particular version of Rust & Cargo:

```shell
-> rustup show
...
active toolchain
----------------

stable-x86_64-unknown-linux-gnu (default)
rustc 1.72.1 (d5c2e9c34 2023-09-13)
```



## VSCode

If you open this repository in VSCode, you will probably want to now install the following Extensions:

- [rust-analyzer](https://github.com/rust-lang/rust-analyzer)
- [CodeLLDB](https://github.com/vadimcn/codelldb)
- [Even Better TOML / Taplo](https://github.com/tamasfe/taplo)

And possibly whatever else comes recommended.

## This repository

I made this repository with:

```shell
cargo new quickly-explore-rs
```

It made a few files:

- `Cargo.toml`
  - Which defines your dependencies and a few other things.
- `.gitignore`
  - Which ignores the `target` directory, which is your build output.
- `src/main.rs`
  - Which is the source code for this application.

Files that may get generated for you:

- `target/*`
  - Your build directory.
- `Cargo.lock`
  - Dependency reification. [Documentation](https://doc.rust-lang.org/cargo/guide/cargo-toml-vs-cargo-lock.html)
  - If you're authoring an application, yes you commit it to your source tree. If you're authoring a library, no, you don't commit it.
  - **Even though this repository is an application, we are not commiting it, so it remains as generated.**

You can reproduce that if you'd like to.

## Welcome to your curated Hello World Experience

- Open up `src/main.rs`.

Cool, it's there. You're welcome to make changes if you wish to personalize your Hello World experience.

- Run it.

```shell
cargo run
```

I really don't like using `cargo` to run stuff, since it implies that you "need cargo to run what you built" 
(you don't) but you will find it handy if you setup multiple binaries in a repository.

Alternatively:

```shell
cargo build
./target/debug/quickly-explore-rs
```

But you probably hate the incredibly slow runtime performance of this Hello
World experience, we can speed that up:

```shell
cargo build --release
./target/release/quickly-explore-rs
```

Now we're cookin' with gas! Ship it!

## Clean up whatever changes you made (if any)

You can do some quick formatting and linting stuff:

```shell
cargo fmt # will automatically clean up your code, where it can
cargo clippy # will helpfully bark at you as you learn Rust patterns
```

These are useful pipeline steps for code hygiene, but also **EXTREMELY USEFUL FOR LEARNING AS YOU GO.**

## Recommendations

The following 3 recommendations are "worth knowing exist," before continuing.
**They aren't worth doing a deep dive into yet,** but you may want to come back
to this section later on to learn a little more.

### Recommendation: Sparse Indexing

`cargo` is changing it's indexing protocol, so I recommend performing whatever
action makes sense for you, to use the HTTP indexing by default, and spare
yourself much build slowness, by [going here for instructions](https://blog.rust-lang.org/inside-rust/2023/01/30/cargo-sparse-protocol.html).

This will probably eventually become a default, if it isn't already.

### Recommendation: Learn about toolchain pinning

`rust-toolchain.toml` is useful for tool pinning, you can
[learn about it here](https://rust-lang.github.io/rustup/overrides.html#the-toolchain-file).

### Recommendation: Learn about Cargo workspaces

It's worth knowing about Rust Workspaces, and you can
[learn about them here](https://doc.rust-lang.org/book/ch14-03-cargo-workspaces.html).

### Recommendation: Learn what a Rust Macro is

The macro sytax in Rust is extremely powerful, useful, but can appear to be a bit
arcane and "meta." It will be awhile before you understand why and where to use
macros, and that's before you understand how to. All that is okay.

You will use them all the time. If you see stuff like this:

- `#[derive(Something)]`
- `println!("something")`

...you are using a macro.

Like all Rust things, [there is a book you can read to learn more](https://veykril.github.io/tlborm/).

### Recommendation: Learn why there are all these nicely documented APIs and Books

- Most of the "books" are being generated from
  [mdbook](https://github.com/rust-lang/mdBook), which is useful
  for "humane documentation" around APIs or features. It's generally
  "just markdown files as input."

- APIs are documented via `rustdoc`, and it comes out of the box in Rust.
  You will find your normal code comments generally land where you'd expect
  them to in, but you can learn how to make it really nice by... You guessed
  it, reading the `rustdoc` book, [which is here](https://doc.rust-lang.org/rustdoc/what-is-rustdoc.html).

## Explore the ecosystem

The root level place folks head to for the Rust Ecosystem is:

- [crates.io](https://crates.io/)
  - Publishing crates to `crates.io` is a well understood topic.
  - It gets much more complex when dealing with private/internal crate repositories.
- You will add things here to your `Cargo.toml` file under `[dependencies]`
- Documentation, will be published to [docs.rs](https://docs.rs/)

`cargo` itself, has it's own ecosystem of tools, like:

- [cargo-generate](https://github.com/cargo-generate/cargo-generate) - Templates for Cargo
- [cargo-llvm-cov](https://github.com/taiki-e/cargo-llvm-cov) - Code Coverage (I end up using 2 different code coverage tools)
- [cargo-audit](https://github.com/RustSec/rustsec/tree/main/cargo-audit) - Rust specific vulnerability scanner
- ... plus a whole lot more...

### General starters for Service Engineering

- CLI Arg parsing: [clap](https://crates.io/crates/clap)
- Serialization / Deserialization: [serde](https://crates.io/crates/serde)
- [Awesome Rust](https://github.com/rust-unofficial/awesome-rust) is a curated list of useful crates.
- Asyncronous Rust: [async-book](https://rust-lang.github.io/async-book/)
  - I mostly use [tokio](https://tokio.rs/), but there is more than one runtime available (even for microcontrollers, [embassy](https://github.com/embassy-rs/embassy) is an example).
  - gRPC Services/Clients: [tonic](https://github.com/hyperium/tonic) (with [prost](https://github.com/tokio-rs/prost) for protobuf)
  - REST Services: [hyper](https://hyper.rs/)... Likley something built on top of `hyper`
  - HTTP Service Calls: [reqwest](https://github.com/seanmonstar/reqwest), but likley a client autogenerated via an OpenAPI crate (there are a few).
  - ["Are we web yet?"](https://www.arewewebyet.org/) is a website that generally contains a curated list of traditional service crates.
    - I personally don't use this list much, but it's useful to see what's out there.
  - [tokio-console](https://github.com/tokio-rs/console) is a good thing to know about.

- Kubernetes:
  - Kubernetes management (from Deployment, through Operators & Controllers to Schedulers): [kube.rs](https://kube.rs/)

- Tracing / Logging
  - Start by learning the [log](https://github.com/rust-lang/log) crate with `env_logger`.
  - Then learn about Tokio's [tracing](https://github.com/tokio-rs/tracing) crate.
    - Then, like myself, patiently await `tracing v0.2.x`
    - `tracing` can be hooked into observability stacks, but it's worth learning `tracing` first.

### Testing

Unit/Integration testing is built into Rust, and [it's in the book](https://doc.rust-lang.org/book/ch11-00-testing.html). Use it.

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

### Benchmarking

- I don't think Rust has "full support" for benchmarks without additional crates (yet).
- Benchmark tests (via the `#[bench]` macro) are a thing in Nightly Rust, these are good for simple things.
- I use [criterion.rs](https://github.com/bheisler/criterion.rs) for non-trivial benchmarking.
- You can learn about all of this from the [Rust Performance Book](https://nnethercote.github.io/perf-book/benchmarking.html).

## Docker images

- [Rust Build Toolchain Images on DockerHub](https://hub.docker.com/_/rust/), [source repo](https://github.com/rust-lang/docker-rust).

## Install a useful tool written in Rust

- `cargo install ripgrep`
  - [repo](https://github.com/BurntSushi/ripgrep)

## Quick Code Changes

Okay, we covered some really high level "rust ecosystem" stuff.

Let's make a code change.

### Add a crate

First, let's add the extremely useful `clap` library to our `Cargo.toml`. Start by checking out the [crate page](https://crates.io/crates/clap).

I am pinning the version, to `4.4.11`, and adding 2 Features: `derive` and `env`. "Features" are important to know about, but I'm not going to cover them here. You can [read up on them](https://doc.rust-lang.org/cargo/reference/features.html).

```shell
-> cargo add clap@4.4.11 --features derive,env
    Updating crates.io index
      Adding clap v4.4.11 to dependencies.
             Features:
             + color
             + derive
             + env
             + error-context
             + help
             + std
             + suggestions
             + usage
             - cargo
             - debug
             - deprecated
             - string
             - unicode
             - unstable-doc
             - unstable-styles
             - unstable-v5
             - wrap_help
```

Hopefully that worked for you like it did for me. If not, when you figure it
out, please submit a PR to this repository :)

### Use the new crate

Change `src/main.rs` to be this:

```rust
// Import the Parser trait.
use clap::Parser;

// Declare our CLI arguments.
#[derive(Parser, Debug)]
#[command(author, version, about, long_about = None)]
struct Args {
    /// Name of the person to greet
    #[arg(short, long, env = "HELLO_WORLD_NAME", default_value="Rust Learning Person")]
    name: String
}

// Say the line, robot.
fn main() {
    let args = Args::parse();

    let name = args.name.clone();
    println!("Hello, {}!", args.name);
}
```

### Run the new version

You can declare a whole lot more with `clap`, like commands, subcommands, etc.

Build it:

```shell
cargo build
```

Run it this way `./target/debug/quickly-explore-rs --help`:

```shell
-> ./target/debug/quickly-explore-rs --help
Usage: quickly-explore-rs [OPTIONS]

Options:
  -n, --name <NAME>  Name of the person to greet [env: HELLO_WORLD_NAME=] [default: "Rust Learning Person"]
  -h, --help         Print help
  -V, --version      Print version
```

Wow, we got a whole lot out of the box from that, and in general those add ons do what you expect them to.

Let's try it two ways:

```shell
-> ./target/debug/quickly-explore-rs --name "Some Real Name"
Hello, Some Real Name!

-> HELLO_WORLD_NAME="Some Real Name" ./target/debug/quickly-explore-rs
Hello, Some Real Name!
```

### Format the changed code (Your IDE may do this for you)

Let's check to see if that's good Rust, with `cargo fmt --check`:

```shell
-> cargo fmt --check
Diff in /home/canardleteer/dev/quickly-explore-rs/src/main.rs at line 6:
 #[command(author, version, about, long_about = None)]
 struct Args {
     /// Name of the person to greet
-    #[arg(short, long, env = "HELLO_WORLD_NAME", default_value="Rust Learning Person")]
-    name: String
+    #[arg(
+        short,
+        long,
+        env = "HELLO_WORLD_NAME",
+        default_value = "Rust Learning Person"
+    )]
+    name: String,
 }
 
 // Say the line, robot.
```

Looks like we didn't quite do that too legibly, but let's let the formatter do the work for us.

```shell
# Clean it up for us.
-> cargo fmt

# Verify it cleaned it up for us.
-> cargo fmt --check
-> 
```

Looking tidy!

### Lint the changed code (Your IDE may do this for you)

Let's see if the code smells right via `cargo clippy`:

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
- The whole crate

But I won't go into that. The linter isn't always right, but often is. You
have many options that don't involve disabling the linter completely. Don't
disable the linter completely. Not using the linter at all is not a reasonable
5th option.

```shell
-> cargo clippy
    Checking quickly-explore-rs v0.1.0 (/home/canardleteer/dev/quickly-explore-rs)
    Finished dev [unoptimized + debuginfo] target(s) in 0.12s
```

That's it! You are now ready to ship your customizable Hello World experience to the world.
