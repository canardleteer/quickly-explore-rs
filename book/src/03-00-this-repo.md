# This Repository

I made this repository with:

```shell
cargo new quickly-explore-rs
```

It made a few files:

- `Cargo.toml`
  - Which defines your package's dependencies and a few other things.
- `.gitignore`
  - Which ignores the `target` directory, which is your build output.
- `src/main.rs`
  - Which is the source code for this application.

Files that may get generated for you as you poke around:

- `target/*`
  - Your build directory.
- `Cargo.lock`
  - Dependency reification lock file - [documentation](https://doc.rust-lang.org/cargo/guide/cargo-toml-vs-cargo-lock.html)
  - If you're authoring an application, yes you commit it to your source tree. If you're authoring a library, no, you don't commit it.
  - **Even though this repository is an application, we are not commiting it, so it remains closer to "as generated."**

`cargo` won't make the following files present in this repository:

- `README.md`
- `book/`
- `rust-toolchain.toml`
- `.github/`

Those have been added after the initial buildout, for documentation, publishing & pinning purposes.
