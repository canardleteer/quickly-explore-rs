# Introduction

I wrote this as a quick guide for folks who are choosing to, or being asked to:

- Work with Rust repositories.
- Align development practices around Rust repositories.
- In some way incorporate Rust in their day to day development considerations.

There is no expectation that you "want" to do any of this, and it's not my goal
to make you want to.

The goal here, is to provide a quick tour of what exists in the Rust Ecosystem.
*I am not intending to teach people how to write Rust.* Where possible, I do
point to far better resources on that subject than I would be able to write.

The Rust ecosystem has been good to me, and I recommend you give it a shot.

- **For developers coming from C or C++**, you should **prepare to learn to trust
  your compiler warnings by default again** while learning Rust.
  - There will come a day when you know Rust better than the Rust compiler does,
    but it's probably not going to be Day 1.

- **For developers who don't naturally start with
  [Test-driven Development](https://en.wikipedia.org/wiki/Test-driven_development)**,
  I encourage you to prepare yourself to engage with the test system earlier,
  rather than later.
  - The testing framework is already setup for you, and extremely easy to use.
  - The benchmark tooling is very easy to access (and will soon be built in).
