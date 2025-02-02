# Day 04 — Basic Linux Shell Scripting
## Tasks
### 1. What is Kernel
The kernel is a computer program that is the core of a computer’s operating system, with complete control over everything in the system.

### 2. What is Shell
A shell is special user program which provide an interface to user to use operating system services. Shell accept human readable commands from user and convert them into something which kernel can understand. It is a command language interpreter that execute commands read from input devices such as keyboards or from files. The shell gets started when the user logs in or start the terminal.

### 3. What is Linux Shell Scripting?
A shell script is a computer program designed to be run by a linux shell, a command-line interpreter. The various dialects of shell scripts are considered to be scripting languages. Typical operations performed by shell scripts include file manipulation, program execution, and printing text.

### 4. Explain in your own words and examples, what is Shell Scripting for DevOps.
Shell scripting is a way to automate tasks in a Unix-based operating system, such as Linux or macOS. It involves writing a series of commands in a script file, which can then be executed all at once, rather than running each command separately.

### 5. What is #!/bin/bash? can we write #!/bin/sh as well?
The line “#!/bin/bash” is called a shebang, and it specifies the path to the interpreter for the script. In this case, the script will be interpreted by the bash shell. Yes, you can also use “#!/bin/sh” to specify the “sh” shell as the interpreter.

### 6. Write a Shell Script which prints “I will complete #90Days0ofDevOps challenge”
This script has a single line of code, which uses the “echo” command to print a message to the terminal. The message is enclosed in quotation marks, so it is treated as a single string by the shell.
```
#!/bin/bash

echo "I will complete #90DaysOofDevOps challenge"
```
To run the script, you can use the following command: “./script.sh”
Here is the output when the script is run:

![6](https://user-images.githubusercontent.com/121767243/218311442-69b30e9f-4125-4b91-b049-3778097ba60e.png)

### 7. Write a Shell Script to take user input, input from arguments and print the variables.
The script begins by displaying a message asking the user to enter their name, and then uses the “read” command to get the user’s input and store it in the “name” variable. Then, the script gets the first argument passed to it (in this case, “Manager” ) and stores it in the “position” variable. Finally, the script prints both variables using the “echo” command.
```
#!/bin/bash

# Get the user's name as input
echo "Enter your name: "
read name

# Get the first argument passed to the script
position=$1

# Print the variables
echo "Name: $name"
echo "Position: $position"
```
To run the script and pass an argument, you can use the following command: “./newscript.sh Manager”

Here is the output if you enter “KumarWaghmare” as the name:

![7](https://user-images.githubusercontent.com/121767243/218311460-b355e70d-dc95-4e51-adbf-1fe236e0d65b.png)

### 8. Write an Example of If else in Shell Scripting by comparing 2 numbers
When the script is run, it gets the two numbers to compare as arguments and stores them in the variables “num1" and “num2". Then, it uses an “if” statement to compare the values of these variables. If “num1” is greater than “num2”, the first block of code is executed and the message “10 is greater than 5” is printed to the terminal. If “num1” is not greater than “num2”, the second block of code is executed and the message “5 is less than or equal to 10” is printed to the terminal.
```
#!/bin/bash

# Get the two numbers to compare as arguments
num1=$1
num2=$2

# Compare the numbers
if [ $num1 -gt $num2 ]
then
  echo "$num1 is greater than $num2"
else
  echo "$num1 is less than or equal to $num2"
fi
```
To run the script and compare the numbers “5" and “10" , you can use the following command: “./compare.sh 5 10” and “./compare.sh 10 5”

Here is the output when the script is run:

![8](https://user-images.githubusercontent.com/121767243/218311476-1ec9dc1c-1149-4c42-9880-a2d52df20598.png)
