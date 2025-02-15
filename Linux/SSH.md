## Add Private Key Permanently

***Note**: Maybe it works automatically in the current version of Linux*

In the file ~/.ssh/config add the keys for the simple cases
```bash
IdentityFile ~/.ssh/gitHubKey
```

Additionally if you want to set the key specific to one host, you can do the following in your ~/.ssh/config :

```bash
Host github.com
    User git
    IdentityFile ~/.ssh/githubKey
```

This has the advantage when you have many identities that a server doesn't reject you because you tried the wrong identities first. Only the specific identity will be tried

**Important:** The config file must have chmod of 600: 
User can read and write and Everything else is deactivated 
-rw-------
```bash
chmod 600 ~/.ssh/config
```

If you set a pass phrase you need to enter it with the first action on each session

## Add passphrase to ssh-agent

* At first you need to ensure that `ssh-agent` is started when the session is started.
* Add private key using `ssh-add`:
  ```sh
  $ ssh-add ~/.ssh/id_rsa_key  
  Enter passphrase for /home/user/.ssh/id_rsa_key:  
  Identity added: /home/user/.ssh/id_rsa_key   
  ```
* Check if the key is added using `ssh-add -l`

