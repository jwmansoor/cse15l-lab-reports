# Lab Report 1: Remote Access and File System
Hello everyone! This is a short tutorial that will go through the steps needed to be able to log into a course-sepecific account on ieng-6. It will have the exact steps I took, so make sure to follow along then try it on your own. 

## Step 1: Installing VS Code
![Image](Screenshot 39.png)

The first thing you want to do is download Viurtual Studio Code on your computer. If you already have VS code downloaded or you are using your school's computer lab, then you can skip this step. I had to do this step because I got a new computer that didn't have VS code.
* First, I went to this link https://code.visualstudio.com/ and downloaded the version for windows. If you have an Apple Macbook, then downlaod the version for Apple. After it has installed, click allow to open it. 
* I personally like to have my VS code on my taskbar because I use it alot as a Computer Science student, so I pinned it to my taskbar. You can do the same by long pressing the icon after you open it and choosing "pin to taskbar." 

## Step 2: Remotely Connecting
![Image](Screenshot 40.png)

Now, I was ready to get remote access by logging into a remote computer over the internet.
* First, if you are using a Windows computer like I am, you will need to install git for Windows. To do so, you want to download git from this link: https://git-scm.com/download/win. I followed the steps on this website https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994. Basically, you open the terminal in VS code by clicking on "terminal" on the top strip and you need to open the command pallete by pressing CTRL + SHIFT + P. Then, type "select default profile" in the search bar, and choose Git Bash as your default. In your terminal, click on the arrow next to the plus sign on the top right. Choose "Git Bash" from the menu. Now, you will have Git Bash be your default terminal. If you have a Macbook, just choose "bash" from the menu as it is already there.
* Now, I had to use the ssh command to connect to my remote server. I used the command "$ ssh cs15lsp23kl@ieng6.ucsd.edu" to connect to my specific account. In your terminal, type "ssh" + your specific course id. For this class, it will be "ssh" + "cs15lsp23" + the letters in your course specific account. To find those letters, you want to log into https://sdacs.ucsd.edu/~icc/index.php and check the letters after "cse15lsp23" on the button under "Additional Accounts". 
* Since it is the first time I logged into this server, it asked me to provide a passcode by stating the authenticity can't be established. I typed "yes" and typed in my password. You want to do the same thing because it is expected to get the message saying the authenticity can't be established since it is the first time you connect to that server. The computer doesn't know whether to trust your or not, in this case, since it is your first time. However, it is only an issue when you try to connect to a server you connect to often and get this message, because then it means someone oelse is trying to control the connecion. 
* Then, I got a long message saying I am currently logged into ieng-6-203.ucsd.edu with the cluster status of ieng-6-201, ieng-6-202, and ieng-6-203. When you get this, it means you have successfully connected! You could be connected to either one of these three servers, and you will know which one because it tells you "you are currently logged into ieng-6-THENUMBEROFTHESERVER. 
* I did not have an issue logging into the remote server, so I then discussed with my partner what this message means and we concluded that it meant we successfully logged in. I noticed that we did not log into the same server, and therefore we concuded the cluster status means how many people logged into each one.

## Step 3: Trying Some Commands
![Image](Screenshot 42.png)

Finally, I had to try some commands to explore this new remote server. You would want to do the same thing to get familiar with them. 
I ran these commands and noticed they have different functions as different commands printed different data. 
* $ cd~ and cd ran but printed nothing
* $ ls printed the unhidden file 
* $ ls -l printed information on the unhidden file, as well as showed its permissions
* $ ls -at printed all files including the hidden files and organized them by time  
* $ ls -lat printed all files with their permissions and organized them by time
* cat /home/linux/ieng6/cs15lsp23/public/hello.txt - printed "hello.txt"

