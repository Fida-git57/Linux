# Linux
Creating an Instance

Step1: Create an AWS account

Step2: Login and open EC2 Console]- https://console.aws.amazon.com
Select the region

Search for EC2 at the top of the AWS console

Step 3: Launch Instance

Give a Name
Create RedHat Linux Server with t2.micro instance Type

Key Pair -  Choose to create a new pair, Give a name and download the pem file
---------------------------------------------------------------------------------------
Connecting to the server

Step1: Download and install Mobaxterm

Step2: Open AWS console and Connect the Linux server

Copy the SSH id

Open Mobaxterm --> cd ~/Desktop/pemfile/
ls
paste the SSH id
uname
exit
----------------------------------------------------------------------------------------
LINUX

Linux is a multi-tasking, multi-user OS. It is a open Source developed by C language and is a case sensitive.
--------------------------------------------------------------------------------------------------------------
Linux Distributors:

1. RedHat
2. CentOS
3. Ubuntu
4. SuSe Linux
5. Fedora
6. Gentoo
7. Mandriva
8. Debian
-------------------------------------------------------------------------------------------------------------
Types of users in Linux
1.Root User----> ONE---->[Main]
2.Normal User----> N no. of users can connect. Eg: AB,BC
--------------------------------------------------------------------------------------------------------------
Linux Commands:

/ --> root directory/ parent directory
/home --> subdirectory --> it consits of all users info

/bin --> binary --> it contains binary files
/sbin --> s=system --> system binary 
-----------------------------------------------------------------------------------------
TYPES OF USERS IN Linux

1. Root user : 1 user --> it has all the prevailages
2. Normal User : n user --> Created by root user
---------------------------------------------------------------------------------------
Diff b/w bin and sbin
		They both have binary files, The binaries which are available in sbin can be accesible by only root user
but the binaries which are available in bin can be accesible by any of the user
--------------------------------------------------------------------------------------------------
/etc
This directory consists of all the configuration files
1. sudoers
2. passwd
3. shadow
4. group
5. cron.allow
6. motd
-------------------------------------------------------------------------------------------
/dev
dev= devices
This directory consists of all the devices info
----------------------------------------------------------------------------------------
/lib --> libraries
This directory contains all the libraries which are going to used by operating system
--------------------------------------------------------------------------------------
/proc --> 
 all the processes related info will be available in this
 cpuinfo --> this file contains cpu information
 --------------------------------------------------------------------------------------
 /opt
 by default this dir is empty
 All the external softwares are installed in this dirc
 This directory will be accesibleby only rootuser.
 --------------------------------------------------------------------------------------
 /temp --> temporary purpose
 This dirc can be accesible by any of the user.
 --------------------------------------------------------------------------------------
 /var 
 it consists of global variables, files.
		-log
		-html
------------------------------------------------------------------------------------
To create file and directories:
mkdir <directory_name> --> To create a directory_name
mkdir -v <directory_name> --> To show that diectory has created
	E.g : mkdir -v Devops
mkdir -p <directory_name> --> To create multiple directories inside one another
	E.g : mkdir -p Devops/linux/shell script/git/maven/tomcat/sonar qube
mkdir -vp Devops/linux/shell script/git/maven/tomcat/sonar qube
		The command shows which directory has first created in order
-v --> verbose    ,m- mode ,    -p --> parent
mkdir -m 700 phyton --> to create a directory with some custom permissions.
----------------------------------------------------------------------------------------
touch <file_name> --> To create a file
	E.g : touch devops.txt
	----------------------------------------------------------------------------------------
To list the files: (To check the output too)
ls --> To list all the files and directories
ls -l --> To list the files and directories in long format
ls -lt --> To list the files and directories sorted with time
ls -lrt --> To list the files and directories sorted with timein reverse 
ls -li -->inode : It is a data structure it can be used to store the info
		but doesn't contain 1 info i.e, file name or directory name but they contain info about
		the permissions, link,size ....
ls -la --> To see the hidden directories and files and it start with . (dot)
ls -lh --> Human readable format
----------------------------------------------------------------------------------------
To check the current directory:
pwd --> To check the present working directory
-----------------------------------------------------------------------------------------------
man 
	This command gives what all their in a command
	to come out type q
