# linux
Linux Notes


======
Linux
======

Pre-Requisites : Nothing

Note: AWS cloud account is required to setup Linux VM.

Syllabus : 

1) What is OS
2) Windows Vs Linux
3) Linux History and Distros
4) Linux VM Setup in AWS Cloud
5) Working with Files and Directories
6) Working with Text Filters
7) Working with Text Editors
8) Users & Groups Management
9) File permissions
10) Process Mgmt
11) Network Commands
12) Package Managers
13) How to deploy apps in linux
14) Linux Interview questions

==============================
What is Operating System (OS)
==============================

=> OS is a software which acts as mediator between users and computers

=> To use any computer OS is mandatory.

=> OS provides a platform to perform operations in the computer.

=> We have several Operating Systems in the market.

	Ex: Windows, Unix, Linux, Mac, Android, IOS etc...

===========
Windows OS
===========

=> Windows OS developed by Microsoft company

=> Windows OS is licensed os (we need to purchase).

=> Windows OS is GUI based.

=> Windows is single user based OS. Only one person can use at a time.

=> Security features are less in Windows, we need to install Anti Virus software to protect our files.

=> Windows OS is recommended for personal use only.

	Ex: Watching movies, playing games, coding, online classes..

==========
Linux OS
==========

=> Linux is community based OS.

=> Linux is Free and Open source OS.

=> Linux OS is multi user based os. Multiple users can access single linux machine at a time.

=> Linux OS supports both GUI and CLI.

=> Security features are very good in linux, Anti virus s/w is not required for linux machines.

=> Linux OS is highly recommended for business purpose

	Ex: Database servers, DevOps tools, App Deployments...

==============
Linux History
==============

=> Linux OS developed by Linus Torvalds in 1991.

=> Linus Torvalds used Minux OS to develop Linux OS.

	(Li)nus Torvalds + Mi(nux) = Linux

=====================
Linux Distributions	
=====================

=> Linus Torvalds provided linux os as free and open source.

=> Many companies downloaded linux os code and modified according to their requirements and released into market with their brand names those are called as Linux Distributions.

=> We have 200+ Linux Distributions/Flavours in the market...

 ex: Amazon Linux, Red Hat, Ubuntu, Cent OS, Kali, Fedora, SUSE...

==================
Environment Setup
==================

1) Install Linux OS directley in your computer. (Costly)

2) Install Linux OS as Guest OS in windows machine using Virtual box. (performance issue)

3) Setup Free Linux machine in AWS cloud. (recommended).

===================================================================

Step-1 : Login into AWS cloud with your account credentials.

Step-2 : Create Linux Machine using EC2 service (free of cost)

Step-3 : Download and install SSH Client softwares

	Ex: Git Bash, MobaXterm, putty...

Step-4 : Connect with Linux machine using SSH client software.

Step-5 : Execute Linux commands.

======================================================================
Refererence Videos : https://ashokit.in/yt-content/cloud-tutorials
======================================================================

====================
Linux Architecture
====================

1) SHELL

2) KERNEL

3) HARDWARE 


user --> linux cmd --> shell --> kernel --> linux hardware --> output

# display default shell of linux machine
$ echo $0

# display kernel version
$ uname -r

==================
Linux File System
==================

=> In Linux OS everything will be represented as file only.

=> Root Directory (/) is starting point for the linux machine.

=> Inside root directory we have several other directories like below

/home : It contains users home directories

		ashok : /home/ashok/

		john : /home/john/

		ec2-user : /home/ec2-user/

/bin : It contains system binaries

/boot : It contains system bootstrapping files

/dev : It contains device files

/lib: System libraries

/usr : User utilities and applications we can keep here

/mnt : Mounted File Systems

/opt : Optional software packages..

===================================
Working with files & directories
===================================

### mkdir : To create empty directory

### rmdir : To remove empty directory

### ls : To display content of present working dir

		ls
		ls -l
		ls -lr
		ls -lt
		ls -ltr
		ls -la

### touch : To create empty files

### rm : To remove file

