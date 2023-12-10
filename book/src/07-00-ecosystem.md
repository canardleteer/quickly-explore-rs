# Ecosystem Exploration

The root level place folks head to for the Rust Ecosystem is:

- [crates.io](https://crates.io/)
  - Publishing crates to `crates.io` is a well understood topic.
  - It gets much more complex when dealing with private/internal crate repositories.
- You will add things here to your `Cargo.toml` file under `[dependencies]`
- Documentation, will be published to [docs.rs](https://docs.rs/)
- **crates** in general are versioned and compiled libraries/executables,
  built from a **package** repository.
  - It's usually okay to interchange the term "crate" and "package," but they do
    have specific meaning in some contexts.
  - Once published to a public place like `crates.io`, a crate can be redacted,
    but are otherwise immutable.

`cargo` itself, has it's own ecosystem of tools, like:

- [cargo-generate](https://github.com/cargo-generate/cargo-generate) - Templates for Cargo
- [cargo-llvm-cov](https://github.com/taiki-e/cargo-llvm-cov) - Code Coverage (I end up using 2 different code coverage tools)
- [cargo-audit](https://github.com/RustSec/rustsec/tree/main/cargo-audit) - Rust specific vulnerability scanner
- ... plus a whole lot more...
