# Linux Shells – Simple Notes (TryHackMe Room)

---

## 🧠 Task 1 – What is a Shell?

- The **shell** is the middleman between the user and the operating system.
- Two main ways to interact:
  - **GUI** (Graphical User Interface)
  - **CLI** (Command Line Interface)
- The shell is the bigger concept. CLI is just one way to use a shell.

### Learning Goals
- Understand the Linux shell
- Learn basic commands
- Learn different types of shells
- Write simple shell scripts

---

## 💻 Task 2 – Basic Commands

### `pwd`
- Print Working Directory  
- Shows where you are.

### `ls`
- Lists files and folders in the current directory.

### `cd foldername`
- Change directory.
- `cd ..` → go back one folder.

### `cat filename`
- Shows content inside a file.

### `grep "word" filename`
- Searches for a word inside a file.

### `history`
- Shows previously executed commands in the current session.

### Default Shell
- Most Linux systems use **bash** (Bourne Again Shell) by default.

---

## 🐚 Task 3 – Types of Shells

### 1️⃣ bash
- Default shell in most Linux systems.
- Supports scripting.
- Has tab completion.
- Has command history.

### 2️⃣ fish (Friendly Interactive Shell)
- Beginner friendly.
- Syntax highlighting.
- Auto spell correction.
- More user-friendly features.

### 3️⃣ zsh (Z Shell)
- Very customizable.
- Supports plugins.
- Can be styled heavily.
- Often used in Kali Linux.

---

## TASK 4 – SHELL SCRIPTING NOTES


1) What is a Shell Script?

- A shell script is a file that contains multiple Linux commands.
- Instead of typing commands one by one, you write them in a file.
- File extension must be: .sh


---------------------------------
2) Shebang (VERY IMPORTANT)
---------------------------------

Every bash script must start with:

#!/bin/bash

- This is called the shebang.
- It tells Linux to use bash to run the script.
- It MUST be the first line.


---------------------------------
3) Making Script Executable
---------------------------------

Before running a script, give permission:

chmod +x scriptname.sh

- chmod = change mode
- +x = add execute permission

To run the script:

./scriptname.sh


---------------------------------
4) Variables
---------------------------------

Variables store values.

Example:

name="John"
echo $name

- name="John" → stores value.
- $name → accesses the stored value.

Taking user input:

echo "What's your name?"
read name
echo "Welcome $name"

- read name → saves user input into variable.


---------------------------------
5) Loops (Repetition)
---------------------------------

Used to repeat something multiple times.

Example:

for i in {1..10}
do
  echo $i
done

What happens:
- It runs 10 times.
- $i changes from 1 to 10.

Main idea:
Loop = Repeat task automatically.


---------------------------------
6) Conditional Statements (if / else)
---------------------------------

Used to make decisions.

Basic structure:

if [ condition ]
then
  commands
else
  commands
fi

Example:

if [ "$name" == "Stewart" ]
then
  echo "Access granted"
else
  echo "Access denied"
fi

Logic:
- If condition is true → run first block.
- If false → run else block.
- fi = ends the if statement.


---------------------------------
7) Comments
---------------------------------

Used to explain code.

# This is a comment

- Anything after # is ignored by the system.


---------------------------------
IMPORTANT CONCEPTS TO REMEMBER
---------------------------------

- #!/bin/bash → required at top
- chmod +x → make script executable
- ./script.sh → run script
- Variables store values
- $variable → access variable
- read → take input
- Loops → repeat tasks
- if/else → decision making
- # → comment

### Useful Shell Commands

Check your current shell:


## TASK 5 – LOCKER SCRIPT NOTES

1) What This Script Does

- It asks the user for:
  1. Username
  2. Company name
  3. PIN

- Then it checks if all the values are correct.
- If everything matches → Access granted.
- If anything is wrong → Access denied.


---------------------------------
2) Variables Used
---------------------------------

The script creates 3 empty variables:

username=""
companyname=""
pin=""

These will store the user’s input.


---------------------------------
3) Loop Used in Script
---------------------------------

The script uses a loop:

for i in {1..3}
do
   ...
done

- It runs 3 times.
- Each time it asks for different information.


How it works step by step:

First loop (i = 1):
- Asks for username
- Stores it in variable "username"

Second loop (i = 2):
- Asks for company name
- Stores it in "companyname"

Third loop (i = 3):
- Asks for PIN
- Stores it in "pin"


---------------------------------
4) Conditional Check (Authentication)
---------------------------------

After collecting input, it checks:

if username == "John"
AND companyname == "tryhackme"
AND pin == "7385"

If all are correct:
→ "Authentication successful"
→ Access to locker granted

If any value is wrong:
→ "Authentication denied"


---------------------------------
5) Correct Credentials
---------------------------------

Username: John
Company: tryhackme
PIN: 7385

PIN is the main answer question from the room.


---------------------------------
6) Concepts Used in This Script
---------------------------------

- Variables
- read (to take input)
- for loop (to repeat 3 times)
- if / else (to check conditions)
- Logical AND (&&) to require all conditions true

Important idea:
All three conditions must be TRUE.
If even one is wrong → access denied.

## TASK 6 – PRACTICAL EXERCISE NOTES

1) What This Task Was About

- We were given a script called: flag_hunt.sh
- The script was incomplete.
- Our job was to fix it so it can:
  → Search log files
  → Find a hidden flag
  → Print the file name where it finds the flag

This task tested:
- Variables
- Loops
- grep
- File permissions
- Root access


---------------------------------
2) Switching to Root User
---------------------------------

First step:

sudo su

Why?
- Because normal user might not have permission
- Log files in /var/log often require root access


---------------------------------
3) Understanding the Script
---------------------------------

The script started with:

#!/bin/bash

Then it defined variables:

directory=""
flag=""

We had to fill them in.


---------------------------------
4) Correct Values We Added
---------------------------------

Directory:

directory="/var/log"

Flag:

flag="THM-Flag01-script"

(Exact flag name may vary depending on room version,
but this is what the script was searching for.)

---------------------------------
5) The Loop Logic
---------------------------------

The script used:

for file in $directory/*.log
do
   ...
done

What this does:
- Looks inside /var/log
- Loops through every file ending with .log
- Checks them one by one


---------------------------------
6) grep Command Used
---------------------------------

Inside the loop:

grep -q "$flag" "$file"

What this means:
- Search for the flag
- -q means "quiet mode"
- It does NOT print output
- It only checks if it exists

If flag is found:
→ It prints file name
→ Says flag found

If not:
→ It keeps checking next file


---------------------------------
7) Important Detail

When writing:

for file in $directory/*.log

We must use:
$directory

NOT:
"/var/log"

Because we are referencing the variable.


---------------------------------
8) Running the Script

If permission error happens:

chmod +x flag_hunt.sh

Then run:

./flag_hunt.sh


---------------------------------
9) After Finding the File

Once script tells us which file contains the flag:

We use:

cat filename.log

That shows the message:

"The cat is sleeping under the table"

Final answer:
under the table


---------------------------------
10) Concepts Used in This Task
---------------------------------

- Root access (sudo su)
- Variables
- Variable referencing ($variable)
- Loops (for)
- Wildcards (*.log)
- grep -q
- chmod +x
- cat

```



```bash
echo $SHELL
