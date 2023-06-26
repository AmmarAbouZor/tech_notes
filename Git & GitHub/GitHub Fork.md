## Fork and create branche

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
