## Tools

- [wasm-tools](https://github.com/bytecodealliance/wasm-tools): Provide tools to print `*.wasm` files in `*.wat` format and validate them.
- [cargo-wasi](https://github.com/bytecodealliance/cargo-wasi): Build and test to target `wasm32-wasi` directly.
- [wasm-pack](https://github.com/rustwasm/wasm-pack): Build for web-assembly that is intended to be working with JavaScript.

## Libraries:

- [wit-bindgen](https://github.com/bytecodealliance/wit-bindgen): A language binding generator for WebAssembly interface types

## WASM Component Model 

- Resources are data that can't be copied and is passed around by handle.
  They can have constructors and methods too. 
- Resources arguments can be defined is `borrowed` which means that the resources are passed by reference. Otherwise the passed arguments will be destroyed when the function gets out of scope 

