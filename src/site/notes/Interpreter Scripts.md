---
{"dg-publish":true,"permalink":"/interpreter-scripts/"}
---

A plain ole text file that contains a sequence of commands that's executed by an interpreter program. This allows you to run numerous files (or perform a sequence of operations) with the input of a file. Really nice for large projects! 
# a basic script  
For a [[🌎 Unix\|🌎 Unix]] environment.... 
1. Execute permission enabled 
2. First line is the *shebang*: `#! interpreter [optional-arg]`
	1. `-x` (on optional-arg) OR `set -x` (as first command) displays the commands that it executes
	2. `-e` (on optional-arg) OR `set -e` (as first command) stop executing the commands if a command terminates with an error 
	3. can combine commands like in UNIX 

