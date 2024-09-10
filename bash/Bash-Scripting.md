## Comments

 > In bash scripts, comments are used to add explanatory notes or disable certain lines of code.
 > Task 1: Create a bash script with comments explaining what the script does.

## Echo

 > The echo command is used to display messages on the terminal.
 > Task 2: Create a bash script that uses echo to print a message of your choice

## Variables

 > Variables in bash are used to store data and can be referenced by their name.
 > Task 3: Create a bash script that declare variables and assign values to them.

## Using Variables

 > Use the created variables to perform simple task
 > Task 4: Create a bash script that takes two variables (numbers) as input and prints their sum using those variables.

## Using Built-in Variables

 > Bash provides several built-in variables that hold useful information.
 > Task 5: Create a bash script that utilizes at least three different built-in variables to display relevant information.

## Wildcards

 > Wildcards are special characters used to perform pattern matching when working with files.
 > Task 6: Create a bash script that utilizes wildcards to list all the files with a specific extension in  a directory.

   >> 
   ```
   #!/bin/bash
   # Task 1: This script updates the system packages and lists all files in the current directory

   # Update system packages
   sudo apt update && sudo apt upgrade -y # Update and upgrade with yes to prompts

   # List all files in the current directory
   ls -l

   # Task 2: Print a message indicating completion
   echo "System updated and directory listing complete"

   # Task 3: Assign values to two variables
   a=4
   b=5
   # Task 4: Sum and print the two variables
   c=$((a+b))
   echo "The sum of two values $a and $b is $c"

   # Task 5: To display relevant information using built in variables
   # Display the username
   echo "Username: $USER"

   # Display the hostname
   echo "Hostname: $HOSTNAME"

   # Display the current working directory
   echo "Current Directory: $PWD"

   # Task 6: List all files with specific extension
   ls *.md
   ```

   