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