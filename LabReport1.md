# Lab Report 1 - Remote Access and FileSystem
---
## Example 1:
```
#code block
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```
When the program was run, the working directory was "/home/lecture1". "cd" is the command that is supposed to take you into or out of a directory.
Having no other arguments means you're trying to go to the base directory, which explains the output, showing that the working directory after executing the command is always "/home".

The output (or the execution of the command) was not an error because the cd command is intended to change the working path. I think it makes sense that the working path changes to the home path when no additional arguments are given
because the user doesn't specify which directory they want to go into.

---

## Example 2:
```
#code block
[user@sahara ~/lecture1]$ cd messages
[user@sahara ~/lecture1/messages]$
```
The working directory when the program was run was "/home/lecture1". "cd" is the command supposed to change your working directory, so it makes
sense that whenever the relative path to another directory is entered as an argument, your working directory changes to that path.

The output was not an error because the cd command acted as intended.

---

## Example 3"
```
#code block
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$ 
```
The working directory when the program was run was "/home/lecture1". "cd" is the command supposed to change your working directory, so it makes
sense that an error message would be displayed if you're trying to cd into a file.

The output was an error because the cd command stated that Hello.java was not a directory and ended up not doing anything. Furthermore, whenever
the terminal says "bash:" followed by a message indicating an error!

---

