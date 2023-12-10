# Documentation

- `README.md` files are used often.

- Most of the "books" are being generated from
  [mdbook](https://github.com/rust-lang/mdBook), which is useful
  for "humane documentation" around APIs or features, and even more useful once your README becomes too long. It's generally
  "just markdown files as input."
  - This guide started as a README, and became an `mdbook`.
  - Pretty much by just doing an `mdbook init` and moving over sections in the README.

- APIs are documented via `rustdoc`, and it comes out of the box in Rust.
  You will find your normal code comments generally land where you'd expect
  them to in, but you can learn how to make it really nice by... You guessed
  it, reading the `rustdoc` book, [which is here](https://doc.rust-lang.org/rustdoc/what-is-rustdoc.html).
  - [docs.rs](https://docs.rs/) is the index of docs generated from everything published to [crates.io](https://crates.io/).
