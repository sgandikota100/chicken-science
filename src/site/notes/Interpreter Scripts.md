---
{"dg-publish":true,"permalink":"/interpreter-scripts/"}
---

A plain ole' text file that contains a sequence of commands that's executed by an interpreter program. This allows you to run numerous files (or perform a sequence of operations) with the input of a file. Really nice for large projects! 
# a bash script  
To start writing a shell script (we're going to write a bash script here), you need to open a terminal window (on a Linux or MacOS system open "Terminal"). Remember, you'll be presented with a command prompt where you can enter commands directly into the shell. Next open a text editor (such as `nano`, `vim`, `emacs`, `gedit`, or even `VSCode`). 

We're going to use `vim` here; open a new file by typing `vim hello_farm.sh`. Press the `i` key (meaning insert) to start typing. There's a few key points you'll need for your script to work.  Begin your script with `#!/bin/bash` (called the shebang). The shebang specifies the interpreter for the script to be run on, which in this case, `/bin/bash` is the path to the Bash shell in Unix-based systems. Now it's time to add some commands to your script. Let's start with the echo command, which is used to output text or a variable value to the console. We'll use it to print `Hello, Farm!` to the terminal. The script is complete! It's a simple one, just printing a single line of text, but it's a good start. 

What if we want to see what command is executed? Or stop the script so when it fails? We can add optional arguments after the shebang (on the same line tho) that specifies what we want. For the two cases above, we can ass `-x` and `-e` respectfully. We also can add them to the first line rather than the shebang as `set -x` and `set -e` respectfully: 

```bash 
#!/bin/bash -ex
echo "Hello, Farm!"
```

Before you get too excited, you need to make it executable (so it can be run by the system). Use the `chmod -x` command in the terminal, which changes the file permissions (the `+x` option adds the "execute" permission to the file!). Now, to run the script, type `./hello_farm.sh ` (`./` specifies that the file is in the *current directory*). Press enter and bam! Because our script contains a single command to print "Hello, Farm!", that's exactly what it will do. 

**A recap:** 
1. Execute permission enabled 
2. First line is the *shebang*: `#! interpreter [optional-arg]`
	1. `-x` (on optional-arg) OR `set -x` (as first command) displays the commands that it executes
	2. `-e` (on optional-arg) OR `set -e` (as first command) stop executing the commands if a command terminates with an error 
	3. can combine commands like in UNIX 

