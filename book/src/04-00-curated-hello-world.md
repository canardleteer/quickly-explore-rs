# Welcome to your Curated Hello World Experience

- Open up `src/main.rs`.

Cool, it's there. You're welcome to make changes if you wish to personalize your Hello World experience.

- Run it.

```shell
cargo run
```

Alternatively:

```shell
cargo run --bin quickly-explore-rs
```

I really don't like using `cargo` to run stuff, since it implies that you "need cargo to run what you built"
(you don't) but you will find it handy if you setup multiple binaries in a repository.

So you can run the binary without `cargo` directly:

```shell
cargo build
./target/debug/quickly-explore-rs
```

- Build a Release Version

You may hate the incredibly slow runtime performance of this Hello
World experience (sarcasm), we can speed that up:

```shell
cargo build --release
./target/release/quickly-explore-rs
```

Now we're cookin' with gas! **Ship it!**
