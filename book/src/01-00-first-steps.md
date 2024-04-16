# First Steps

## Clone This Repository

- The expectation, is that you have [the repository that hosts this book](https://github.com/canardleteer/quickly-explore-rs) open and available for reference.

```shell
git clone https://github.com/canardleteer/quickly-explore-rs.git
```

## Install Rust

- Start by going to [rustup.rs](https://rustup.rs/) to download the installer.
  - You are welcome to audit the shell script beforehand, since I don't
    recommend randomly piping curl to a shell (but that seems to be the
    way people do things now?)
  - This sometimes fails for people. There's enough info in the shell script
    to manually do it.

  - Poke around a little bit.

```text
# Take a look at what ya got:
rustup show

# Where did a bunch of stuff land?
rustup which cargo

# Install the Rust Formatter
rustup component add rustfmt

# Install the Rust Linter
rustup component add clippy
```

## Cargo

- `cargo` is the general **package manager** for the Rust ecosystem, and your general "entrypoint" into Rust.
  - It is also how you launch compiling your code (which is a package, or collection of packages).
  - The overall [Cargo documentation](https://doc.rust-lang.org/cargo/getting-started/installation.html) is going to be better than mine. This is just a quick tour.
  - In practice, calling the Rust compiler (`rustc`) directly, is rare.

```text
# What version did ya get?
cargo --version

# What can cargo do?
cargo --list
```

**You are now generally setup with everything you should need.**

If you want to:

- Learn more about the package manager (Cargo), I recommend starting with the [Cargo Book](https://doc.rust-lang.org/cargo/getting-started/)
- Learn more about writing in Rust, the language, I recommend starting with the [Rust Book](https://doc.rust-lang.org/book/)
- Just learn some basics? **Keep reading.**
