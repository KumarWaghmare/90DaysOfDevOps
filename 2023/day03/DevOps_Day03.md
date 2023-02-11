# Day 03 — Basic Linux Commands
## Tasks
### What is the Linux command to :

### 1.To view what’s written in a file.

To view the contents of a file, you can use the “cat” command. This command stands for "concatenate" and it prints the contents of the specified file to the terminal. Here’s an example of how to use “cat” to view the contents of a file called “file.txt” : “cat file.txt”

![1 (1)](https://user-images.githubusercontent.com/121767243/218267437-5b3ad4ee-c70c-4601-b7bd-b591f3de9aff.png)

### 2.To change the access permissions of files.

To change the access permissions of a file, you can use the “chmod” command. This command stands for "change mode," and it allows you to specify which users or groups can read, write, or execute a particular file.

Here is a example of how to use “chmod” to change the access permissions of a file called “file.txt” :

To give read, write, and execute permissions to the owner of the file and read and execute permissions to everyone else, you can use the following command: “chmod 755 file.txt”

![2](https://user-images.githubusercontent.com/121767243/218267454-f2c6ed71-9029-423e-b2a4-b8d70008378c.png)

### 3.To check which commands you have run till now.

To view a history of previously run commands, you can use the “history” command. This command displays a list of all the commands that have been run in the current session. By default, the “history” command will show the most recent commands first, with the most recent command at the bottom of the list. Here's an example of how to use “history” :

![3](https://user-images.githubusercontent.com/121767243/218267465-09002d92-6a39-4483-87e4-fb2357aeabb7.png)

### 4.To remove a directory/ Folder.

To remove a directory, you can use the “rm” command with the “-r” flag to recursively delete the directory and all its contents. The “rm” command stands for "remove," and it is used to delete files or directories. The “-r” flag stands for "recursive," and it tells the “rm” command to delete the directory and all its contents, including any subdirectories and files.

Here’s an example of how to use “rm” to delete a directory called “my_directory” : “rm -r my_directory/”

![4](https://user-images.githubusercontent.com/121767243/218267477-498d9481-c08a-44d7-899a-dce1afc9fe74.png)

### 5.To create a fruits.txt file and to view the content.

To create a file called “fruits.txt” and view its contents, you can use the “touch” and “cat” commands. The “touch” command is used to create a new, empty file, and the “cat” command is used to view the contents of a file. Here's an example of how to create a file called “fruits.txt” and view its contents:

![5](https://user-images.githubusercontent.com/121767243/218267500-5458a7b8-35cd-4bea-a4f4-64f6eb1d5d43.png)

### 6.Add content in devops.txt (One in each line) — Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.

To add content to “devops.txt” , you can use the “echo” command followed by the desired text and the “>>” operator to append the text to the file. The “echo” command is used to print text to the terminal, and the “>>” operator is used to append the output of a command to a file. You can also use “ vim and nano”

Here is a example of how to use “echo” to add content : “echo “text” >> devops.txt”

![6](https://user-images.githubusercontent.com/121767243/218267512-078dc4fd-7aad-4228-a391-cbab8e568544.png)

### 7.To Show only top three fruits from the file.

To show only the top three fruits from the file, you can use the “head” command followed by the “-n” flag to specify the number of lines to display. For example: “head -n 3 fruits.txt”

![7](https://user-images.githubusercontent.com/121767243/218267520-e4f30075-98bb-404e-b049-b6584c9637ee.png)

### 8.To Show only bottom three fruits from the file.

To show only the bottom three fruits from the file, you can use the “tail” command followed by the “-n” flag to specify the number of lines to display. For example: “tail -n 3 fruits.txt”

![8](https://user-images.githubusercontent.com/121767243/218267527-95377e4e-8d68-4b2f-8d83-f85bcb61efa7.png)

### 9.To create another file colour.txt and to view the content.

To create a file called “colour.txt” and view its contents, you can use the “touch” and “cat” commands. For example:

![9](https://user-images.githubusercontent.com/121767243/218267536-a6d48f47-7382-401f-93d3-5c2401260205.png)

### 10.Add content in colors.txt (One in each line) — Red, Pink, White, Black, Blue, Orange, Purple, Grey.

To add content to colors.txt, you can use the “echo” command followed by the desired text and the “>>” operator to append the text to the file. For example:

![10](https://user-images.githubusercontent.com/121767243/218267547-1a668dcf-ddf7-4adc-8aa6-215df24c6e67.png)

### 11.To find the difference between fruits.txt and colors.txt file.

To find the difference between two files, you can use the “diff” command. This command compares the contents of the two files and displays any differences. The syntax for using “diff” is as follows: “diff file1 file2”

![11](https://user-images.githubusercontent.com/121767243/218267568-4b515723-fbbe-46a5-8c2e-1118c9b148a1.png)