### mv : rename + move

		mv <present-name> <name-name>

		mv <present-location> <new-location>

### cat : Using cat command we can perform below 3 operations

1) Create a new file with data

		$ cat > os.txt

Note: press CTRL + D to close the file		

2) Append data to existing file

		$ cat >> os.txt

3) Print file data

		$ cat os.txt

		$ cat -n os.txt

## tac : It is used to print file data from bottom to top

		$ tac os.txt

### cp : Copy data from one file to another file

		$ cp f1.txt f2.txt

Note: How to copy 2 files data to 3rd file

		$ cat f1.txt f2.txt > f3.txt

### wc : word count. It will display no.of lines, no.words and no.of chars available in the file.	

		$ wc f1.txt	

===========================
Working with Text Filters	
===========================

### head : It is used to print first 10 lines of the file.

		$ head f1.txt

		$ head -n 15 f1.txt

		$ head -n 40 f1.txt

### tail : It is used to print last 10 lines of the file.

		$ tail f1.txt

		$ tail -n 30 f1.txt

		$ tail -n 100 f1.txt

Note: To check application latest log msgs we will use tail command.		

### grep : Global Regular Expression print. It is used to print the lines which contains given key word.

		# Print lines which contains Java keyword
		$ grep 'Java' mydata.txt

		# Ignore case sensitive
		$ grep -i 'java' mydata.txt

		# Skip the lines which contains Java keyword
		$ grep -v 'Java' mydata.txt

====================================
Working with Text Editors in Linux
====================================

### vi : Visual Editor. It is used to edit file data.

		$ vi f1.txt

=> Vi editor works in 3 modes

	1) command mode ($ vi f1.txt)

	2) insert mode (press 'i' in keyboard)

	3) esc mode (press 'esc' in keyboard)

=> When we are in ESC mode we can use below 2 options

	1) Write & Quit (:wq)

	2) Quit without saving (:q!)

====================================================================

========================
file creation commands
=======================

touch : to create empty file

cat  : create file with data (cat > f1.txt)

cp : copy one file data into another file (cp f1.txt f2.txt)

vi : create and open file for editing (vi f3.txt)

====================
reading file data 
====================

cat : print file data from top to bottom

tac : print file data from bottom to top

head : print first 10 lines of file data

tail : print last 10 lines of file data

vi : open the file 


=============
SED Command
=============

=> SED stands for stream editor.

=> SED is used to process the file data (substitute, delete, print, insert).

=> Using SED command we can perform operations on the file without opening the file.

=> SED is very powerful command in linux.

=> we will use below options with SED command

	s - substitute

	d - delete

	p - print

	i - insert

-----------------------------------------------------------------
I like Linux OS
I want to learn Linux. Linux is easy.
Linux is famous. Linux is imp. Linux is free.
-----------------------------------------------------------------

# replace first occurance of linux with unix in every line
$ sed 's/Linux/Unix/' os.txt

# replace second occurance of linux with unix in every line
$ sed 's/Linux/Unix/2' os.txt

# replace third occurance of linux with unix in every line
sed 's/linux/unix/3' os.txt

# replace all occurances of linux keyword with unix
sed 's/linux/unix/g' os.txt

# substitute linux with unix and save changes in the orginal file
sed -i 's/linux/unix/g' os.txt


# delete first line of the file
sed -i '1d' os.txt

# delete 4th line of the file 
sed -i '4d' os.txt

# delete last line of the file
sed -i '$d' os.txt

# delete from 3rd line to last line
sed -i '3, $d' os.txt

# delete from 10th line to 15th line
sed -i '10, 15d' os.txt

# print 10th line only
sed -n '10p' os.txt

# print data from 2nd line to 5th line
sed -n '2,5p' os.txt

# insert data at the end of the file
sed -i '$a\hello friends' mydata.txt

# insert data in 2 nd line
sed -i '2i\hello friends' mydata.txt

=================================
Working with Zip files in linux
=================================

=> Zip is used for files archieve (compress)

## syntax to create zip file 

