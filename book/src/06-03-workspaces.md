# Cargo Workspaces

It's worth knowing about Rust Workspaces, and you can
[learn about them here](https://doc.rust-lang.org/book/ch14-03-cargo-workspaces.html).

- If you find yourself wanting to work on more "packages," but remain in a
  single repository, this is generally what you want.
- These are things that generally "all change together at once."
- These can be very useful while gradually separating isolated components,
  without forcing it all to happen at once.
