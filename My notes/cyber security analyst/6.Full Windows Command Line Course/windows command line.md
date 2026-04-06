# 🧠 1. What is Windows Command Line?

The Windows command line is mainly:

- **Command Prompt (CMD)** → traditional shell
- **PowerShell** → modern, powerful scripting shell

👉 In this guide, we focus on **CMD (Command Prompt)** first.

---

# ⚙️ 2. How CMD Works Internally

When you type a command:

dir

### Internally:

1. CMD reads input
2. Parses command + arguments
3. Checks:
    - Internal command? (like `dir`)
    - External program? (like `.exe`)
4. Executes via Windows API
5. Returns output + exit code

---

# 📂 3. Basic Navigation Commands

## 📁 Show files (like `ls` in Linux)

dir

👉 Lists files & folders

---

## 📁 Change directory

cd Documents

Go back:

cd ..

Go root:

cd \

---

## 📍 Show current path

cd

---

# 📄 4. File & Folder Operations

---

## Create folder

mkdir test

---

## Delete folder

rmdir test

👉 Force delete:

rmdir /s /q test

---

## Create file

echo Hello > file.txt

---

## View file

type file.txt

---

## Delete file

del file.txt

---

# 🔁 5. Copy & Move

---

## Copy

copy file.txt backup.txt

---

## Move

move file.txt folder\

---

# 🧮 6. Variables in CMD

CMD uses **environment variables**

---

## Set variable

set name=Abhishek

Use it:

echo %name%

---

## System variables

echo %USERNAME%  
echo %PATH%  
echo %TEMP%

---

# 📥 7. User Input

set /p name=Enter your name:  
echo Hello %name%

---

# 🔀 8. Conditional Statements

@echo off  
set num=10  
  
if %num% GTR 5 (  
  echo Greater  
) else (  
  echo Smaller  
)

---

## Operators:

- `EQU` → equal
- `NEQ` → not equal
- `GTR` → greater
- `LSS` → less

---

# 🔁 9. Loops

---

## For loop

for %%i in (1 2 3) do echo %%i

---

## Loop through files

for %%f in (*.txt) do echo %%f

---

# 📦 10. Batch Scripts (.bat)

CMD scripts are called **batch files**

---

## Example:

@echo off  
echo Hello World  
pause

### How it works:

- `@echo off` → hides commands
- `pause` → waits for key press

---

# 🔗 11. Pipes & Redirection

---

## Redirect output

echo Hello > file.txt

Append:

echo World >> file.txt

---

## Pipe

dir | find "txt"

👉 Filters output

---

# 📊 12. Exit Codes

echo %ERRORLEVEL%

- `0` → success
- `1` → error

---

# ⚡ 13. Advanced Commands

---

## Task management

tasklist

Kill process:

taskkill /PID 1234 /F

---

## Network commands

ipconfig  
ping google.com  
netstat -an

---

# 🔐 14. Permissions (Basic)

icacls file.txt

Modify:

icacls file.txt /grant username:F

---

# 🧠 15. Advanced Batch Concepts

---

## Functions (using labels)

@echo off  
call :greet  
exit /b  
  
:greet  
echo Hello Abhishek  
exit /b

---

## Arrays (simulation)

CMD has no real arrays, but:

set arr[0]=one  
set arr[1]=two  
echo %arr[0]%

---

## String operations

set str=HelloWorld  
echo %str:~0,5%

👉 Output: Hello

---

# 🧪 16. Debugging

echo on

👉 Shows command execution

---

# ⚙️ 17. System Info Commands

systeminfo  
whoami  
hostname

---

# 🔥 18. Real-World Scripts

---

## 📊 System Monitor

@echo off  
echo CPU Info:  
wmic cpu get loadpercentage  
  
echo Memory:  
wmic OS get FreePhysicalMemory  
  
echo Disk:  
wmic logicaldisk get size,freespace,caption  
pause

---

## 📂 Backup Script

@echo off  
set source=C:\data  
set dest=C:\backup  
  
xcopy %source% %dest% /E /I /Y  
  
echo Backup completed  
pause

---

## 🌐 Network Checker

@echo off  
ping google.com  
if %ERRORLEVEL% EQU 0 (  
  echo Internet is working  
) else (  
  echo No connection  
)

---

# ⚡ 19. CMD vs PowerShell (IMPORTANT)

|Feature|CMD|PowerShell|
|---|---|---|
|Type|Basic|Advanced|
|Scripting|Limited|Powerful|
|Objects|❌|✅|
|Modern|❌|✅|

---

# 🚀 20. PowerShell Preview (IMPORTANT)

Example:

Get-Process

$name = "Abhishek"  
Write-Output $name

👉 PowerShell uses **objects**, not just text

---

# 🧠 INTERNAL DIFFERENCE (VERY IMPORTANT)

---

### CMD:

- Works with **text**
- Simple parsing
- Limited scripting

### PowerShell:

- Works with **objects**
- .NET based
- Advanced automation

---

# 🎯 BEST PRACTICES

✔ Always use quotes:

set name="Abhishek"

✔ Use `@echo off` in scripts  
✔ Check error levels  
✔ Avoid hardcoding paths

---

# 🔥 NEXT LEVEL (FOR YOU)

Since you're into **development + cybersecurity**, build:

### 💻 Projects:

1. File organizer script
2. Network scanner
3. Log analyzer
4. Auto backup system