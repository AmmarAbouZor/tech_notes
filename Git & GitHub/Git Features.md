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

## Identify where a bug happend with `git bisect`

This command do an interactive binary search in commits history and it will jumps between the commits
- We start by setting the bad commit (usually HEAD) and the good commit (A commit without the bug)
- After that it will jump to a commit in the middle and we can test the bug and report if the commit good or bad
- This can be repeated until we find the commit where the bug has been introduced
- This can be done in a very simple way with `LazyGit`
- Here is the version of doing that from the command line:

```bash
git bisect start
git bisect bad          # Mark the current commit as bad
git bisect good <good_commit_hash>  # Mark a known good commit

# Git will now checkout a commit in between
# Test the code, then mark it as good or bad
git bisect good         # or git bisect bad

# Repeat the test and marking until the bad commit is found
# Once done, reset bisect
git bisect reset
```
