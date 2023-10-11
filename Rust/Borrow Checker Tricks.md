## Split_at_mut()

This gives two slices from one slice enabling us to have two mutable references to the given slice. So we can for example change one part of the slice depending on the other part (Watch quick sort in Jon Sorting video on YouTube for more info) 


## Iterate through an Iterate more than once

Iterating through in iterator consumes it which make the following code impossible

```rust
let mut iterator = input.lines();
let _: Vec<_> = iterator.take(5).collect();
# The following can't be done because iterator was consumed in the previous line
let __ = iterator.next(); 
```

The Solution for that is with using the method `by_ref()` on the iterator

```rust

let mut iterator_ref = iterator.by_ref();
```