$ zip <zip-file-name> <data>

# create zip with all .txt files
zip myfiles *.txt

# extract zip file
unzip myfiles.zip

======================
Networking commands
======================

ping : To check connectivity

	ping www.google.com

	ping www.facebook.com

	ping 192.168.3.2

wget : It is used to download files from internet

	wget <url>

curl : It is used to send http request to the url

	curl https://dummyjson.com/quotes/random 

ifconfig : To get IP address of our machine

============================================================


=================
User Management
=================

=> Linux is a multi user based OS

=> Within one linux machine we can create multiple user accounts.

=> Multiple users can acces single linux machine and can perform multi tasking at time.

Note: "ec2-user" is a default user in "amazon linux" vm. ec2-user having sudo priviliges.

	Amazon Linux AMI => ec2-user

	Ubuntu AMI ==> ubuntu

Note: For every user one home directory will be available.

		ec2-user ==> /home/ec2-user

		john ==> /home/john

		smith ==> /home/smith

# display all users created
cat /etc/passwd		

# create new user
sudo useradd <uname>

# set pwd for user
sudo passwd <uname>

# switch user account
su <uname>

# navigate to current user home directory
cd ~

# delete user along with user home directory
sudo userdel <uname> --remove

# rename user
sudo usermod -l <new-name> <old-name>



/etc/passwd : This file contains user information.

/etc/shadow : This file contains user passwords in encrypted format


===================================
Working with user groups in linux
===================================

=> When we create user in linux, for that user one user group also will be created with the given username.

# display all user groups
cat /etc/group

# create group in linux
sudo groupadd <group-name>

# add user to group
sudo usermod -aG <group-name> <uname>

# remove user from group
sudo gpasswd -d <uname> <group-name>

# display users belongs to group
sudo lid -g <group-name>

# check one user belongs to how many groups
id <uname>

# delete group
sudo groupdel <group-name>

# changing group name
$ sudo groupmod -n <new-name> <old-name>

==================================================
How to give sudo priviliges for user in linux ?
==================================================

=> By configuring user details in "sudoers file" we can provide sudo priviliges to the user.

=> Using "sudoers" file we can control which user can run command as a superuser.

# print sudoers file content
sudo cat /etc/sudoers

# Open sudoers file
sudo visudo

# Add below line under root user
<uname>   ALL=(ALL)       ALL

=> After making changes, to close sudoers file press =>  ( CTRL + X + Y + Enter)

========================================================================================

Assignment : Create a new user in linux vm and connect to linux vm by using newly created user credentials.

========================================================================================

==========================
File Permissions in Linux
==========================

=> Using file permissions concept we can secure our files and we can protect our file data available in linux machine.

=> We have 3 types of permissions in linux

		r => read

		w => write

		x => execute

=> file/directory permissions will be represented like below

		rwxrwxrwx f1.txt

=> file permissions contains 9 characters and those are divided into 3 parts

	first 3 characters => user/owner permissions

	middle 3 characters => group permissions

	last 3 characters => other users permissions


=> Lets under file permissions with diff scenarios


Scenario-1 ::  rw-r--r--  f1.txt

		user => read + write
		group => read
		others => read

Scenario-2 :: rwxr-xr-x  f1.txt

		user => read + write + execute
		group => read + execute
		others => read + execute

Scenario-3 :  rwx--xr-x f1.txt

		user => read + write + execute
		group => execute
		others => read + execute


=> To change file/directory permissions we will use 'chmod'	command

			+  => To add permission
		
			-  => To remove permission

# Giving execute permission for user
$ chmod u+x f1.txt			

# giving write permission for group
$ chmod g+w f1.txt

# Remove execute permission for others
$ chmod o-x f1.txt

# give all permissions for group
$ chmod g+rwx f1.txt

# Remove all permissions for others
$ chmod o-rwx f1.txt

====================================
File Permissions in Numeric Format
====================================

0 => No Permission

1 => Execute

2 => Write

3 => ( 2 + 1) => Write + Execute

4 => Read

5 => (4 + 1) => Read + Execute

