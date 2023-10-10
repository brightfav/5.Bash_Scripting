# Shell Scripting

## what is Shell Scripting?

A shell script is a text file that contains a sequence of commands for a UNIX-based operating system.

## When is Shell Scripting needed?

Using a shell script is most useful for repetitive tasks that may be time consuming to execute by typing one line at a time.

## Shell Scripting Syntax Element

**1.** **Variables:**

Shell Variable is used in shell scripts for many functionalities like storing data and information, taking input from users, printing values that are stored. They are also used for storing data temporarily and storing output of commands

example `name="bright"`

![define variable](<img/2 define a variable.png>)

**2.** **Control Flow**

When it comes to bash scripting, flow control is all about making sure that your commands are executed in the right order. This can be achieved using logic.

example in the command below in an empty script file



`#!/bin/bash`

`# Example script to check if a number is positive, negative, or zero`

`read -p "Enter a number: " num`

`if [ $num -gt 0 ]; then
    echo "The number is positive."
elif [ $num -lt 0 ]; then
    echo "The number is negative."
else
    echo "The number is zero."
fi`

![typed code of control flow](<img/3 control flow.png>)

the above control flow command prompts you to to type a number and prints a statement stating the number is positive or negative as seen below.

![executed control flow script](<img/6 executed script.png>)


example 2 - iterating through a list using a `for loop` in the command below

`#!/bin/bash`

`# Example script to print numbers from 1 to 5 using a for loop`

`for (( i=1; i<=5; i++ ))
do
    echo $i
done`

![edited script](<img/7 follow up script.png>)

after runnig the script i gave the result below

![result of script](<img/8 result of follow up script.png>)



**3.** **Command Substitution**

Command substitution is a mechanism that is followed by programmers in a shell script. In this mechanism, the output of a command replaces the command itself.
In simple words, the output of a UNIX command is bundled and then used as a command.

using backtit for command substitution
> current_date=`date +%Y-%m-%d`

using `$()` syntax for command substitution
> current_date=$(date +%Y-%m-%d)


**4.** **Input and Output**

**Example** accept user input
> echo "Enter your name:"
read name

**Example** output text to the terminal
> echo "Hello World"

**Example** out the result of a command into a file
> echo "hello world" > index.txt

**Example** Pass the content of a file as input to a command
> grep "pattern" < input.txt

**Example** pass the result of a command as input to another command
> echo "hello world" | grep "pattern"

**5.** **Functions**
>  It is a sequence of commands that do a single job. Typically, a function is used for an operation that you tend to do frequently in a shell script. Before you can call a function in a shell script, you must define it in the script.

**Example**

`#!/bin/bash

`# Define a function to greet the user
greet() {
    echo "Hello, $1! Nice to meet you."
}`

`# Call the greet function and pass the name as an argument
greet "John"`


## Writing My First Script

### Step 1

i opened my terminal and created a folder called `shell-scripting` uaing the code below 

`mkdir shell-scripting`


### Step 2

next i created a script file named `user-input.sh` using the command below

`touch user-input.sh`

![create directory](<img 2/1 create directory and script file.png>)

### Step 3

i edit with `vim` command editor the `user-input.sh` file using the command below

`vim user-input.sh`

afterwards i typed the script code below

`#!/bin/bash`

`# Prompt the user for their name
echo "Enter your name:"
read name`

`# Display a greeting with the entered name`
`echo "Hello, $name! Nice to meet you."`

![edit user-input sile](<img 2/2 first script code.png>)

### Step 4 save file

I saved my file

### step 5 I run the bash script

to do this first i must make my script file executable. To make this possible i use the command below

`chmod +x user-input.sh`

![make file executable](<img 2/3 make file executable.png>)

### Step 6 Run the script file

To run the script file i use the command below

`./user-input.sh`

![script run](<img 2/4 result of first script.png>)

## Directory Manipulation and Navigation

This script will carry out the following tasks

1. display the current directory

2. Create a new directory called "my_directory"

3. change into the "my_directory" directory

4. create two files inside it

5. list the files in the directory

6. move back one level up

7. remove "my_directory" directory and all its contents

8. list all the files in the current directory

### Making of script to carry the above task

1. i created a file named `navigating-linux-filesystem.sh` usin the command below

`touch navigating-linux-filesystem.sh `

![script file navigation](<img 2/5 create file navigating linux file system.png>)

2. i opened and edited the script file using the command below

`vim navigating-linux-filesystem.sh`

after which i typed the code below into the script file

`#!/bin/bash`

`# Display current directory
echo "Current directory: $PWD"`

`# Create a new directory
echo "Creating a new directory..."
mkdir my_directory
echo "New directory created."`

`# Change to the new directory
echo "Changing to the new directory..."
cd my_directory
echo "Current directory: $PWD"`

`# Create some files
echo "Creating files..."
touch file1.txt
touch file2.txt
echo "Files created."`

`# List the files in the current directory
echo "Files in the current directory:"
ls`

`# Move one level up
echo "Moving one level up..."
cd ..
echo "Current directory: $PWD"`

`# Remove the new directory and its contents
echo "Removing the new directory..."
rm -rf my_directory
echo "Directory removed."`

`# List the files in the current directory again
echo "Files in the current directory:"
ls`

![typed code into script file](<img 2/6 code typed into file.png>)

3. I made the file executable using the command below

`chmod +x navigating-linux-filesystem.sh`

![make file executable](<img 2/7 make the file executable.png>)

4. I run my script using the code below

`./navigating-linux-filesystem.sh`

