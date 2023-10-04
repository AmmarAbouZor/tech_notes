## Use Aliasing Instead of wildcard

This will create an undefined behavior of you remove one of them since the removed one will be the variable name

```rust
use VeryLongEnumName::*;
match val {
	VarA => {},
	VarB => {},
	VarC => {},
}
```

the safe way in this situation is to use aliasing:

```rust
use VeryLongEnumName as E;
match val {
	E::VarA => {},
	E::VarB => {},
	E::VarC => {},
}
```