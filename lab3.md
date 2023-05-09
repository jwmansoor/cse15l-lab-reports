# Lab Report 3: Researching Commands 
For this lab report, I chose to research four different ways to use the command `grep` in my terminal. I used [ChatGPT](https://openai.com/blog/chatgpt) to help me generate command-line options. For each of my options, I gave examples from the directories and files in `./technical` as well as cited my sources. 

## The Basic `grep` Command: 
`grep "string" file.txt`

* The grep command takes two arguments: a `string` that you are searching for, and the `file` that you are searching in. It then looks for the specified `string` in the specified file and prints out all of the lines containing that string right in the terminal.

`grep path/to/directory/* .txt)`
* While you can't use the `grep` command to search for a file within a directory (use `find` or `locate` instead), you can use it to search for a `string` in all files in that directory. It looks for that `string` in the directory then prints out all the lines that contain it.
* The format above gives you the option to add a file extension, like `.txt` or `.java` in case you were looking for a word in a specific kind of file. 

## Option 1: 
`grep -r "string" directory/`
* This command 

