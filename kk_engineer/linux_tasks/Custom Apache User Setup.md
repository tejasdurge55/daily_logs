For some security reasons xFusionCorp Industries security team has decided to use custom Apache users for each web application hosted there rather than its default user. Since this is going to be the Apache user so it shouldn't use the default home directory. Create the user as per requirements given below:

a. Create a user named kareem on the App server 3 in Stratos Datacenter.

b. Set UID to 1755 and its home directory to /var/www/kareem
```
sudo useradd -u 1755 -d /var/www/kareem kareem
              |       |			  |
      userid(UID)     home directory     user
```
```
    1  sudo useradd -u 1755 -d /var/www/kareem kareem
    2  cat /etc/passwd
       kareem:x:1755:1755::/var/www/kareem:/bin/bash  -- 
    3  cd /var/
    4  ls
    5  sudo mkdir www
    6  cd www/
    7  sudo mkdir kareem
    8  ls -la
    9  sudo chown -R kareem kareem/
   10  ls -la
  
```
```
ls -la
total 12
drwxr-xr-x  3 root   root 4096 Feb 19 09:32 .
drwxr-xr-x 14 root   root 4096 Feb 19 09:31 ..
drwxr-xr-x  2 kareem root 4096 Feb 19 09:32 kareem
```
The format contains a few columns. Let's try to understand them:

permissions. Here we can see what kind of permission has the object. We will work with permissions... soon :)

number of hard links. By default every object has 1 hard link. What are links? We will learn it in 18th lesson.

Owner. The owner of the object. It doesn't mean who created it, but who owns it at this moment.

Group. Owner belongs to the group (of users). This inforation is here too. This means that our 'groupmates' have specific access to the file.

Size. File size in bytes.

date and time of last modification of the object.

file name.

Owner and group. For now it will be enough to know that we see on the listing above the names of the users and groups. The system keeps and translates them from numerical representation. These are UID for user identifier and GID for group identifier. We can list this information in numeric wayby entering the
ls -n 

Note :
======

	 1) everbody knows first we have to switch into app server 3 as per question
	 2) In this class i learnt how to delete a user command is (userdel -r USERNAME) , and also i remembered how to change ownership once again...

