## List all Environment Variables
There are different commands for that

```bash
# env is the common one
env
env | bat

# declare shows the built-in functions as well
declare
declare | bat
```

## Get Info about a command
There are different commands for that too

```bash
# Which is strait forward
which nvim;
which ls;

# type gives more info
type nvim;
type -a la; 
```

## Set Global Environment Variables
The file `~/bash_profile` will be executed when the users log in. 
Therefore it would be useful to set the global variables here to share them among other shells