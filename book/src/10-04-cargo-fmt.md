# Format the changed code

- Let's check to see if that's good Rust, with `cargo fmt --check`:

```text
-> cargo fmt --check
Diff in /home/canardleteer/dev/quickly-explore-rs/src/main.rs at line 6:
 #[command(author, version, about, long_about = None)]
 struct Args {
     /// Name of the person to greet
-    #[arg(short, long, env = "HELLO_WORLD_NAME", default_value="Rust Learning Person")]
-    name: String
+    #[arg(
+        short,
+        long,
+        env = "HELLO_WORLD_NAME",
+        default_value = "Rust Learning Person"
+    )]
+    name: String,
 }
 
 // Say the line, robot.
```

- Looks like we didn't quite do that too legibly, but let's let the formatter do the work for us, with `cargo fmt`.

```text
# Clean it up for us.
-> cargo fmt

# Verify it cleaned it up for us.
-> cargo fmt --check
-> 
```

Looking tidy!
