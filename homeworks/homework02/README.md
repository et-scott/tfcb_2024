# Homework 2: Unix shell

This homework will assess your ability to run commands in the shell and make a simple script.

Replace the lines specified in _italics_ with your answers and save as a text file.


## Problem 0

**60 points**

Complete the interactive tutorial.

_Did you hit any points of frustration, and if so, how could we improve the material to avoid that frustration?_


## Problem 1

**20 points**

**Write a script that outputs some user and location data and moves that output to a newly created directory**

Make a single script that prints out a file called question01.txt. 

This file should contain the following text:

  My username is (your username, but the script needs to work for anyone, not just you)

  My home directory is (your home directory, but the script needs to work for anyone, not just you)

  The contents of the tfcb_2023/lectures/lecture04/ directory are

  (prints the contents of that directory)

This script should also create a directory called homework02, and move question01.txt into the homework02 directory.

An example output answer should be:

My username is campbellm <br>
My home directory is /Users/melody <br>
The contents of the tfcb_2023/lectures/lecture04/ directory are<br>
01-first-steps.md<br>
02-directories<br>
03-redirection<br>
04-vim<br>
05-history<br>
06-scripting<br>
07-more-interactive-shell<br>
README.md<br>
quickref.md<br>
sequence.gb<br>
slides<br>
vader.txt<br>

#Define new file
Q1_file="question01.txt"

#Define directory 
lecture_dir=/Users/eijahscott/Documents/GitHub/MCB-536/tfcb_2023-main/lectures/lecture04

#Define directory content
lecture_contents=$(ls "$lecture_dir")

#Define username and home directory
sername=$(whoami)
home_dir=$HOME

#Output
echo "My username is $username" > "$Q1_file"
echo "My home directory is $home_dir" >> "$Q1_file"
echo "The contents of the tfcb_2023/lectures/lecture04/ directory are $lecture_contents" >> "$Q1_file"

#Make new directory 
mkdir -p homework02

#Move file
mv "$Q1_file" homework02/

#Print the content
cat homework02/question01.txt

## Problem 2

**20 points**

**Write a script that uses a loop to output files with specific names**


Make a single script that does the following:

Makes a new directory in homework02 called question02

In that directory, your script should make 25 new files called
file###.txt

the ### should be the numbers from a list you can find here:

tfcb_2023/homeworks/homework02/list.txt

You can make the contents of those files whatever you want (hint: slide 9... )

mkdir -p homework02/question02

for num in 504 569 231 717 986 528 759 654 751 262 889 281 186 108 388 374 148 716 637 550 382 797 477 202 699; do touch "homework02/question02/file${num}.txt"
done