----------------------------------------------------------------------------------------------------
To delete the directories and files

1. rmdir <directory name>
		The above command deletes only empty files

2. rm <file_name> --> To delete a file
rm -rf <directory_name> --> To delete a directory
rm -f <file name >--> To delete a file
rm -rf * --> Remove all the files and directories in the present location
		r : recirsive , f- forcebly
-------------------------------------------------------------------------------------------------
Diff b/w rmdir and rm
	rm removes the files and directory
	rmdir removes the directories from the file system and the directory should be empty before deleting

---------------------------------------------------------------------------------------------------
To see in hirarchial format of all the directories
tree

To install 
In RedHat server to install we use yum command

In yum
	1.yum install tree
	2.yum update tree
	3.yum remove tree
This yum command will work only under root user
To switch to root user sudo su -
Then execute the yum command
switch back to normal user --> exit
----------------------------------------------------------------------------------------------
To change Directory:
cd <directory_name> --> To change the directory
cd .. --> To go back to a previous directory
cd ~ --> To goto home directory [/home/ec2-user]
cd - --> previous working directory
cd /etc --> Absolute path
cd etc --> Relative pat
----------------------------------------------------------------------------------------------
File Maintenace Commands
-----------------------------------------------------------------------------------------------------------------
touch --- To create empty files
	To update the content need to use some editors
	vi
	vim
	nano
1. vi ---> E.g: vi <filename> (It will be in command mode)
				i (insert mode)
				esc button
				:wq
----------------------------------------------------------------------------------------------------------------------
to check the content
cat <file name>
---------------------------------------------------------------------------------------------------
copy

cp <file_name1> <file_name2> --> To copy a file
cp <file_name> <dir>/<file_name> --> To copy a file from inside a directory
cp -r <dir1> <dir2> --> To copy a directory
---------------------------------------------------------------------------------------------------------
move -mv

mv <file_name1> <file_name2> --> To move a file
mv <file_name> <dir>/<file_name> --> To move a file inside a directory
mv -r <dir1> <dir2> --> To move a directory
-----------------------------------------------------------------------------------------------------
wc --> word count
	it shows how many lines , words, characters are there in particular file
		wc <filename>
		wc -l <filename>   ---> displays only lines
		wc -w <filename>   ---> displays only words
		wc -c <filename>   --> displays only characters
----------------------------------------------------------------------------------------------------------
echo 
echo "<text>" --> To print the text on the terminal
	echo hello guys
------------------------------------------------------------------------------------------------------------
cat tcsd.conf
	to display number of lines
	cat -n tcsd.conf
	
	To display top 10 lines  ---> head <filename>
	head -n 12 <filename>  ---> to display top 12 lines
	to display last 10 lines  ---> tail <filename>
	to display last 20 lines --> tail -n 20 <filename>
	to display range of specific line numbers ---> sed -n "90,98p" <filename>
----------------------------------------------------------------------------------------------------------
who --> To check all the users that are logged in to the server
who -H ----> heading
	This command gives about name,line,time,comment
w ---> this gives more info about users and what they are doing
uptime ---> how long the server is running
users ---> which user are connected to the server --> just the user name in this command
---------------------------------------------------------------------------------------------------
Diff b/w sudo su - and sudo su
sudo su -  ---> it will switch to the root user then it will load the root user configurations and it will point to the root user home directory
sudo su --> it will switch to the root user then it will not load the root user configurations and it will not point to the root user home directory
--------------------------------------------------------------------------------------
umask --> User mask : It is used to set the permissions
	when creating a file or directory it will be created with some default permissions.
	
			umask		dir		file

normal		0022		755		0644
root		0002		775		0664

Base permissions for dir is :0777
Base permissions for file is :0666

user  group  others
rwx   rwx    r-x
r-read--->4
w-write--->2
x-execute--->1
----------------------------------------------------------------------------------------------------------------------------------------------------
Diff b/w absolute and relative path
An absolute path begins with root directory
eg: /home/fidaarooj/linux/linux.txt
and relative path begins with current directory
eg: ./linux/linux.txt
----------------------------------------------------------------------------------------------------------------------------------

