## Login to the server as super user and perform below

## 1. Create users and set passwords – user1, user2, user3
sudo useradd user1
sudo useradd user2
sudo useradd user3

sudo passwd user1
sudo passwd user2
sudo passwd user3


## Create Groups – devops, aws

sudo groupadd devops
sudo groupadd aws

## Change primary group of user2, user3 to ‘devops’ group

sudo usermod -g devops user2
sudo usermod -g devops user3

## Add ‘aws’ group as secondary group to the ‘user1’

sudo usermod -a -G aws user1


## Create the file and directory structure shown in the above diagram.

`sudo su -`

`mkdir home dir1 dir2 dir3 dir3 dir4 dir5 dir6 dir7 dir8 opt`

touch f1.txt f2.txt

mkdir dir2/dir1

mkdir dir2/dir1/dir2/

mkdir dir2/dir1/dir2/dir10

mkdir dir2/dir1/dir2/f3.txt

mkdir dir3/dir11

mkdir dir4/dir12

touch dir4/dir12/f4.txt

touch dir4/dir12/f5.txt

mkdir dir5/dir13

mkdir dir7/dir10

touch dir7/f3.txt

mkdir dir8/dir9

mkdir opt/dir14

mkdir opt/dir14/dir10

touch opt/dir14/f3.txt


## Change group of /dir1, /dir7/dir10, /f2 to “devops” group

chgrp devops dir1
chgrp devops dir7/dir10
chgrp devops f2.txt

## Change ownership of /dir1, /dir7/dir10, /f2 to “user1” user.
chown user1 dir1 dir7/dir10 f2.txt


## 2.Login as user1 and perform below
## Create users and set passwords – user4, user5

sudo vi /etc/sudoers
su - user1

sudo useradd user4
sudo useradd user5

sudo passwd user4
sudo passwd user5

## Create Groups – app, database
sudo groupadd app
sudo groupadd database

 ## Login as ‘user4’ and perform below
## Create directory – /dir6/dir4
mkdir dir6
mkdir dir6/dir4

## Create file – /f3
touch f3.txt

## Move the file from “/dir1/f1” to “/dir2/dir1/dir2”
mv -i dir1/f1.txt dir2/dir1/dir2
## Rename the file ‘/f2′ to /f4’
mv f2.txt f4.txt

## Login as ‘user1’ and perform below
## Create directory – “/home/user2/dir1”
sudo mkdir /home/user2/dir1

## Change to “/dir2/dir1/dir2/dir10” directory and create file “/opt/dir14/dir10/f1” using relative path method.

cd /dir2/dir1/dir2/dir10

touch opt/dir14/dir10/f1.txt

## Move the file from “/opt/dir14/dir10/f1” to  user1 home directory

mv root/opt/dir14/dir10/f1.txt  /home/user1

## Delete the directory recursively “/dir4”

[root@ip-172-31-6-26 ~]# rm -r dir4
rm: descend into directory 'dir4'? yes
rm: descend into directory 'dir4/dir12'? yes
rm: remove regular empty file 'dir4/dir12/f4.txt'? yes
rm: remove regular empty file 'dir4/dir12/f5.txt'? yes
rm: remove directory 'dir4/dir12'? yes
rm: remove directory 'dir4'? yes

## Delete all child files and directories under “/opt/dir14” using single command.
[root@ip-172-31-6-26 ~]# rm -r opt/dir14
rm: descend into directory 'opt/dir14'? yes
rm: remove directory 'opt/dir14/dir10'? yes
rm: remove regular empty file 'opt/dir14/f3.txt'? yes
rm: remove directory 'opt/dir14'? no
[root@ip-172-31-6-26 ~]# ls

## Write this text “Linux assessment for an DevOps Engineer!! Learn with Fun!!” to the /f3 file and save it.
echo "Linux assessment for an Devops Engineer!! Learn with Fun!! " > dir2/dir1/dir2/f3.txt

Login as ‘user2’ and perform below
Create file “/dir1/f2”

## Delete /dir6
rmdir dir6

## Delete /dir8
[root@ip-172-31-6-26 ~]# rm -r dir8
rm: descend into directory 'dir8'? yes
rm: remove directory 'dir8/dir9'? yes
rm: remove directory 'dir8'? yes


## Replace the “DevOps” text to “devops” in the /f3 file without using  editor.

Using Vi-Editor copy the line1 and paste 10 times in the file /f3.

Search for the pattern “Engineer” and replace with “engineer” in the file /f3 using single command.

Delete /f3

Login as ‘root’ user and perform below

Search for the file name ‘f3’ in the server and list all absolute  paths where f3 file is found.

Show the count of the number of files in the directory ‘/’

Print last line of the file ‘/etc/passwd’

Login to AWS and create 5GB EBS volume in the same AZ of the EC2 instance and attach EBS volume to the Instance.

Login as ‘root’user and perform below

Create File System on the new EBS volume attached in the previous step

Mount the File System on /data directory

Verify File System utilization using ‘df -h’ command – This command must show /data file system

Create file ‘f1’ in the /data file system.

Login as ‘user5’ and perform below

Delete /dir1

Delete /dir2

Delete /dir3

Delete /dir5

Delete /dir7

Delete /f1 & /f4

Delete /opt/dir14

Logins as ‘root’ user and perform below

Delete users – ‘user1, user2, user3, user4, user5’

Delete groups – app, aws, database, devops

Delete home directories  of all users ‘user1, user2, user3, user4, user5’ if any exists still.

Unmount /data file system

Delete /data directory

Login to AWS and detach EBS volume to the EC2 Instance and delete the volume and then terminate EC2 instance.
