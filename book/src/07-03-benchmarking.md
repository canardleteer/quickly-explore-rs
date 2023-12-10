# Benchmarking

- I don't think Rust has "full support" for benchmarks without additional crates (yet).
- Benchmark tests (via the `#[bench]` macro) are a thing in Nightly Rust, these are good for simple things.
- I use [criterion.rs](https://github.com/bheisler/criterion.rs) for non-trivial benchmarking.
- But there is more available, and you can learn about all of this from the [Rust Performance Book](https://nnethercote.github.io/perf-book/benchmarking.html).
