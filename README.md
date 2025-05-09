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

mv command can be used to move the files or dir from one location to another location and also renaming.
	cp is just to copy files or directories

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

user/owner 	 group 	 others
rwx  		 rwx   	 r-x
r-read--->4
w-write--->2
x-execute--->1

r- Read Permission
w- Write Permission
x- Execute Permission
- --> No permission
rwx
rw- --> Owner of the file
rw- --> Group to which the file belongs
r-- --> Others

rw-rw-r--		:664
rwxrwx-x		:771

rwx --> 7
rw --> 6
x --> 1
- --> 0

chmod 664 <file_name> --> To give rw for owner, rw for group, r for others
chmod 777 <file_name> --> to rwx for owner, group and others
chmod 740 <file_name> --> To give rwx for owner, r for groups, no permission for others

chmod u+x <file_name> --> To give owner the executable permission
chmod o-w <file_name> --> To Remove write permission from the the others

u --> Owner
o --> Others
g --> Groups

----------------------------------------------------------------------------------------------------------------------------------------------------
Diff b/w absolute and relative path
An absolute path begins with root directory
eg: /home/fidaarooj/linux/linux.txt
and relative path begins with current directory
eg: ./linux/linux.txt

----------------------------------------------------------------------------------------------------------------------------------
chmod -change mode ---> changing the access permissions
chmod -R permisions <directive name>
-R --> recursive
e.g:	chmod 777 devops.txt
		chmod +r devops.txt
		chmod u+rwx devops.txt  --> it will change to rwx for just users
				u= users , g= groups , 0= execute
				
		chmod ugo-rwx <filename>  --> to remove all the permissions
  --------------------------------------------------------------------------------------------------------------------------------
  chown ---> ONLY ROOT USER SHOULD EXECUTE
		to change the ownership(group)
		
	chown -R <directory name> --> to change the ownership of sub directories
 ------------------------------------------------------------------------------------------------------------------------------
 chgrp --> To change the groupname and filename
chgrp -R groupname filename

To check the groups we can see in etc/
  --> cat /etc/group
	there we can see and can change the groupname to any group
			E.G: chgrp wheel <filename>
TO change username and groupname at a time
		chown username:groupname filename
  
  -----------------------------------------------------------------------------------------------------------------------------------------
  ln --> for creating link b/w files
HARD LINK							SOFT LINK					of-original file
1.ln of lf							ln -s of lf					lf -link file
2.of and lf both have same				of and lf having different
properties						properties
3.create only for files				 	creates dirs and files
4.of and lf same inode					of and lf have diff inodes
5.if we delete the of still we can			cannot
 able to access lf

------------------------------------------------------------------------------------------------------------------------------------------
Text editor commands
---------------------------------------------------------------------------------------------------------------------------------------------------------------
vi
vim
nano

-----------------------------------------------------------------------------------------------------------------------------------------------------------
vi 
by usinf vi editor we can create the files and update the files
	Eg:	1)	vi python.txt					2)  vi python.txt									3) vi python.txt
			Command mode						Command mode									:q
			i  --> insert mode					i										In this case  we didn't updated anything
			.......							Hello -->Hi
			esc button						esc
			:wq							:q!   --->(without saving forcebly close)
   
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
vim
	vim vimtest.txt
	First need to install vim by root dir and install
	
	eg
:se nu --> set numbers for particular file in vim
:108 --> for specifying particular lines	
:se nonu --> to remove numbers of lines
/<word>  ---> to search something word
:q for closing

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
nano
	This editor does not has command or insert mode by default it is going to open in insert mode
	
	eg: nano test.txt
		Iam creating nano test editor
		
		nano test.py
		Hello guys............
		ctrl o ---> for saving
		ctrl x ---> for closing
  ----------------------------------------------------------------------------------------------------------------------------
hostname --> To check the ip address of the system [private ip address]
To display Ip address
1. ifconfig
		to install ifconfig ---> yum install net-toolse
2. ip a
3. hostname -i

To change the hostname change to root user
	hostname <new hostname>
	exit

 ----------------------------------------------------------------------------------------------------------------------------------
  service --> it will give the status of service
		service /systemctl
		
		systemctl list-units-files ---> to see the running services
		service sn option --> option(status/start/stop/restart)   sn=service name
		
	To change the services it should be done through the root user
--------------------------------------------------------------------------------------------------------------------------
last --> to check when users have logged in it gives all the info about what time we logged and logged out and date
PROCESS MANAGEMENT COMMANDS

-------------------------------------------------------------------------------------------------------------------------------
ps: display the current process running
ps -ef ---> gives detailed info e=all f=formatted way
	PID =process ID
	ppid=Praent Process ID
 
------------------------------------------------------------------------------------------------------------------------------------
kill --> kill the process 
	kill -9 PID
	
	kill have 1-64 types of signal --> kill -l
------------------------------------------------------------------------------------------------------------------------
top --> monitory utility

sar --> resources utilization 1hr-2hr back.

-----------------------------------------------------------------------------------------------------------------------------------------
ARCHIVE / DATA BACKUP Commands

-------------------------------------------------------------------------------------------------------------------------------------------
zip ---> zip -r <zip filename> <directoryname>

unzip --> to extract directory --> unzip <zip filename>
To unzip in a particular directory --> unzip <zip filename> -d /tmp/

tar -cvf--> creating tar file  ---> tar -cvf <tar filename> <directoryname>
						tar -zcvf <tar filename.gz> <directoryname>
	c=create   v=verbose  f=file system   .gz=gunzip  z=gunzip file   x=extract
