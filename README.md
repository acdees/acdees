<!---
acdees/acdees is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

# Over The Wire Bandit Game

### Level 0

The goal of this level was to login onto the server where the game is stored. I was given the information the the name of the site, a username and password to sign into it, the port it needs to connect to, and the fact that it was an ssh.

I used https://www.wikihow.com/Use-SSH to understand how to use an ssh and what it is exactly. I also used the SSH man page to look for the version of the command that i needed

I first tried ssh -L bandit.labs.overthewire.org which did not work. I also tried ssh bandit.labs.overthewire.org to get access, however the port was not specified correctly so access was denied

![image](https://github.com/acdees/acdees/assets/158079550/37196b51-5427-4e7b-9bbc-4326b18f7264)

Finallly I gained access by using the command ssh bandit0@bandit.labs.overthewire.org -p 2220

It then prompted for a password which was Bandit0

Now that I was loged in the game finally began and the real level 0 could be started.

To continue to level one I had to find and print data from the file readme which was located in the home directory.

I used cd to change to the home directory and ls to make sure that i was in the right spot. I used cat -A to print the contents of the readme file and got the passowrd.
I found these commands by looking at the man pages for level 0's suggested commands.

The password is: 
**NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL**

Each time I gained a password for a level I had to relogin to the game using the username of bandit# and the password i found in the previous level. (# represents the number of whatever level I was trying to access)

### Level 1

For this level I had to print the contents of a file with a dash (‘ - ‘) as its name. 

I searched on google for how to call a file with a dash as its name and found the answer on the stackoverflow website.

![image](https://github.com/acdees/acdees/assets/158079550/a4b97759-d30e-4906-9b3a-e467c5cd360e)

I used the command cat ./- to get the output of the file.

**rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi** was the password that was output for the next level

### Level 2

The goal of level two was to print data from a file that contained spaces in its name. 

I used google to find methods to do this and chose to use the method of putting the full name after cat in double quotations (‘ “ ‘) 

![image](https://github.com/acdees/acdees/assets/158079550/47e1e641-26fb-47df-89f4-156163ce91db)

I used the line: cat "spaces in this filename"

However I also found that another way to do this was: cat spaces\in\this\filename Regardless of which I did, I still got the output with the password which was 

**aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG**

### Level 3

The goal of this level was to access a hidden file in the inhere directory and print the password from it.

I used the command cd inhere to move directories.  I tried using ls to see any files but since they were hidden I couldn’t see them.

I looked through the man pages for ls, file and find. I found that I could use the find command to search for files in a directory
and used it to see what files were in the directory including the hidden ones. The command caused two files to output . and ./.hidden
I then used the command cat ./.hidden and got the password:

**2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe**

### Level 4

The task for this level was like the last in which I needed to access a file in the inhere directory. The difference being that this time the file I needed was the only human-readable file in the directory.

After doing cd inhere and using ls to check the available files, I was given an output of 10 different file names.

![image](https://github.com/acdees/acdees/assets/158079550/5a19e814-d890-4b3b-a881-23f88936f742)

I used the man page and to understnd how to use the file command and the differnt options I had for what it output. I also used google to see how to put the name in the command because the man page did not seem very clear.

I then used the find command to see the names of all the files and then used the file command to check their types

![image](https://github.com/acdees/acdees/assets/158079550/73a4c7e4-f67b-455d-96bf-0991194cbe5e)

![image](https://github.com/acdees/acdees/assets/158079550/9cd6333a-accf-4b21-971b-a69abf24eb05)

After doing this I put in the command cat ./-file07 and got the password: 

**lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR**

### Level 5

For level 5 I had to find the password that was in a file that met certain criteria.
It was in the directory inhere and the file was a specific type and length.

To find the file with the correct size I first used the find -size 1033c command. I use the man page to find how to specify the length of the file and used google to find how to say that it was in bytes.

This output that the file i wanted was in the maybehere07 director. I changed directories to maybehere07 and checked using the file command for which version of file2 was the text file of the right length.

After that I found the password for level 6 to be:

**P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU**

### Level 6

For level 6 the password could be found in a file owned by a specific user and group and the file was a certain size.
Using the find command I searched for the group, user and size of the file I needed. 

I thought I had done something wrong but I realized that within the many files that said permission denied, one of them was different than the others. This was the /var/lib/dpkg/info/bandit7.password

To get the output of the password I did a simple cat “/var/lib/dpkg/info/bandit7.password” command and got:

**z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S**

![image](https://github.com/acdees/acdees/assets/158079550/6be0fced-fedd-460f-a773-98b2c2f8565f)

### Level 7

For this level the password could be found in a specific text file next to the word millionth. 

I knew that I needed to use the grep command but I did not know the opperation for finding a specific word, so I looked in the man page and found -w

![image](https://github.com/acdees/acdees/assets/158079550/f7060c84-b92e-482a-9a9e-68fe44c9af9b)

Using this I did the command grep -w millionth* and got the password:

**TESKZC0XvTetK0S9xNwm25STk5iWrBvP**

I had first tried doing grep -w millionth but it did not output anything for me without the wildcard added in.

### Level 8

The password to move on to level 9 could be found in the data.txt file. It is the only line of text that shows up exactly once. 

I used the sort command on data.txt so it would be easy to spot if something didn’t have a pair. This allowed me to find the password:

**EN632PlfYiZbn3PhVK3XOGSlNInNE00t**

After finding the password I tried again to find it using strictly commands. I tried using the sort and uniq commands together but it would give me a long list of different strings and not the strictly unique string.

I finally found a way for it to work using pipes and the -u option for uniq. The command line that found me the password was

![image](https://github.com/acdees/acdees/assets/158079550/b3c4a869-7507-4add-b034-105180c8a04a)

Even though I had already found the password, I didn’t like that I couldn’t find it strictly with commands as I felt that was the point of the game. 

After finally getting a command line to work it served as a double check that the password I found when looking through the sorted list was still the one I was looking for overall.

### Level 9

The password for level 10 is in the data.txt file. It is a human-readable string with multiple ‘=’ in front of it. 

To find only the readable data I used the strings command and I used the man page to see how this command worked.
After doing this I could look through the strings and find the correct password, however I wanted to be able to narrow it down more. 

I first tried using the sort but that did not help me much. I then thought to use the grep and designate multiple of the equal symbols for what grep was looking for. this was because the level had specified that there would be multiple equal signs preceding the password. 

To get the grep to be most effective I first used the strings command and then piped that output into a grep. This allowed me to narrow down my options to 4 and in those options the text read the message “the password is” and then the following line held the password:
**G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s**

![image](https://github.com/acdees/acdees/assets/158079550/6c0d6cb6-dd99-490e-8316-5d7bfff0c8cf)

### Level 10

For level 10 I needed find the password in the data.txt file. The difference with this file is that it contained base64 encoded data.

I used the binary64 wiki page to learn what binary 64 was and then used the man page for binary64 to see what command I would need to use to decode the data.

Once I knew the command I then knew that I could pipe the output to a cat and it would show me what the strings in the file were. 

![image](https://github.com/acdees/acdees/assets/158079550/dc3562d3-73d5-407e-bf57-33cd7fc92af1)

The password ended up being:

**6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM**

### Overall

This is a very fun and easy way to learn how to navigate linux commands. While it is a little daunting to start with, because you dont know how to do anything yet, the suggestions that overthewire gives you are very helpful and because you are just trying to learn techniques on how to use the terminal, there are many ways for you to learn and do things. Its nice being able to get to a solution to a problem without worrying that you didnt follow the right format. The thing I like about coding is there is always some goal you are trying to achieve. This was also enjoyable because not only is the game a fun tool to learn commands, but I know that learning them is benefical for me and that I will likely need to know them in the future. Even if I end up not doing much in Linux, the basis of terminal coding will still be helpful knowledge.















