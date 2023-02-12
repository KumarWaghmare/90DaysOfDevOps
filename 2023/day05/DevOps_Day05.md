# Day 05 — Advanced Linux Shell Scripting for DevOps Engineers with User management
## Tasks:

### 1. Write a bash script CreateDirectories.sh that when the script is executed with three given arguments (one is directory name and second is start number of directories and third is the end number of directories) it creates specified number of directories with a dynamic directory name.
This script will create a series of directories with names that are formed by concatenating the value of the variable “$1" with the values of the variable “$i” as it iterates through a range of values specified by “$2” and “$3”.

The script uses a “for” loop to iterate through the range of values specified by “$2” and “$3”. The loop variable “$i” is initialized to the value of “$2”, and the loop continues until “$i” is greater than “$3”. The body of the loop creates a new directory using the “mkdir” command and the value of “$1” concatenated with the value of “$i”.
```
#!/bin/bash 

for ((i=$2;i<=$3;i++))
do 
 mkdir $1$i
done
```
It would create the following directories:

![1 (1)](https://user-images.githubusercontent.com/121767243/218311797-3ef92119-1bae-444c-a453-9bc38b6559af.png)

### 2. Create a Script to backup all your work done till now.
This script sets the current date and time, sets the directories for the backup and the work to be backed up and creates the backup file using the “tar” command. The “tar” command creates a gzipped tar archive of the work directory and stores it in the specified backup file. Finally, the script prints a message indicating that the backup is complete.
```
#!/bin/bash

# Set the current date and time
date=$(date +%Y-%m-%d_%H-%M-%S)

# Set the directory where the backup will be stored
backup_dir="/home/ubuntu/Backup_dir"

# Set the directory that contains the work to be backed up
work_dir="/home/ubuntu/Directories/"

# Create the name of the backup file
backup_file="$backup_dir/work_backup_$date.tar.gz"

# Create the backup
tar -czvf $backup_file $work_dir

echo "Backup complete: $backup_file"
```
You can run this script by making it executable and then running it with “./backup.sh”

![2](https://user-images.githubusercontent.com/121767243/218311873-3b5a5a60-1cb8-46c6-a2e2-3577f655eedd.png)

### 3. About Cron and Crontab, to automate the backup Script
Cron is a daemon that runs in the background on Unix-like operating systems, including Linux and macOS. It allows you to schedule tasks to be automatically run in the background at a specified time or interval.

Crontab is a command that allows you to edit the cron table, which is a list of commands that are scheduled to run at specified times. Each line in the cron table represents a separate task, and consists of the following fields:

* Minute (0–59)
* Hour (0–23)
* Day of the month (1–31)
* Month (1–12)
* Day of the week (0–6, with 0 representing Sunday)
* Command to be run
### 4. About User Management
User management is the process of creating, modifying, and deleting user accounts on a computer system or network. It involves tasks such as setting passwords, permissions, and privileges for users, and is typically done using special tools provided by the operating system. User management is an important aspect of system administration, as it allows you to control who has access to the system and what actions they are allowed to perform.

### 5. Create 2 users and just display their Usernames

![5](https://user-images.githubusercontent.com/121767243/218311946-400b5ca2-1e3f-4c42-abe5-3c633dcc4ee2.png)

