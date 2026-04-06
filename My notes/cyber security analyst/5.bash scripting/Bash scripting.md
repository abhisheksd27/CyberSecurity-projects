# 🚀 PHASE 1: BEGINNER (Foundation)

---

## 🧠 1. What is Bash?

**Bash (Bourne Again Shell)** is:

- A **command-line interpreter**
- A **scripting language**
- Used in Linux/macOS terminals

👉 Think of it like:

> “A bridge between you and the operating system”

---

## 📜 2. First Script

#!/bin/bash  
echo "Hello World"

### 🔍 Explanation:

- `#!` → tells OS which interpreter to use
- `echo` → prints output

---

## ⚙️ 3. Running Script

chmod +x script.sh   # make executable  
./script.sh          # run

### How it works:

- `chmod` gives execute permission
- `./` means “run from current directory”

---

## 📦 4. Variables

name="Abhishek"  
echo $name

### Rules:

- ❌ `name = Abhishek` (wrong)
- ✅ `name="Abhishek"`

---

## 📥 5. Input

echo "Enter name:"  
read name  
echo "Hello $name"

---

## 🧮 6. Arithmetic

a=10  
b=5  
sum=$((a + b))  
echo $sum

---

## 🔀 7. Conditions

num=10  
  
if [ $num -gt 5 ]  
then  
  echo "Greater"  
else  
  echo "Smaller"  
fi

---

## 🔁 8. Loops

### For Loop

for i in 1 2 3  
do  
  echo $i  
done

### While Loop

i=1  
while [ $i -le 3 ]  
do  
  echo $i  
  ((i++))  
done

---

# ⚡ PHASE 2: INTERMEDIATE

---

## 🔥 9. Functions

greet() {  
  echo "Hello $1"  
}  
greet Abhishek

👉 `$1` = first argument

---

## 📂 10. File Handling

if [ -f file.txt ]  
then  
  echo "File exists"  
fi

### Flags:

- `-f` → file
- `-d` → directory

---

## 📊 11. Command Line Arguments

echo $1  
echo $2

Run:

./script.sh hi hello

---

## 🔗 12. Pipes & Redirection

### Output to file

echo "Hello" > file.txt

### Append

echo "World" >> file.txt

### Pipe

cat file.txt | grep Hello

---

## 🧠 13. Exit Status

echo $?

- `0` → success
- `1` → failure

---

## 🔄 14. Command Substitution

today=$(date)  
echo $today

---

# 🚀 PHASE 3: ADVANCED

---

## 🧩 15. Arrays

arr=(one two three)  
  
echo ${arr[0]}  
echo ${arr[@]}

---

## 🎯 16. Case Statement

case $1 in  
  start) echo "Starting";;  
  stop) echo "Stopping";;  
  *) echo "Invalid";;  
esac

---

## 🧵 17. Processes & Background Jobs

sleep 5 &

- `&` → runs in background

Check jobs:

jobs

---

## 🔐 18. Permissions Deep Dive

chmod 755 script.sh

### Meaning:

- 7 → rwx
- 5 → r-x

---

## 🧪 19. Debugging

bash -x script.sh

👉 Shows step-by-step execution

---

## 🧠 20. Environment Variables

export MY_VAR="Hello"  
echo $MY_VAR

---

# 🔥 PHASE 4: EXPERT LEVEL

---

## ⚙️ 21. Process Substitution

diff <(ls dir1) <(ls dir2)

👉 Runs commands and compares output

---

## 🧬 22. Advanced File Parsing

while IFS=',' read name age  
do  
  echo "$name is $age"  
done < file.csv

---

## 🧠 23. Traps (Signal Handling)

trap "echo Exiting..." SIGINT

👉 Runs when Ctrl+C is pressed

---

## ⚡ 24. Cron Jobs (Automation)

crontab -e

Example:

0 2 * * * /path/script.sh

👉 Runs daily at 2 AM

---

## 🔍 25. Regex in Bash

if [[ $email =~ ^[a-z]+@[a-z]+\.[a-z]+$ ]]  
then  
  echo "Valid"  
fi

---

## 🧠 26. Subshells

(cd /tmp && ls)

👉 Runs in isolated environment

---

## 🧩 27. Advanced Expansion

echo ${name:-"Default"}

👉 If `name` is empty → use default

---

## ⚡ 28. Parallel Execution

cmd1 & cmd2 & wait

👉 Runs commands in parallel

---

# 🧠 INTERNAL WORKING (VERY IMPORTANT)

---

## How Bash Executes:

1. Read script
2. Tokenize input
3. Expand variables (`$var`)
4. Expand wildcards (`*.txt`)
5. Execute command
6. Return exit status

---

# 🧪 REAL-WORLD PROJECTS

---

## 🔥 1. System Monitor Script

#!/bin/bash  
  
echo "CPU:"  
top -bn1 | grep "Cpu"  
  
echo "Memory:"  
free -h  
  
echo "Disk:"  
df -h

---

## 🔥 2. Auto Backup Script

#!/bin/bash  
  
src="/home/user/data"  
dest="/home/user/backup"  
  
mkdir -p $dest  
cp -r $src/* $dest  
  
echo "Backup done"

---

## 🔥 3. Log Analyzer

#!/bin/bash  
  
grep "ERROR" logfile.txt | wc -l

---

# 🎯 BEST PRACTICES (VERY IMPORTANT)

---

✔ Use quotes:

echo "$name"

✔ Check errors:

if [ $? -ne 0 ]; then echo "Error"; fi

✔ Use `set` for safety:

set -e   # stop on error  
set -u   # undefined variable error

---

# 🚀 YOUR NEXT STEP (IMPORTANT)

Since you’re into **Dev + Cybersecurity**, you should:

### Build these:

1. 🔐 Password checker script
2. 📊 System monitor dashboard
3. 📂 File organizer
4. 🌐 Network scanner (basic)