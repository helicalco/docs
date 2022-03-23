---
title: Using Linux
pcx-content-type: tutorial
weight: 1
meta:
  title: Using Linux
---

# Using Linux

## Useful Linux Commands

### cd

Allows you to change the current working directory.

```sh
$ cd /path/to/directory
```

### . & ..

`.` is the current directory. `..` is the parent directory.
For example, if you are in the directory `/home/user/Documents/my-project`, then `.` is `/home/user/Desktop/my-project` and `..` is `/home/user/Documents`. So to move backwards in the directory tree, you can use `cd ..`.

### ~

`~` is the home directory (`/home/user` by default).

### \*

Wildcard matches all files.

### ls

Lists the contents of the specified directory.

```sh
$ ls [directory]
```

Can also just run `ls` alone and it will list the current directory.
Running ls with -s flag will list files or directories with their sizes (in kilobytes).

```sh
$ ls -s [directory]
```

### cat

Concatenate reads the contents of a file and prints it to the standard output.

```sh
$ cat [file]
```

### column

Column is super helpful when dealing with csv or any table formated files.

```sh
$ column [file]
```

Not much will happen differently from cat when using column with no flags. Two important flags are `-t` and `-s`. `-t` is used to create a table by determining the number of columns. `-s` defines the column delimiter. Using these together will format the output in a table.

```sh
$ column [file] -t -s ','
```

### echo

Echo is used to print text to the standard output.

```sh
$ echo [string]
```

### find

Finds files and directories.

```sh
$ find [directory to search from] [expression what to find] [what to find]
$ find Documents -name "*.md"
```

Above command will find all files with the extension `.md` in the `Documents` directory.

### grep

Stands for - Globally search for a Regular Expression and Print it out.
Preforms text searchs for a defined pattern.

```sh
$ grep [string/pattern] [files]
```

This will search for and return any lines of text that contain the pattern in given files.

Helpful flags:

- `-i`: Case insensitive search.
- `-c`: Count the number of matches.
- `-n`: Print the line number of each match.

### history

Outputs your recent commands with numbers to identify them.

```sh
$ history
```

You can run a command again by using `!` and the number of the command `!5`.

### |

Pipe allows you to run multiple commands in a single command. It pipes the standard output of one command into the standard input of the next command.

```sh
$ hisory | grep cd
```

The above command would list the history which would pipe into grep. Grep would then search for `cd` and output every command you've made with cd.

### head

Prints the first n lines of a file/input.

```sh
$ head [file]
```

Can specifiy number of lines using `-n` flag.

### man

Lookup manual for a given command.

```sh
$ man [command]
```

### mkdir

Creates directories.

```sh
$ mkdir [directories]
```

`-p` flag will create parent as necessary ie. can create 3 directories one inside the next.

```sh
$ mkdir -p dir1/dir2/dir3
```

### mv

Used to move files and directories. Can also rename files and directories.

```sh
# move files/directories to new destionation
$ mv [files/directories] [destination]
# rename file/directory
$ mv [file/directory] [new name]
```

### cp

Copy files and directories.

```sh
$ cp [files/directories] [destination]
```

### pwd

Print working directory will output the path of the current working directory.

```sh
$ pwd
```

### sudo

Sudo is used to temporaily gain/give administrative privileges. If any command is restricted, use sudo before the given command. It will then prompt for your password.

```sh
$ sudo [command]
```

### rm

Remove command removes files and directories.

```sh
# simple file remove
$ rm [path/to/file]
# remove directory
$ rm -r [path/to/directory]
# remove multiple files
$ rm [path/to/file1] [path/to/file2]
```

### wc

Count the number of lines, words, characters, and bytes in a file or input.

```sh
$ wc [options] [file]
```

For example:

```sh
$wc pedigree.txt
```

Will look something like this:

```
397 4222 22566 /pedigree.txt
```

- 397 is the number of lines.
- 4222 is the number of words.
- 22566 is the number of characters.

You can also pass in multiple files.

#### Important flags:

- -l, --lines - Print the number of lines.
- -w, --words - Print the number of words.
- -m, --chars - Print the number of characters.
- -c, --bytes - Print the number of bytes.

### awk

Awk is a language that can be used to manipulate text files. It is useful for transforming data files and producing formatted reports.

The syntax is:

```sh
$awk options 'selection criteria' [input-file] > [output-file]
```

For example, lets say you have this pedigree file:

```
9997515 5017534 7651593
9939593 5765357 6245551
9998766 5455357 7736346
9954672 5017534 6245551
9999762 5455357 6245551
```

To print out the file:

```sh
$ awk '{print}' pedigree.txt
```

If you wanted to see every line with a certain id, you could do this:

```sh
$ awk '{if ($1 == "9997515") print}' pedigree.txt
```

Outputs:

```
9997515 5017534 7651593
```

Imagine you wanted to find the id of an animal that had two certain parents. You could do this:

```sh
$ awk '{if($2 == "5017534" && $3 == "7651593") {print}}' pedigree.txt
```

Outputs:

```
9997515 5017534 7651593
```

If you only want to print certain columns, you can use the $0, $1, $2 ....
$0 means to print every column, then $1, $n, denotes each column from 1 to n.
For example:

```sh
$ awk '{print $1}' pedigree.txt
```

Outputs:

```
9997515
9939593
9998766
9954672
9999762
```
