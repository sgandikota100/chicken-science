---
{"dg-publish":true,"permalink":"/unix/"}
---

*Basic commands you should know!* 

## Shortcuts  
- `C` = `CTRL` 
- `M` = `META` (usually `ALT`, `OPT`, or `ESC` )

| command | Description            |
| ------- | ---------------------- |
| C-d     | delete next char       |
| C-k     | delete rest of line    |
| C-a     | go to start of line    |
| C-e     | go to end of line      |
| C-b     | move backwards 1 char  |
| C-f     | move forward 1 char    |
| M-f     | move forward 1 word    |
| M-b     | move backward one word |
| C-v     | move up 1 page         |
| M-v     | move down 1 page                       |

## Directory Management 
- All your directories are organized under a topmost directory called `\` which represents the root folder

| command | Description                                  |
| ------- | -------------------------------------------- |
| `cd`    | change directory; use cd - to revert to former directory; cd to go home                           |
| `pwd`   | print working directory; cd .. or `../..` to go back                    |
| `ln`    | make links + symlinks to files / directories |
| `mkdir` | make new directory; `-p` enables a passive option force mkdir                           |
| `rmdir` | remove directory                                              |

### Absolute v. Relative Paths 
You can use both of the following with the `cd` command: 
- Absolute paths have a fixed starting point, your home directory: `~/a/b/dest`
- Relative paths start in some directory: `/a/b/dest`
## File Operations 
Notes: 
- `.` files refer to path alias for the directory while `..` refers to path alias for parent of the directory

| command    | Description                                |
| ---------- | ------------------------------------------ |
| `ls`       | list files / directories                   |
| `tree`     | displays directory visually                |
| `cp`       | copy files; -r to copy whole directory                               |
| `rm`       | remove files / directories; -r to rm whole directory∫                 |
| `mv SOURCE DEST` or `mv SOURCE... DIRECTORY`       |  rename or move files / directoies          |
| `chmod`    | change file / directory access permissions |
| `chown`    | change file / directory ownership          |
| `realpath` | displays absolute path given relative one                                           |

### Flags for ls 
- `-l` = long output; shows mode (- for files, d for directories followed by Read, Write, or eXecute), 2?, user, group, size (byte count), timestamp, and name
- `-lh` = long output, human readable
- `-a` = show ALL files, including hidden ones (`.filename`)
- `.` lists files of current working directory's parent 
## Process Managment 
| command | Description                |
| ------- | -------------------------- |
| `ps`    | list processes             |
| `top`   | show tasks + system status |
| `kill`  | kill a process             | 

## Shell Commands 
| command | Description|
| ------- | -----------|
| `clear`   |clear screen|
| `history` | hx         |

## Text File Operations 
| command | Description                       |
| ------- | --------------------------------- |
| `cat`   | concatenate files & show contents |
| `more file1`  | shows part of file                                   |
| `less file1`  | shows less of file; press q to quit                                |
| `head`  | shows first 10 lines              |
| `tail`  | shows last 10 lines               |
| `grep`  | search for patterns in txt files                                  |

## vi commands 
to use vi, type `vi` file1 to edit; don't forget to hit esc to change between views 

| Command    | Description                                                       |
| ---------- | ----------------------------------------------------------------- |
| :w         | save file                                                         |
| :q         | quit file (also use :wq to save + quit)                           |
| :q!        | quit w/o saving                                                   |
| j, k, h, l | down, up, left, right (also use arrow)                            |
| 0          | move cursor to start of current line                              |
| $          | move cursor to end of current line                                |
| u          | undo                                                              |
| i          | insert text before cursor                                         |
| a          | append text after cursor                                          |
| o          | open and put text in new line below current line (caps for above) |
| r          | replace single char under cursor                                  |
| x          | delte single char under cursor                                    |
| dd         | delete entire current line                                                                  |

## Input | Output 

| Command                   | Description                       |
| ------------------------- | --------------------------------- |
| `command > file`          | redirect standard output to file  |
| `command >> file`         | append standard output to file    |
| `command < file`          | redirect standard input from file |
| `command1 \| command2`     | pipe output of 1 to input of 2    |
| `cat file1 file2 > file0` | concatinate 1 & 2 to 0            |
| `sort`                    | sort data                         |
| `who`                     | list users currently logged in    | 

## Javadoc commands 
| Command | Description                             |
| ------- | --------------------------------------- |
| javadoc | parses Javadoc comments into HTML files |
|         |                                         |
