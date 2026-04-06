## 🛠 Prep: Setting up workspace

bash

```
mkdir -p ~/recon && cd ~/recon
REPORT="recon_$(hostname)_$(date +%Y%m%d_%H%M%S).txt"
echo "=== Recon Report ===" > $REPORT
echo "Date: $(date)" >> $REPORT
```

- **mkdir -p ~/recon && cd ~/recon** Creates a directory `~/recon` and moves into it. `-p` ensures no error if it already exists. ➝ Keeps recon files organized in one place.
    
- **REPORT="recon_**(hostname)_**(date +%Y%m%d_%H%M%S).txt"** Defines a variable `REPORT` with a unique filename using hostname + timestamp. ➝ Prevents overwriting and helps track multiple engagements.
    
- **echo "=== Recon Report ===" > $REPORT** Creates the file and writes a header. `>` overwrites/creates. ➝ Starts the log file cleanly.
    
- **echo "Date: $(date)" >> $REPORT** Appends current date/time. `>>` means append. ➝ Useful for timeline tracking.
    

## 🖥 uname: OS & Kernel Info

bash

```
echo "\n--- OS Info ---" >> $REPORT
uname -a >> $REPORT
cat /etc/os-release >> $REPORT
cat /proc/version >> $REPORT
```

- **uname -a** → Kernel name, release, version, architecture, hostname.
    
- **cat /etc/os-release** → Distro name/version (Ubuntu, Debian, etc.).
    
- **cat /proc/version** → Kernel build info, compiler version. ➝ Helps identify exploit compatibility and OS family.
    

## 👤 whoami: Identity & Privileges

bash

```
echo "\n--- Identity ---" >> $REPORT
whoami >> $REPORT
id >> $REPORT
hostname >> $REPORT
cat /etc/hostname >> $REPORT
```

- **whoami** → Current username.
    
- **id** → UID, GID, groups.
    
- **hostname / cat /etc/hostname** → System hostname. ➝ Confirms if you’re root (`uid=0`) or in privileged groups (sudo, docker, disk).
    

## 🌍 env: Environment Variables

bash

```
echo "\n--- Environment ---" >> $REPORT
env >> $REPORT
echo $PATH >> $REPORT
echo $SHELL >> $REPORT
echo $HOME >> $REPORT
```

- **env** → Dumps all environment variables.
    
- **echo $PATH** → Shows search path for executables.
    
- **echo $SHELL / $HOME** → Current shell and home directory. ➝ Look for secrets (API keys, DB creds) and PATH hijack opportunities.
    

## 👥 /etc/passwd: User Enumeration

bash

```
echo "\n--- Users ---" >> $REPORT
cat /etc/passwd >> $REPORT
cat /etc/passwd | grep -v nologin | grep -v false
awk -F: '($3==0){print $1}' /etc/passwd
```

- **cat /etc/passwd** → Lists all accounts, home dirs, shells.
    
- **grep -v nologin/false** → Filters only login‑capable users.
    
- **awk -F: '($3==0){print $1}'** → Finds UID 0 accounts (root equivalents). ➝ Detects backdoors, service accounts, and potential escalation paths.
    

## 📜 Script: Automating Recon

bash

```
nano fingerprint.sh
```

Contents:

bash

```
#!/bin/bash
REPORT="recon_$(hostname)_$(date +%Y%m%d_%H%M%S).txt"
echo "=== System Fingerprint Report ===" > $REPORT
echo "Date: $(date)" >> $REPORT

echo "\n--- OS Info ---" >> $REPORT
uname -a >> $REPORT
cat /etc/os-release >> $REPORT

echo "\n--- Identity ---" >> $REPORT
whoami >> $REPORT && id >> $REPORT
hostname >> $REPORT

echo "\n--- Environment ---" >> $REPORT
env >> $REPORT

echo "\n--- Users (login shells only) ---" >> $REPORT
cat /etc/passwd | grep -v nologin | grep -v false >> $REPORT

echo "\n--- UID 0 accounts ---" >> $REPORT
awk -F: '($3==0){print $1}' /etc/passwd >> $REPORT

echo "\n[+] Done. Report saved to: $REPORT"
```

Run it:

bash

```
chmod +x fingerprint.sh
./fingerprint.sh
cat $REPORT
```

- **chmod +x** → Makes script executable.
    
- **./fingerprint.sh** → Runs the script.
    
- **cat $REPORT** → Reads the generated report. ➝ Automates recon, saves time, ensures consistent logging.
    

✅ **Why this matters overall:** This workflow mimics how real pentesters document findings. Every command logs directly into a timestamped report, ensuring reproducibility and evidence collection. It’s the foundation of post‑exploitation recon and privilege escalation planning.