# Use the new crate

Now we need to so something useful with this added crate.

Change `src/main.rs` to be this:

```rust,ignore
// Import the Parser trait.
use clap::Parser;

// Declare our CLI arguments.
#[derive(Parser, Debug)]
#[command(author, version, about, long_about = None)]
struct Args {
    /// Name of the person to greet
    #[arg(short, long, env = "HELLO_WORLD_NAME", default_value="Rust Learning Person")]
    name: String
}

// Say the line, robot.
fn main() {
    let args = Args::parse();

    let name = args.name.clone();
    println!("Hello, {}!", args.name);
}
```