To extract tar file ---> tar -cvf <tar filename>	
To extract gz file ---> tar -zcvf <gz filename>	

	
	
e.g: 	devops              --------> 10GB
	devops.zip          --------> 1GB
	devops.tar	    --------> 500 MB
	devopa.tar.gz	    ---------> 200 MB
	compresses more
 
 -----------------------------------------------------------------------------------------------------------------------------------------------
USER/GROUP ADMINISTRATIVE 

----------------------------------------------------------------------------------------------------------------------------------------------------
useradd <user_name> --> To add a user to the server    : ROOT USER CAN DO This

RHEL 7.x onwards UID starts with 1000
UID-->user ID

RHEL 6.x or lower --> 500

UID for root user -->0

----------------------------------------------------------------------------------------------------------------------------------
To set the password
passwd <password>
	If we set the password it will be in shadow file.
	
	passwd <user_name> --> To set the password for the user
	ec2-user:!!:19239:0:99999:7:::
	fida:!!:19253:0:99999:7:::
		Here the !! we be replaced by password
		
	cat /etc/passwd
-----------------------------------------------------------------------------------------------------------------------------------	
Chage ---> changing the expiry date of the passwords
	chage <username>
	
-------------------------------------------------------------------------------------------------------------------------------------------
groupadd <groupname>   --> to create group
To check cat /etc/group

-----------------------------------------------------------------------------------------------------------
usermod --> user modification
To add one user to one group
usermod -g <groupname> <which user>
 
we can lock and unlock the user
usermod -L <username>  --->LOCK
usermod -U <username>  -->UNLOCK
  
------------------------------------------------------------------------------------------------------------------------ 
 To check the group
 lid -g <group name>
 
-------------------------------------------------------------------------------------------------------------------------	
id <username>  or groups<username> ---> TO check a user is in how many groups

---------------------------------------------------------------------------------------------------------------------------------
free --> To find the  amount of free and used RAM memory

dmidecode -t 17 --> It gives RAM info --> Only ROOT user

vmstat --> It will give virtual memory statistics.

mail -->Need to install
	For installing we need to configure SMTP server with Linux server
	
	Syntax : mail emailid
			 subject:
			 (Email body)
			 ctrl D 
-----------------------------------------------------------------------------------------------------------------------------
clear --> clears the screen --> Linux
	In windows --> cls
 
-------------------------------------------------------------------------------------------------------------
cal --> Displays the calender
	cal -1 --> display current month
	cal -3 --> display previous,current,next month
	cal <year> --> to display particular year
	cal <month> <year> --> to display particular month and year 
 
-----------------------------------------------------------------------------------------------------------
sort ---> to arrange
	vi friends.txt
	content:wq
	sort friends.txt
	
	or
	
	cat friends.txt | sort
	
	here | --> pipe
	here cat command input is given as a output to the sort command by using pipe
	
	cat friends.txt | sort |tr [a-z] [A-Z]    ----> here sort command is given as output for other command
						In this tr --> translate smaller letters to caps
------------------------------------------------------------------------------------------------------------------						
grep --> global regular expression print
	Used to search for strings inside a file

		grep Fida friends.txt    ---> to search content in particular file
		grep -e "<pattern1>" -e "<pattern2>" --> To search for multiple patterns
		grep -i zeba friends.txt  ---> to search content irrespective of case in file
----------------------------------------------------------------------------------------------------------
sed --->stream editor used to find and replace words
	sed -n "90,98p" <filename> to search b/w range
	sed -n "90p" tcsd.conf ----> for particular line to display
	sed "s/<old string>/<new string>/" sample.txt   ---> To replace old string with new string 
	sed "s/<old string>/<new string>/g" sample.txt  --> To replace old string with new string and make changes to the file
	
sed '2s/<old_string>/<new_string>/g' <file_name> --> To replace old string with new string in 2nd line
sed '2,4s/<old_string>/<new_string>/g' <file_name> --> To replace old string with new string from 2nd to 4th line
sed '2,$s/<old_string>/<new_string>/g' <file_name> --> To replace old string with new string from 2nd to end of file

sed '4d' <file_name> --> To delete the 4th line
sed '2,4d' <file_name> --> To delete the from 2nd to 4th line
sed '2,$d' <file_name> --> To delete the 2nd to end of the file

sed -n '2p' <file_name> --> To print the 2nd line
sed -n '2,4p' <file_name> --> To print the 2nd to the 4th line
sed -n '2,$p' <file_name> --> To print the 2nd to end of file

---------------------------------------------------------------------------------------------------------
SYESTEM RESOURCES COMMANDS

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
who --> To check all the users that are logged in to the server
who -H ----> heading
	This command gives about name,line,time,comment
w ---> this gives more info about users and what they are doing
uptime ---> how long the server is running
users ---> which user are connected to the server --> just the user name in this command
whoami --> To check the current user

--------------------------------------------------------------------------------------------------------

load average : how much cpu utilization it gives 3 values that is the interval time
				1Min	5MIN	15th MIN
				0.00	0.00	0.00
    
------------------------------------------------------------------------------------------------------------------------
Binary files
Manual files ---> documentation

whereis <dir/file>--> it gives the path where that file or dir is
man <dir> ---> description about what and all inside is this in that option

----------------------------------------------------------------------------------------------------------
date --> print or set the system date and time and time zone
		As normal user can't set the date
	timedatectl -->  to see complete details of time zone.
 
------------------------------------------------------------------------------------------------	
df ---> disk feed
Hard disk indo will be in dev dirc
File Size and Disk Size

df -h --> To check the disk size of the server
free -h --> To check the system memory of the server [RAM]

du -sh <file_name> --> To check the file size

