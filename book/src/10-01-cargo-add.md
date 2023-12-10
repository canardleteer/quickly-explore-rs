# Add a crate

First, let's add the extremely useful `clap` library to our `Cargo.toml`. Start by checking out the [crate page](https://crates.io/crates/clap).

I am pinning the version, to `4.4.11`, and adding 2 Features: `derive` and `env`.

- "Features" for crates are important to know about, but I'm not going to cover them here. You can [read up on them](https://doc.rust-lang.org/cargo/reference/features.html).

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

- Hopefully that worked for you like it did for me. If not, when you figure it
out, please submit a PR to this repository :)
