# Day 06 — File Permissions and Access Control Lists
## Tasks:

### 1. Explain about file permissions and change the user permissions of a file named “file.txt” and note the changes after “ls -ltr”.
In Linux, every file and directory is owned by a specific user and group. The file’s owner has certain permissions, or access rights, to the file, which determine what they can do with it. There are three types of permissions that can be set for a file: read, write, and execute. There are also three types of permissions that can be set for a directory: read, write, and execute.

![1 (1)](https://user-images.githubusercontent.com/121767243/218312313-f2baf45f-7ed6-443a-8a0c-1574eb5e1563.png)

The “chmod” command is used to change the permissions of a file or directory. The permissions for a file or directory can be set for the owner, for the group that the file belongs to, and for all other users. The “u”, “g”, and “o” options stand for user, group, and others, respectively. The “+” and “-” signs are used to add and remove permissions, respectively. The “x” permission allows a file to be executed or a directory to be searched. The “w” permission allows a file to be modified or a directory to be modified by adding or deleting files. The “r” permission allows a file to be read or a directory to be listed.

### 2. Explain ACL and try out the commands “getfacl” and “setfacl”.
The “getfacl” and “setfacl” commands are used to get and set file access control lists (ACLs) in Linux. ACLs allow you to specify fine-grained permissions for files and directories beyond the standard user, group, and other permissions.

The output of the “getfacl” command will show the ACLs for the file, including the owner, group, and permissions for each user and group. For example:

![2](https://user-images.githubusercontent.com/121767243/218312335-2d5ffbc8-9b63-47dc-be51-8def0ab07f56.png)

“setfacl” is used to set or modify the ACLs of a file or directory.

For example, to give read and execute permissions to “user2" and read permission to “user3” for a file called “myfile” , you would run:
```
setfacl -m u:user2:rx,u:user3:r myfile
```
The “-m” option tells “setfacl” to modify the existing ACLs of the file. The “u:user2:rx” and “u:user3:r” values specify the permissions to set for “user2” and “user3" , respectively.
```
# file: myfile
# owner: user1
# group: group1
user::rw-
user:user2:r-x
user:user3:r--
group::r--
mask::r--
other::r--
```
In this example, the ACLs for the file now include entries for “user2” and “user3”, with the specified permissions.