6 => (4 + 2) => Read + Write

7 => (6 + 1) => Read + Write + Execute


# ugo+x
chmod 111 f1.txt

# ugo+w
chmod 222 f1.txt

# ugo+wx
chmod 333 f1.txt

# u+r g+rx o+rw
chmod 456 f1.txt

# u+rwx g+rwx o+rwx
chmod 777 f1.txt

===============
chown command
===============

=> It is used to change file/directory ownership

# change owner
sudo chown new-owner <file/dir>

# change owner-group
sudo chown :new-group <file/directory>

# change owner & group of file/directory
sudo chown new-owner:new-group <file/directory>

=============================================
How to find the location of files in linux?
=============================================

=> In linux we can use 'find' command to search file paths.

# search for the files which are having name as f1.txt
sudo find /home -name f1.txt

# search for empty files inside /home
sudo find /home -type f -empty

# search for empty directories inside /home
sudo find /home -type d -empty

=====================
process management
=====================

Process management in Linux involves controlling and monitoring the execution of programs (processes) on the system. 

# display processes running with PID
$ ps aux

Note: Every process will have process id (PID)

# kill process
kill <PID>

# terminate process immediatley (forcefully)
kill -9 <PID>


==========================
Package Managers in Linux
==========================

=> Package means a software

	Ex: git, maven, java, python etc.....

=> package managers are used to manage software packages (softwares) in linux machine.

=> package managers are specific to linux distribution.

	Amazon Linux  ===> yum

	Ubuntu Linux  ===> apt

# check git client installed or not
git --version	

# install git client s/w
sudo yum install git -y

# check java installed or not
java -version

# install latest version of java s/w
sudo yum install java -y

# check java installation path
whereis java

# install java 11 version
sudo yum install java-11-amazon-corretto -y

# select java version when we install multiple versions
sudo alternatives --config java

# check maven installed or not
mvn -version

# install maven s/w
sudo yum install maven -y

# check maven installation path
whereis mvn

# install httpd webserver
sudo yum install httpd -y

# check httpd status
sudo service httpd status

# start httpd as service
sudo service httpd start

================================
What is systemctl in linux ?
================================

=> systemctl is used to manage services in linux machines.

=> using systemctl we can perform below operations

		a) start a service
		b) stop service
		c) re-start service

# stop httpd server
sudo systemctl stop httpd

# start httpd server
sudo systemctl start httpd

# reload service
sudo systemctl reload httpd

==============================
How to change hostname in vm
==============================

# set hostname
$ sudo hostname <new-name>

# close the session
$ exit 

Note: connect back to vm then we can see configured hostname.

===========================
Linux Commands Summary
===========================

1) whoami

2) pwd

3) date

4) cal

5) cd

6) ls

7) mkdir

8) rmdir

9) rm

10) touch

11) mv

12) cp

13) cat

14) tac

15) wc

16) head

17) tail

18) grep

19) vi

20) sed

21) zip

22) unzip

23) ping

24) wget

25) curl

26) ifconfig

27) find

28) uptime

29) free

30) top

31) ps aux

32) kill <pid>

33) useradd

34) passwd

35) userdel

36) usermod

37) groupadd

38) groupdel

39) gpasswd

40) lid

41) id

42) groupmod

43) chmod

44) chown

45) yum install

46) whereis

47) systemctl

48) sudo hostname



=======================================================
1) What is the difference between Linux and Unix?
=======================================================

Linux : Free Os. Community based

Unix : Proprioty os. Licensed.

=> Linux is a Unix-like system created from scratch in the early 1990s by Linus Torvalds, inspired by Unix but built independently.

=> Unix is the original operating system, developed in the 1970s at Bell Labs. Linux mimics its behavior but is not derived from its source code.

===========================================================================
2) How do you find out what process is using a specific port like 8080 ?
===========================================================================

sudo lsof -i :8080

sudo lsof -i :80

==========================================
3) What does the 'chmod 755' command do?
==========================================

user (7) : read + write + execute

group (5) : read + execute

