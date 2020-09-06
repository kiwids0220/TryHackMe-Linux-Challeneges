# TryHackMe-Linux-Challeneges
This is the write up for TryHackMe-Linux-Challenege.
This is the Linux Chanlleges from TryHackMe. Shout out to Ben who created the room for us to experience the wholesomeness of Linux. The post is created 09/01/2020.

I do this just to get it refresh of how I was able to solve this room. 

Task 1: Deploy the virtual machine.

If you want to manually SSH into the machine, use the following credentials:

Username: garry
Password: letmein

How many visible files can you see in garrys home directory?
![t1.1](https://github.com/kiwids0220/TryHackMe-Linux-Challeneges/blob/master/t1.1.png)
![ssh](https://github.com/kiwids0220/TryHackMe-Linux-Challeneges/blob/master/ssh.png)



 

Once we have connected to the machine with ssh garry@machine_IP.  Then enter the password letmein. 

Let the room begin…

Task 2: 

#1 What is flag 1? 

Answer: as we know, command “ls” can be used to display the current files within the current working directories. And we can use “cat” to read a .txt file and output the texts. So the result will be shown below.
![linux](https://github.com/kiwids0220/TryHackMe-Linux-Challeneges/blob/master/t2.1.png)

#2 what is flag2 (just a reminder, I will not be going over the command mentioned in previous questions. Ex. ls, cat…

For task #2, we need to login as bob, and find the flag2. Well, for switching users, we can use the “su” command. 

And then let’s  see where is flag2. Spoil alert, it is not in the current directory. So this is when the ‘find’ tool comes in handy. Lets try ‘find  /  flag2 2>/dev/null | grep flag2. “2>/dev/null” simply means when we encounter the error messages, redirect them to /dev/null, which acts kind of like a black hole.

there we go, now we can use “cd” which stands for change directory to move ourself to the /home/bob directory. and with “cat” we can successfully obtain the flag.
![linux](https://github.com/kiwids0220/TryHackMe-Linux-Challeneges/blob/master/t2.2(2).png)

#3 flag3 

for flag3, we need to find the bash history of bob. Where do we find that? Try google it!  (HINT: try use ‘ls -la’) 

#4  Flag4 is about Cronjob. Well, with googling, we will be able to know where the cronjob list is stored. 

#5 flag5 is the same as previous find. so no more talk over that.

#6 is the same…

#7. look at the system processes. With googling, we know we can use command ‘px aux’ to check the system process.

#8. Try to read “tar” manual for the details. 



#9 find the hosts, it is referring the hosts record in /etc directory. 

#10, find the other users in the system. Linux stores all its user:group in /etc/passwd

 

#11 flag11 check  out the alias file by ~/.bashrc.

#12 find the motd.d directory file. 

#27 find / -xdev -type f -print0 2>/dev/null | xargs -0 grep -E ‘^[a-z0–9]{32}$’ 2>/dev/null (find the given string within all the files) -xdev, only search directories on the current filesystems. Print0 will correspond to the option of xargs.

#29 use “tr” -d ” \n” …./…./..

 

#31~32. Mysql, use show database;  exit; use; select * from …;

 
