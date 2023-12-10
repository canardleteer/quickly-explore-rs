# Sparse Indexing

`cargo` is changing it's indexing protocol, so I recommend performing whatever
action makes sense for you, to use the HTTP indexing by default, and spare
yourself much build slowness, by [going here for instructions](https://blog.rust-lang.org/inside-rust/2023/01/30/cargo-sparse-protocol.html).

This will probably eventually become a default, if it isn't already.
