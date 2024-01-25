## Create Group & Add users to it
To create a group or check if a group already exists use:
```bash
sudo groupadd $GROUP_NAME
```
To add users to the group:
```bash
sudo usermod -aG $GROUP $USER
```
After that you need to log out or restart your computer to make sure it's working

## Check the users of each group
The groups are saved in the file `/etc/group` but sudo privileges are needed for that
```bash
sudo cat /etc/group | grep "..."
```

## Activate su session
On many distributions `su` command isn't allowed so it wont work even with sudo password. To activate this we need to call it from sudo of call the sudo interactive mode command
```bash
sudo su - # Or
sudo -i
```