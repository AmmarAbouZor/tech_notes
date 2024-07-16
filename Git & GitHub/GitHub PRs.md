## Checkout PR on your Fork Locally

The following commands are to check a PR locally on your machine form a fork of the main repository where this PR exist

1. Fetch the PR and give it a name
```bash
git fetch {remote_name} pull/{PR_Number}/head:{Custom_Name}
git fetch upstream pull/{PR_Number}/head:{Custom_Name}
git fetch origin pull/{PR_Number}/head:{Custom_Name}
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

### Quick way to check PR

It's possible in git to pull the changes from a pr directly. With this we can create a branch locally and pull the changes from the PR, or we can even pull the changes directly to our current branch and reset it later

```bash
git pull upstream pull/{PR_Number}/head # This would work on any branch even on the master

# To reset the branch we can use 
git reset --hard origin/master # or upstream/master
```
