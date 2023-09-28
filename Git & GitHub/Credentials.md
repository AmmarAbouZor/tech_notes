#GitHub
## Setup GitHub credentials for the first time

1. Show the configs
```bash
git config --list --show-origin 
```

2. Set username and password 
```bash
printf "protocol=https\nhost=github.com\n" | git credential fill 
```

3. Pass the credentials to the credential-store
```bash
printf "protocol=https\nhost=github.com\n" | git credential-store get 
```
This should give the credential back

## Use credentials-store with GitHub Repos

run this in each repo the first time you want to push something:
```bash
git config credential.helper store
```
