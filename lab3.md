# Lab Report 3: Researching Commands 
For this lab report, I chose to research four different ways to use the command `grep` in my terminal. I used [ChatGPT](https://openai.com/blog/chatgpt) and [digitalocean.com](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix) to help me generate command-line options. The specific prompt I gave ChatGPT was "find different ways to use grep in my terminal."  It came up with a bunch of different options and I chose four of the most interesting/useful ones. For each of my options, I gave examples from the directories and files in `./technical` as well as cited my sources.  

## The Basic `grep` Command: 
**`$ grep "string-name" file-name.txt`**
* The grep command takes two arguments: a `string` (that you want to search for), and a `file` (that you are searching in). It then looks for the specified `string` in the specified `file` and prints out all of the lines that contain that string right in the terminal.
    * ![Image](grepsc1.png)
    * For example, I used the `grep` command here to search for the string `good` in the file `./technical/biomed/1468-6708-3-1.txt` by typing in `grep "good" ./technical/biomed/1468-6708-3-1.txt`. It printed out all of the lines in the file `1468-6708-3-1.txt` in my terminal.  

## Option 1: 
**`$ grep -r "string-name" directory-name/`**
* This command allows us to search recursively for a `string` in all of the `files` and `subdirectories` of a `directory`. This means that by adding the flag `-r` to the `grep` command, we are telling it to search for that `string` in the whole directory instead of a specific file. As a result, the file name along with the line containing that string gets printed out in the terminal. 
* This command can be very useful when we don't know what specific file to search in. 
       * Additionally, if we want to search in our current directory, we can also try `grep -r "string-name" *`
* Source: [ChatGPT](https://openai.com/blog/chatgpt)

**Example 1:** 
```
grep -r " love " ./docsearch

./docsearch/technical/government/About_LSC/Strategic_report.txt:we do not pursue state planning because we love planning. We don't
./docsearch/technical/government/About_LSC/Strategic_report.txt:really love planning-at least most of us do not. We love legal
./docsearch/technical/government/Media/Domestic_Violence_Ruling.txt:speak again.' People have financial difficulties. They may love the
./docsearch/technical/government/Media/Terrorist_Attack.txt:Curnin. "What I'd love to see is this [alternative bar exam] in
./docsearch/technical/government/Media/Assuring_Underprivileged.txt:& Ettinger in Los Angeles, where she combined her love of
./docsearch/technical/government/Media/Politician_Practices.txt:I love Jimmy Carter. I'm starting to feel the same way about Roy
./docsearch/technical/plos/journal.pbio.0020150.txt:        things to do. We would love to get it to the point that it would be useful [on an
./docsearch/technical/plos/pmed.0020060.txt:        destroy their love letters. Instead, she bequeathed us this charming insight into the
./docsearch/technical/plos/journal.pbio.0030065.txt:        love such standards to be used in text, but there is an understandable reluctance to impose
./docsearch/technical/911report/chapter-13.5.txt:                testimony, Mar. 24, 2004 ("I would love to be able to tell you who did it, who
./docsearch/technical/911report/chapter-3.txt:            Despite the problems that technology creates, Americans' love affair with it leads 
```
* This command is useful for cases like this, where we want to find all of the files that contain the string ` love ` inside the directory `./docsearch' 

**Example 2:**



## Option 2: 
**`$ grep --color "string-name" file-name.txt`**

* When we add `--color` to the grep command and run it in our terminal, it prints out all of the lines containing the specified `string` in the specifed `file.txt` **AND colors that `string` red.**
* Source: [Link](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)

**Example 1:**

`$ grep --color "tumors" ./technical/biomed/bcr45.txt`

![Image](grep--color1.png)
      **Markdown doesn't have a built-in method for changing text colors, so I provided an image of the output in [Visual Studio Code] (https://code.visualstudio.com/) instead of a code-block.**
*  In this example, `grep --color` searches for the string `tumors` in the file `bcr45.txt`, prints out the lines containing it, and changes the color of every string `tumors` to red. This is useful because it makes it easy to see where the string we are looking for is exactly located. It basically points out the string by changing its color to red. 
 
**Example 2:**

`$ grep --color "summer" ./technical/plos/journal.pbio.0020053.txt`
![Image](grep--color3.png)
       **Markdown doesn't have a built-in method for changing text colors, so I provided an image of the output in [Visual Studio Code] (https://code.visualstudio.com/) instead of a code-block.**
* Since there is only one line that contains the string `summer` in this file, that line is printed out with `summer` in red. `grep --color` changes the color of the string `summer` to red to make it easier for us to find where it is on that line. This can be very useful when we have multiple lines that contain the string we are searching for because it makes it easier to see the exact occurance of it, such as our ouput in example 1.

## Option 3: 

## Option 4: 

