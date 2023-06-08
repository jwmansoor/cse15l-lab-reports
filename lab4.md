# Lab Report 4: SSH Keys
Below are the screenshots of recreating the steps 4-9 from lab 7, as well as an explanation of the exact keypresses/commands used to complete each step. 

## Step 4: Logging Into ieng6
<img width="434" alt="Screenshot 2023-06-07 at 10 03 26 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/aa19852e-715d-4ae3-aa88-43c63d8e7725">

* The exact keys I pressed to get to this step were `<up> <up> <up> <enter>`. That is because I had already typed the `ssh` command for logging into ieng6 earlier, so I did not have to retype it. I accessed it by using the `<up>` key three times (because it was 3 times up in my search history) and selected it by using the `<enter>` key for efficiency. Accessing the command this way saves me time and effort. 
* The command I ran to log into ieng6 was `ssh cs15lsp23kl@ieng6.ucsd.edu`. It did not prompt me for my password this time because I followed the instructions for generating SSH keys earlier in the lab! :)

## Step 5: Cloning the Fork of the Repository from Github: 
<img width="493" alt="Screenshot 2023-06-07 at 10 14 58 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/5af7f47f-2299-44c5-9be6-8af50f60c777">

* For this step, I just typed in `git clone ` and `<CTRL-V>` to paste my https link next to it. I could have used `CTRL-R` to access this command from my bash history, but I found it easier to type it and paste my link next to it because I already had the https link copied to clipboard. I then clicked `<enter>` after typing in my command to run it. 
* I used the command `git clone https://github.com/jwmansoor/lab7`. I always run this command to clone a github repository from the command line, as it is the most efficient way to do so. 

## Step 6: Running the Tests and Demonstrating They Fail 
<img width="541" alt="Screenshot 2023-06-07 at 10 36 08 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/5f399a7d-ff91-4622-9338-f3d65c7130e8">

* First, I had to change the directory to my desired one, which was lab7. For this step, I typed in `cd lab7` and `<enter>`. I found that directly typing in the command `cd` was the easiest way to do this, so I didn't need to access it in my history. 
* Then, I typed in `bash test.sh` to run the tests and demonstrate there was a failure. Again, I just typed in the command instead of looking it up in my history because it is one of the easier commands and I remember it, so I thought it would be more efficient if I just typed it in myself. After typing in the command, I clicked `<enter>` to send a signal for my computer to run it. 
* To sum up, the commands I used were `cd lab7` and `bash test.sh`, to change the directory and run the tests. 

## Step 7: Editing the Code File to Fix the Failing Test
<img width="652" alt="Screenshot 2023-06-07 at 11 51 54 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/adb16fb5-42b8-4bb6-ad0c-ccc3f5144770">

<img width="641" alt="Screenshot 2023-06-07 at 11 11 20 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/d3322ab9-e861-48de-a653-fdb57c17620f">

* To view the code in the `ListExamples.java` file, I accessed the vim command by pressing `<CTRL-R> <v> <enter>`. This time, I searched for the command in my history by clicking `<CTRL-R>`instead of typing it in, because it seemed more efficient to do so. The `vim` command allows me to view the code in the file and edit it if needed (by typing in `<i>` after). 
* Then, I pressed `<i>` to activate Insert mode and fix the mistake. 
* I looked for the blue comment that told me which part needed to be fixed, so then I moved my cursor when I got to the space after the `1` in `index1` and clicked on it with my mouse. I typed `<delete> <2>` to delete the 1 and change it to 2 instead.
* I pressed `<esc>` to exit insert mode and get back to the normal mode, and `:wq <enter>` to save my edit and exit the code. 

## Step 8: Running the Tests and Demonstrating They Now Succeed 
<img width="427" alt="Screenshot 2023-06-07 at 11 18 32 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/103e3e1d-d9e4-4563-bcea-b2824379f323">

* I pressed `<up> <up> <enter>` to access and run the `bash test.sh` command. I knew that it was there a few times up in my search history, because I had just run it earlier to check the tests in Step 6. The effect of these few keypresses was that it saved me time. 
* The `bash test.sh` command runs the tests in that bash file. It showed me that all the tests passed this time. 

## Step 9: Commmiting + Pushing to my Github Account 
<img width="542" alt="Screenshot 2023-06-07 at 11 34 25 PM" src="https://github.com/jwmansoor/cse15l-lab-reports/assets/130420272/0ca51b83-2973-4a21-8f7f-1f190bae0142">

* I used the `git ` commands to commit and push my changes to my repository. So, I typed in `git add . <enter>` to add the changes I made. Then, I typed the command `git commit -m "Yaay, I'm done, final step"` and clicked `<enter>` to commit. The words after `-m` made up my commit message. Lastly, I typed the command `git push` and `<enter>` to push push the resulting change to my Github account. 
* I see the git commands as my command-line tools, because they make it easy to clone, add, commit, and push. It saves me time and effort. 
