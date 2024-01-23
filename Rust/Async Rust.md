## Run many tasks asynchronously
Running the tasks with a normal loop with `tokio::spawn()` inside a list to await leads to much memory consumption since many tasks could be spawned while the other ones are still running. For that situation You can use `futures_util::stream`. Here is an example:
```rust
use futures_util::{StreamExt, stream}; 

#[tokio::main] 
async fn main() { 
	let client = reqwest::ClientBuilder::new()...;

	stream::iter(0..1_000_000)
	.for_each_concurrent(10, |url| callback(&client, url))
	.await;
}
```

Another solution is using  `tokio::task::JoinSet`