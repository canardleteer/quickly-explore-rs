# Install Some Useful Tools

- `cargo install ripgrep`
  - [repo](https://github.com/BurntSushi/ripgrep)
- `cargo install mdbook`
  - [repo](https://github.com/rust-lang/mdBook)

## Use `rg` after install

```shell
rg "# Install Some Useful Tools" .
```

And it should find the Markdown source for this chapter.

## Use `mdbook` after install

To locally view this book:

```shell
mdbook serve book
```

And it would then be serving at:

- [http://127.0.0.1:3000](http://127.0.0.1:3000)