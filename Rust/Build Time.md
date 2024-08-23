
## Important Blog

Here is a [great blog](https://fasterthanli.me/articles/why-is-my-rust-build-so-slow) form **Faster than Lime** about build time.
It has a lot of information about the mentioned tools below as well.

## Time Report with `--timings`

We can use the flag `--timings` on cargo build, which will generate a html file with useful information about how long each compilation takes, and tracks concurrency information over time.

```rust
cargo build --timings
```

By the end of the run, cargo will print out the path to the generated html file.

### [cargo-bloat](https://github.com/RazrFalcon/cargo-bloat)

CLI tool to find out what takes most of the space in executables.
For usage and installation check the GitHub.

This tool can be used to understand what code ends up inside the binary executables. It's useful for optimizing build time as well.

## [cargo-llvm-lines](https://github.com/dtolnay/cargo-llvm-lines)

This tool measures the number and size of instantiations of each generic function in a program, indicating which parts of your code offer the highest leverage in improving compilation metrics.

Generic functions in Rust can be instantiated multiple times, so they can disproportionately affect compile time, compiler memory usage, and the size of compiled executables.

More infos on the GitHub repo.


