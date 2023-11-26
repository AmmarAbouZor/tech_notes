## Change Repo from HTTP to SSH
Changing can be done with the command `set-url` on the wanted remote 
Here is the work through:
1. At first you can view the current remotes with the command:
```bash
git remote -v
```

2. Set the new URL using the command `set-url`
```bash
git remote set-url origin [SSH-URL]
```

3. Check the new remote URL again 
```bash
git remote -v
```

