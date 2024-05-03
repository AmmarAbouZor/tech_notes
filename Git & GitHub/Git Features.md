## Clone Sub Directory Only Using "Sparse Checkout"

To clone a sub directory or a group of sub directories you can use the `Sparse Checkout` feature from git. Here is how to use it:

1. Clone Git with no-checkout `-n` with the filter to clone git tree only:
```bash
git clone -n --depth=1 --filter=tree:0 {repo-url}
cd {repo-name}
```

2. Set the directories names that you want to include:
```bash
git sparse-checkout set --no-cone {dir_1} {dir_2}
## For Example
git sparse-checkout set --no-cone example
```

3. Check out:
```bash
git checkout
```