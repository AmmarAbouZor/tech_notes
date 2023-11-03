## Checkout PR on your Fork Locally

The following commands are to check a PR locally on your machine form a fork of the main repository where this PR exist

1. Fetch the PR and give it a name
```bash
git fetch upstream pull/{PR_Number}/head:{Custom_Name}
```
2. Checkout the PR using the custom name
```bash
git checkout {Custom_Name}
```

### Pull changes to the PR
To pull the changes you need to specify the pr again. The given name won't work

```bash
git pull upstream pull/{PR_Number}/head
```