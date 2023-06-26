## No Slide at ends

### Go to previous

for that it's always good to use the method `saturating_sub()` which will check if the value is negative then return zero

### clamp
this method keeps the index in a certain range without sliding
```rust
let selection = selection.clamp(min, max)
```
