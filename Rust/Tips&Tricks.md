## Hide Warnings While Prototyping

It's helpful sometimes to hide the warning while prototyping a big feature. This is possible right now using a flag on the crate level. This flag should be set on the `main.rs` or `lib.rs` file

```rust
// The bang `!` applies it to all children of the module

#![allow(dead_code, unused_imports, unused)]
```
