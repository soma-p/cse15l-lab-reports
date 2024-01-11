# Lab Report 1 - Remote Access and FileSystem
---
## Example 1:
```
#code block
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$

[user@sahara ~/lecture1]$ cd
[user@sahara ~]$

[user@sahara ~]$ cd
[user@sahara ~]$ 
```
The working directories when the program was run were "/home", "/home/lecture1", and "/home/lecture1/messages". "cd" is the command that is supposed to take you into or out of a directory.
Having no other arguments means you're trying to go to the base directory, which explains the output, showing that the working directory after executing the command is always "/home".

I don't think the output (or the execution of the command) was an error because the cd command is intended to change the working path. I think it makes sense that the working path changes to the home path when no additional arguments are given
because the user doesn't specify which directory they want to go into.

---

## Example 2:
```
#code block
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$

[user@sahara ~/lecture1]$ cd messages
[user@sahara ~/lecture1/messages]$

[user@sahara ~]$ cd lecture1/messages
[user@sahara ~/lecture1/messages]$ 
```
