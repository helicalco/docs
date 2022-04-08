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

Lists the contents of the current directory.

```sh
$ ls
```

Running ls with -s flag will list files or directories with their sizes (in kilobytes).

```sh
$ ls -s
```

### cat

Concatenate reads the contents of a file and prints it to the terminal.

```sh
$ cat [file]
```

### column

Column is super helpful when dealing with csv or any table formated files.

```sh
$ column -t [file]
```

The `-s` defines the column delimiter.

When dealing with CSV files, make sure to provide the `-n` flag too which prevents adjacent delimiters being merged.

```sh
$ column -t -n -s ',' [file]
```

For example, you could have a `genotype_report.txt` file that looks likes this:

```
ID CallRate #AA #AB #BB #NC %AA %AB %BB %NC
27813162 0.185837 141 192 142 2081 0.06 0.08 0.06 0.81
30282025 0.185837 115 240 120 2081 0.04 0.09 0.05 0.81
21928702 0.996870 596 951 1001 8 0.23 0.37 0.39 0.00
27942765 0.241393 142 292 183 1939 0.06 0.11 0.07 0.76
```

Which is a little hard to track columns. Using:

```sh
$ column -t genotype_report.txt
```

We get:

```
ID        CallRate  #AA  #AB  #BB   #NC   %AA   %AB   %BB   %NC
27813162  0.185837  141  192  142   2081  0.06  0.08  0.06  0.81
30282025  0.185837  115  240  120   2081  0.04  0.09  0.05  0.81
21928702  0.996870  596  951  1001  8     0.23  0.37  0.39  0.00
27942765  0.241393  142  292  183   1939  0.06  0.11  0.07  0.76
```

### find

Finds files and directories.

```sh
$ find [directory to search from] [expression what to find] [what to find]
$ find Documents -name "*.md"
```

Above command will find all files with the extension `.md` in the `Documents` directory.

### grep

Finds all occurences of text in a file.

```sh
$ grep [string/pattern] [files]
```

This will search for and return any lines of text that contain the pattern in given files.

Helpful flags:

- `-i`: Case insensitive search.
- `-c`: Count the number of matches.
- `-n`: Print the line number of each match.

### |

Pipe allows you to run multiple commands in a single command. It pipes the standard output of one command into the standard input of the next command.

```sh
$ cat pedigree.txt | column -t
```

The above example would print the file out and pipe the contents into `column`, which would then format the file.

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

Creates a new directory.

```sh
$ mkdir [my-directory]
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
