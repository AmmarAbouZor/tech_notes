## Updating the packages:

1. To update the packages we need to update the list of the available packages and channels with:
```bash
nix-channel --update
```

2. After that we can update the installed packages with:
```bash
nix-env -u
```
Note: updating the package list is useful before installing new packages too.

## Add NIX To Path

Adding nix path to env `PATH` should happen while installation of nix, but sometimes this doesn't work and we need to add nix path manually.
The best way to do that is by adding it to the file `~/.profile`

```bash
# Check if nix is not already in PATH
if [[ ":$PATH:" != *":/home/{your_profiel_name}/.nix-profile/bin:"* ]]; then
	export PATH="/home/{your_profiel_name}/.nix-profile/bin:$PATH"
fi
```

## Add `*.desktop` Files

Adding `*.desktop` files should be done with the installation of nix but sometimes this doesn't work either, and it must be added manually.
The best way to do that is by adding it to the file `~/.profile`

```bash
# desktop files
export XDG_DATA_DIRS="/home/{your_profile_name}/.nix-profile/share:$XDG_DATA_DIRS"
```

## Fix UTF-8 Error 

Currently we encounter an error about UTF-8 and that the terminal is rolling back to `ansi` . To solve this problem add the following line to the file `~/.profile`

```bash
# UTF-8 support
export LOCALE_ARCHIVE=/usr/lib/locale/locale-archive
```

## Run OpenGL GUI Apps

The apps which use hardware acceleration like `Alacritty, Kitty...` needs to get to the GL drivers in the system which isn't possible automatically if nix isn't running inside nix-OS. 
To solve this issue we need to install the nix package `nixGL` and then we must run the applications as an argument for `nixGL`. For example `nixGL Alacritty ...`
This fix should be added manually to all `*.desktop` files for those apps to the `EXE=` part of them.  

## Add Terminfo to Fish 

When Fish is installed with nix it needs to has access to the `terminfo` files, since it doesn't know about `usr/share/terminfo` directory.
To solve this problem you can link the terminal info folder

```bash 
ln -s /usr/share/terminfo/ ~/.terminfo
```

## Install from unstable channel

After enabling the unstable channel you can use the following pattern to install form the unstable channel:

```bash
nix-env -f channel:nixpkgs-unstable -iA vim
```
