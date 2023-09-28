#rust
To analyse the dependencies there are the following tools:

### [cargo-udeps](https://github.com/est31/cargo-udeps)
Find unused dependencies in Cargo.toml.
#### Install:

```bash
cargo install cargo-udeps --locked
```
#### Usage:

```bash
cargo +nightly udeps
```

If you need to install rust nightly:

```bash
rustup toolchain install nightly
```

### [cargo-bloat](https://github.com/RazrFalcon/cargo-bloat)
Find out what takes most of the space in your executable.
For usage and installation check the GitHub