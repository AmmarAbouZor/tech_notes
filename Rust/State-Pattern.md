
It's best to handle the state pattern with compiler checks. This example demonstrate how to do it the best way 

```rust
use std::marker::PhantomData;

struct Grounded;
struct Launched;

struct Rocket<Stage = Grounded> {
    stage: PhantomData<Stage>,
}

// Start with grounded only
impl Default for Rocket<Grounded> {
    fn default() -> Self {
        Rocket { stage: PhantomData }
    }
}

// Grounded only can launch
impl Rocket<Grounded> {
    fn launch(self) -> Rocket<Launched> {
	   Rocket { stage: PhantomData }
	}
}

// Methods for Launched only
impl Rocket<Launched> {
    fn accelerate(&mut self) {}
    fn decelerate(&mut self) {}
}

// General methods
impl<Stage> Rocket<Stage> {
    pub fn color(&self) -> Color {}
    pub fn weight(&self) -> Kilogram {}
}

fn main() {
    let rocket = Rocket::default();
    rocket.weight();
    let mut rocket = rocket.launch();
    rocket.decelerate();
    rocket.color();
}
```