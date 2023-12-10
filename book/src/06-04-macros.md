# Macros

The macro sytax in Rust is both extremely powerful and useful, but can appear
to be a bit arcane and "meta." They are not like `C/C++` macros. It will be
awhile before you understand why and where to use macros, and that's before you
understand how to. All that is okay.

You will use them all the time. If you see stuff like this in code:

- `#[derive(Something)]`
- `println!("something")`

Or even more broadly, if you see a:

- `!`
- `#`

...you are probably using a macro.

Like all Rust things, [there is a book you can read to learn more](https://veykril.github.io/tlborm/).
