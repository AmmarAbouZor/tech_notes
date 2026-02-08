## Fork and create branch

After forking and cloning the repo locally the following commands are needed:

```bash
git remote add upstream <upstream_clone_url>
```

Then to verify that use: 

```bash
git remote -v
```

Then create a normal branch in the clone

the first push on the branch should include the tracking. To achieve that use

```bash
# This pushes you current local branch only (recommended)
git push -u

# This will push all your local branches (Not recommended in normal workflow)
git push --all -u
```

## Sync Upstream with fork

To achieve that use the following:
1. At first checkout the master in the fork if needed

```bash
git checkout master
```

2. Use one of the following:
- Merge (didn't work): This should work because it will make fast forward only because the master should be clean always
	In the output we should see Fast-Forward if this is working fine

```bash
git merge upstream/main
```
   
- Rebase: This should work too but I found this on a 8 years old youtube video
 
```bash
git pull --rebase upstream master
```

3. After that move to your branch and rebase or merge your master and deal with conflicts if needed.
```base
git rebase master
```

After that we need to force push

```bash
git push --force
```

## Get Branch from Another Fork
In case you have a fork of a repo and you want a branch from another fork from that repo then here are the steps:
1. **Add a Remote for the Other Fork:** 
	 You can add many remotes to your local repo. Adding a new remote can be done with the command
```bash
git remote add [give_name_here] [link_to_fork] 
```

 2. **Fetch Branches from Other Fork**
```bash
git fetch [given_name_for_remote] 
```

3. **Create Branch Based on Target Branch**
```bash
git checkout -b [new_branch_name] [given_name_remote]/[target_branch]
```
I think I can here checkout the target branch directly if I don't want to have any changes there.