![result of script file](<img 2/7 result of file navigating liniux file system script.png>)


### File Operations and Sorting

I will be writing a script that focuses on file operations and sorting

this will be done in the following steps

1. Three files will be created namely file1.txt, file2.txt and file3.txt

2. Display files in their current order

3. Sort them alphabetically 

4. Save the sorted files in sorted_files_txt

5. Display the sorted files

6. Remove the original files

7. Rename the sorted_files_sorted_alphabetically.txt

8. display the content of the final sorted file

### Making of script to carry the above task 

1. i create a script file called `sorting.sh` using the command below

`touch sorting.sh`

![create script file touch](<img 2/9 create script file sorting.png>)

2. i open and typed in a script code using the command below

`vim sorting.sh`

i typed the code below into the script file

`#!/bin/bash`

`# Create three files
echo "Creating files..."
echo "This is file3." > file3.txt
echo "This is file1." > file1.txt
echo "This is file2." > file2.txt
echo "Files created."`

`# Display the files in their current order
echo "Files in their current order:"
ls`

`# Sort the files alphabetically
echo "Sorting files alphabetically..."
ls | sort > sorted_files.txt
echo "Files sorted."`

`# Display the sorted files
echo "Sorted files:"
cat sorted_files.txt`

`# Remove the original files
echo "Removing original files..."
rm file1.txt file2.txt file3.txt
echo "Original files removed."`

`# Rename the sorted file to a more descriptive name
echo "Renaming sorted file..."
mv sorted_files.txt sorted_files_sorted_alphabetically.txt
echo "File renamed."`

`# Display the final sorted file
echo "Final sorted file:"
cat sorted_files_sorted_alphabetically.txt`

![sorting script code](<img 2/10 sorting script file code typed.png>)

3. make the script file executable using the code below

`chmod +x sorting.sh`

![make script file executable](<img 2/11 make sorting script file executable.png>)

4. Run my script file using the code below

`./sorting.sh`

![sorting script executed](<img 2/12 sorting script executed.png>)


### Working with Numbers and Calculations

I will be writing a script will do the following

1. define two variable num1 and num2 with numeric values

2. Perform basic arithmetic operations (addition,subtraction,multiplication,division and modulus)

3. Displays the result

4. It will also perform complex calculations such as raising num1 to the power of 2

5. calculating the square root of num2

6. display the results as well

### Making of script to carry the above task 

1. i created a file called `calculations,sh` using the command below

`touch calculations.sh`

![create script calculations file](<img 2/13 create script calculations.png>)

2. to edit the script file i used the command below

`vim calculations.sh`

3. i typed the code below

`#!/bin/bash`

`# Define two variables with numeric values
num1=10
num2=5`

`# Perform basic arithmetic operations
sum=$((num1 + num2))
difference=$((num1 - num2))
product=$((num1 * num2))
quotient=$((num1 / num2))
remainder=$((num1 % num2))`

`# Display the results
echo "Number 1: $num1"
echo "Number 2: $num2"
echo "Sum: $sum"
echo "Difference: $difference"
echo "Product: $product"
echo "Quotient: $quotient"
echo "Remainder: $remainder"`

`# Perform some more complex calculations
power_of_2=$((num1 ** 2))
square_root=$(awk "BEGIN{ sqrt=$num2; print sqrt }")`

`# Display the results
echo "Number 1 raised to the power of 2: $power_of_2"
echo "Square root of number 2: $square_root"
`

![edit calculations script file](<img 2/14 type code into calculations script file.png>)


4. i made the script file executable using the code below

`chmod +x calculations.sh`

![make the file executable](<img 2/15 make calculations script file executable.png>)

5. i run the script using the command below

`./calculations.sh`

![run the calculations script](<img 2/16 executed calculations script file.png>)


### File Backup and Timestamping

I will be writing a script will do the following

1. Define the source directory and backup directory paths

2. create a timestamp using the current date and time 

3. create a backup directory with the timestamp appended to its name.

4. it then copies all files from the sourch directory to the backup directory using the `cp` command using the `-r` option for recursive copying 

5. it displays a message indicating the completion of the backup process and shows the path of the backup directory with the timestamp.

### Making of script to carry the above task 

1. i created a file called `backup.sh` using the command below

`touch backup.sh`

![create backup script file](<img 2/17 create backup script file.png>)

2. i opened the backup file using the vim editor

![opened backup script file](<img 2/18 open backup script file using vim command editor.png>)

3. I typed the code below into my script file

`#!/bin/bash`

`# Define the source directory and backup directory
source_dir="/path/to/source_directory"
backup_dir="/path/to/backup_directory"`

`# Create a timestamp with the current date and time
timestamp=$(date +"%Y%m%d%H%M%S")`

`# Create a backup directory with the timestamp
backup_dir_with_timestamp="$backup_dir/backup_$timestamp"`

`# Create the backup directory
mkdir -p "$backup_dir_with_timestamp"`

`# Copy all files from the source directory to the backup directory
cp -r "$source_dir"/* "$backup_dir_with_timestamp"`

`# Display a message indicating the backup process is complete
echo "Backup completed. Files copied to: $backup_dir_with_timestamp"`

![code typed into editor](<img 2/19 type code into backup script file.png>)

4. i make the script file executable using the command below

`chmod +x backup.sh`

![make backup file executable](<img 2/20 make backup script file executable.png>)

5. Run the script file using the command below

`./backup.sh`

![run script ](<img 2/21 executed backup script file.png>)

Thank You