others (5) : read + execute

===================================================================
4) What are file permissions in Linux? How do you change them?
===================================================================

rwxrwxrwx

===========================================
5) how to check linux distribution details
===========================================

cat /etc/os-release

========================================
6) How do you check disk space usage?
========================================

df -h

du -sh /dir/path/

=============================================
7) What command is used to view system logs?
=============================================

journalctl

===============================================
8) What is the difference between apt and yum?
===============================================

yum : RHEL-based (CentOS, Fedora, Amazon Linux)

apt : Debian-based (Ubuntu)

=====================================
9) How do you add a user to a group?
=====================================

sudo usermod -aG <group-name> <user-name>

================================================================
10) How do you search for a string in a file using the terminal?
================================================================

grep "search_term" filename

=================================================================
11) What is the difference between /etc/passwd and /etc/shadow ?
=================================================================

/etc/passwd: User details

/etc/shadow: Encrypted passwords (more secure)

=============================================
12) How do you manage services with systemd?
=============================================

using systemctl we can manage services

systemctl start nginx
systemctl enable docker
systemctl status sshd

=============================================
13) how to find 30 days old files in linux ?
=============================================

using find command with mtime.

================================================
14) How do you check network connectivity?
================================================

ping google.com

=============================================
15) How to find linux kernel version
=============================================

uname -r

================================================
16) How to find user belongs to which groups ?
================================================

id uname

================================================
17) How to check linux machine execution time ?
================================================

uptime

===================================================
18) How to change file/directory owner in linux ?
===================================================

chown

======================================================
19) How to enable pwd based authentication in linux ?
======================================================

we need to enable in "/etc/sshd/sshd_config" file

==========================================================
20) how to provide sudo priviliages for a user in linux ?
==========================================================

by configuring user in sudoers file  (visudo)

===================================================
21) How to create a user without home directory ?
===================================================

# create user along with home directory
sudo useradd john

# create user without home directory
sudo useradd -M smith

-M: Tells the system not to create a home directory (e.g., /home/smith).

=============================================
22) how to change password for the user ?
=============================================

sudo passwd <username>

=============================================
23) How do you update and upgrade packages?
=============================================

# redhat based os
sudo yum update

# debian based os
sudo apt update

===================================================
24) How do you check open ports and services?
===================================================

netstat -tuln or ss -tuln

===================================================
25) How do you find which process is using a port?
==================================================

netstat -tulpn | grep :port

==========================================
26) How do you list running processes?
==========================================

ps aux or top

# to kill process
kill -9 <pid>



linux
blob:https://www.ashokit.in/867ab7a8-b70a-4259-abb1-db41c0e098a8

==================================================
How to give sudo priviliges for user in linux ?
==================================================

=> By configuring user details in "sudoers file" we can provide sudo priviliges to the user.

=> Using "sudoers" file we can control which user can run command as a superuser.

# print sudoers file content
sudo cat /etc/sudoers

# Open sudoers file
sudo visudo

# Add below line under root user
<uname>   ALL=(ALL)       ALL

=> After making changes, to close sudoers file press =>  ( CTRL + X + Y + Enter)

========================================================================================

======================================================
19) How to enable pwd based authentication in linux ?
======================================================

we need to enable in "/etc/sshd/sshd_config" file


>whiami
ec2-user
>sudo vi /etc/ssh/sshd_config
change the ::::: PasswordAuthentication yes
:wq
>sudo service sshd restart
and now can connect with username and password
>ssh john@public_ip
enter password:
>whoami
john
>pwd
/home/john

===============================================================================================
pkg managers
yum ::::: Amazon linux, red hat, cent os
apt ::::: ubuntu, debian
===============================================================================================
httpd=> static website (gices same response for every user)
in browser ip:80 or publicip> It works!
default msg
To change   go to   >cd /var/www/html
>sudo vi index.html

===============================================================================================
Assignment: Deploy Spring boot web appl in Linux Machine.


also Refer To linux youtube video : https://www.youtube.com/watch?v=qRu26XpURNE
