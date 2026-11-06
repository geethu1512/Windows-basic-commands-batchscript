# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
~~~
mkdir my-folder
~~~
<img width="787" height="231" alt="image" src="https://github.com/user-attachments/assets/c8b381bd-7ced-4767-acb8-86e9273fd875" />

Remove the directory "my-folder"

## COMMAND AND OUTPUT
~~~
rmdir my-folder
~~~
<img width="441" height="55" alt="image" src="https://github.com/user-attachments/assets/637a5e0b-5d8f-4fa7-8bd6-f5fceb9b30d0" />


Create the file Rose.txt

## COMMAND AND OUTPUT
~~~
type nul > Rose.txt
~~~
<img width="497" height="32" alt="image" src="https://github.com/user-attachments/assets/6e5b7eba-8d51-4542-a199-56f85d61aff3" />



Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
~~~
echo Hello World > hello.txt
~~~
<img width="603" height="52" alt="image" src="https://github.com/user-attachments/assets/66e5236b-1704-4d0a-b5c0-a8154c231253" />


Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
~~~
copy hello.txt hello1.txt
~~~
<img width="1798" height="77" alt="image" src="https://github.com/user-attachments/assets/8fe59e21-870d-4f60-ab81-12c977035261" />



Remove the file hello1.txt

## COMMAND AND OUTPUT
~~~
del hello1.txt
~~~
<img width="447" height="62" alt="image" src="https://github.com/user-attachments/assets/fccf53ed-99b6-4f24-916b-4a40c0c5a9c4" />


List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
~~~
dir hello1.txt
~~~
<img width="462" height="183" alt="image" src="https://github.com/user-attachments/assets/7d0e2434-2a81-45fc-92b0-1427bf17bead" />


List out all the associated file extensions 

## COMMAND AND OUTPUT
~~~
assoc
~~~
<img width="497" height="1055" alt="image" src="https://github.com/user-attachments/assets/f52895ab-0889-4f9a-956c-c881451c02b5" />


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
~~~
fc hello.txt Rose.txt
~~~
<img width="485" height="502" alt="image" src="https://github.com/user-attachments/assets/f6071301-d25a-4335-b05d-b86d8fec083c" />


## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
## CODE
~~~
@echo off
set name=John
echo Hello, %name%
pause
~~~





## OUTPUT

<img width="421" height="102" alt="image" src="https://github.com/user-attachments/assets/9cddf6bd-a6aa-4d9f-8010-4c6199ae3be0" />


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

## CODE 
~~~
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE
:END
echo Thank you!
pause
~~~


## OUTPUT

<img width="642" height="240" alt="image" src="https://github.com/user-attachments/assets/0eb876e9-33fa-4a54-8fec-40388f887d25" />



Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
## CODE
~~~
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
~~~



## OUTPUT
<img width="1874" height="149" alt="image" src="https://github.com/user-attachments/assets/89619a40-a9aa-4fab-917f-480afc0aa3e3" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
### CODE 
~~~
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
~~~

## OUTPUT

<img width="1702" height="60" alt="image" src="https://github.com/user-attachments/assets/05a0f389-2cb4-48ca-851a-eedfb95ff519" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

## CODE
~~~
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU
:EXIT
echo Goodbye!
pause
exit
~~~
## OUTPUT 1

<img width="1919" height="212" alt="image" src="https://github.com/user-attachments/assets/7c32bad9-691d-48e3-b232-21e22a193f39" />
## OUTPUT 2
<img width="1919" height="231" alt="image" src="https://github.com/user-attachments/assets/4c0879db-4067-48db-95d8-bc9373f131a0" />
## OUTPUT 3
<img width="1919" height="213" alt="563141416-ba90f12a-26eb-4cac-8873-19f717750e05" src="https://github.com/user-attachments/assets/6f20df41-6a1a-4a3f-a07d-0ae39b7d5b19" />





# RESULT:
The commands/batch files are executed successfully.

