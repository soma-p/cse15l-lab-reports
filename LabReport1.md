# Lab Report 1 - Remote Access and FileSystem
# "cd" Command:
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

## Example 3:
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

# "ls" Command:

---

## Example 1:
```
#code block
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
[user@sahara ~/lecture1]$ 
```
The working directory when the program was run was "/home/lecture1". "ls" is a command that lists out the elements in a directory, so it makes sense
that it prints out the different files and directories in the working directory.

The output was not an error because the command performed as expected.

---

## Example 2:
```
#code block
[user@sahara ~/lecture1]$ ls messages
en-us.txt  es-mx.txt  fr.txt  zh-cn.txt
[user@sahara ~/lecture1]$ 
```
The working directory when the program was run was "/home/lecture1". "ls" is a command that lists out the elements in a directory, so it makes sense
it prints out the different files and directories in the specified directory in the working directory. When I ran "ls messages", it listed out the different elements in the messages directory.

The output was not an error because the command performed as expected.

---

## Example 3:
```
#code block
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
[user@sahara ~/lecture1]$ 
```
The working directory when the command was executed was "/home/lecture1". "ls" is a command that lists out the elements in a directory, but when it's used with a file instead, it looks for the specified file. If the name requested is not in the working directory, I expect it would return an output that says something along the lines of "no such file/directory".

The output was not an error because the command performed as expected.

---

# "cat" command

---

## Example 1:
```
#code block
[user@sahara ~/lecture1]$ cat




^C
[user@sahara ~/lecture1]$
```
When the command was executed, the working directory was "/home/lecture1". The "cat" command is used to concatenate and display specified files in the command. However, when it's used with no other command line arguments, it still waits for further inputs, which is why it makes sense I had to quit the execution of the command (using Control + C, which shows up as ^C)for the user prompt to appear again.

The output is an error because the command did not execute, and needed to be quit for the prompt to appear. 

---

## Example 2:
```
#code block
[user@sahara ~/lecture1]$ cat messages
cat: messages: Is a directory
[user@sahara ~/lecture1]$ 
```
The working directory was "/home/lecture1" when the command was executed. The "cat" command concatenates and displays the files specified in the command line arguments. So, it makes sense that the output would be an error saying that messages is a directory because the cat command is supposed to be used with files.

The output is an error because of the output message, which says, "cat: messages: Is a directory", basically saying that the command line argument, "messages", is a directory, and cannot be used with the cat command. The output does not perform the cat command's intended functionality, which is to display the contents of the input.

---

## Example 3:
```
#code block
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
[user@sahara ~/lecture1]$ 
```
The working directory was "/home/lecture1" when the command was executed. The "cat" command concatenates and displays the files specified in the command line arguments. So, it makes sense that the cat command would display the contents of Hello.java when the command was executed.

The output is not an error.




