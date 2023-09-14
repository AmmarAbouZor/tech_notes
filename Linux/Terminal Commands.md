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

## Run Command without aliasing
To run command without any built in aliasing add a forward slash to the start of it

```bash
ls # This would normally run 'ls --color=auto' on fedora
\ls # This will run the native ls command
```

## Set Global Environment Variables
The file `~/bash_profile` will be executed when the users log in. 
Therefore it would be useful to set the global variables here to share them among other shells

## Matching files 

```bash
ls *a* # This matches any num of any charachters ex: banana
ls ?a? # This matches the exact num of any charachters ex: ban
ls [ab]* # This matches the given characters in brackets ex: ape bed 
ls [a-g]* # This matches the range between a to g

touch {a,b}-{1,2} # a1, a2, b1, b2
touch {a..c}-{1..3} # a1, a2, a3, b1, b2, b3, c1, c2, c3
```

## Directing File Content:

- `>` this writes the standard output of the command to file
- `2>` this writes the err output of the command to file
- `&>` this writes both outputs of the command to file
- `>>` this appends the file with the output of the command
- `<` this redirect the content of a file to a command like `cat < somefile`

## Going to the previous Path in Bash

```bash
cd - # This change the directory to the previous one
echo $OLDPWD # This prints the previous directory
```

## Permissions chmod Command
### Using Numbers
`chmod` is the command to change the permissions of a file or a folder. The command followed by a number calculated like this: The number contains of three digits. First one for user, second for group and third for all users. 
Each digit can be  combined of (4 for read, 2 for write, 1 for execute). Examples:
```bash
chmod 777 # Gives all access to all gruops  -rwxrwxrwx
chmod 764 # Gives the following permissions -rwxrw-r--
chmod 640 # Gives the following permissions -rw-r-----
```

### Using Letters
`chmod` can be used with letters and +/- signs to indicate the permissions.
The command has the form `{range}{+/-}{r, w, x}`
the range can have the following: 
- u for user
- g for group
- o for others
- a for all users
```bash
chmod u+x # Make the file executable for the user only
chmod g-r # Make the file not editable for the gruop
```

## Find Command
#### Find with names
```bash
find [path] -name '*.rs' -ls # ls to list the files after that
``` 

#### Find by size
```bash
find [path] -size -1M -size +10M # Files between 1 and 10 Migabytes
```

#### Find with user or permissions
```bash
fidn [path] -user user_name
fidn [path] -perm 755
```

#### Find by date and time
the options are:
- Accessed: `atime` for days and `amin` for minutes
- Created: `ctime` for days and `cmin` for minutes
- Modified: `mtime` for days and `mmin` for minutes
```bash
find [path] -mmin -10 # Finds files that is modified in the last 10 mins
```

#### And, Or and NOT
You can combine multiple search options with:
- And `-and`
- Or `-o`
- Not `-not`
```bash
find [path] -mmin -10 -and -user -not [user-name]
```
