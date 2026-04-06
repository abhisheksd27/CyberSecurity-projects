# 🛠 Workspace Setup

### Commands

bash

```
mkdir -p ~/recon && cd ~/recon
REPORT="recon_$(hostname)_$(date +%Y%m%d_%H%M%S).txt"
echo "=== Recon Report ===" > $REPORT
echo "Date: $(date)" >> $REPORT
```

### Explanation

- **mkdir -p ~/recon && cd ~/recon**
    
    - Creates a dedicated directory `~/recon`.
        
    - `-p` avoids errors if it already exists.
        
    - Keeps all recon files organized in one place.
        
- **REPORT="recon_**(hostname)_**(date +%Y%m%d_%H%M%S).txt"**
    
    - Defines a variable `REPORT` with a unique filename.
        
    - Combines hostname + timestamp → prevents overwriting and helps track multiple engagements.
        
- **echo "=== Recon Report ===" > $REPORT**
    
    - Creates the file and writes a header.
        
    - `>` overwrites/creates a new file.
        
- **echo "Date: $(date)" >> $REPORT**
    
    - Appends current date/time.
        
    - `>>` means append.
        
    - Useful for timeline tracking and evidence collection.
        

# 🖥 OS & Kernel Info

### Commands

bash

```
echo "\n--- OS Info ---" >> $REPORT
uname -a >> $REPORT
cat /etc/os-release >> $REPORT
cat /proc/version >> $REPORT
```

### Explanation

- **uname -a**
    
    - Kernel name, release, version, architecture, hostname.
        
- **cat /etc/os-release**
    
    - Distro name/version (Ubuntu, Debian, CentOS, etc.).
        
- **cat /proc/version**
    
    - Kernel build info, compiler version.
        
- **Why important?**
    
    - Identifies OS family and kernel version.
        
    - Helps check exploit compatibility (kernel privilege escalation, distro‑specific weaknesses).
        

# 👤 Identity & Privileges

### Commands

bash

```
echo "\n--- Identity ---" >> $REPORT
whoami >> $REPORT
id >> $REPORT
hostname >> $REPORT
cat /etc/hostname >> $REPORT
```

### Explanation

- **whoami**
    
    - Current username.
        
- **id**
    
    - UID, GID, groups.
        
- **hostname / cat /etc/hostname**
    
    - System hostname.
        
- **Why important?**
    
    - Confirms if you’re root (`uid=0`) or in privileged groups (sudo, docker, disk).
        
    - Group memberships can reveal escalation paths (e.g., docker group → root via container escape).
        

# 🌍 Environment Variables

### Commands

bash

```
echo "\n--- Environment ---" >> $REPORT
env >> $REPORT
echo $PATH >> $REPORT
echo $SHELL >> $REPORT
echo $HOME >> $REPORT
```

### Explanation

- **env**
    
    - Dumps all environment variables.
        
- **echo $PATH**
    
    - Shows search path for executables.
        
- **echo $SHELL / $HOME**
    
    - Current shell and home directory.
        
- **Why important?**
    
    - Environment variables may contain secrets (API keys, DB creds).
        
    - PATH hijacking opportunities (placing malicious binaries earlier in PATH).
        
    - Knowing shell type helps craft payloads/scripts correctly.
        

# 👥 User Enumeration

### Commands

bash

```
echo "\n--- Users ---" >> $REPORT
cat /etc/passwd >> $REPORT
cat /etc/passwd | grep -v nologin | grep -v false
awk -F: '($3==0){print $1}' /etc/passwd
```

### Explanation

- **cat /etc/passwd**
    
    - Lists all accounts, home dirs, shells.
        
- **grep -v nologin/false**
    
    - Filters only login‑capable users.
        
- **awk -F: '($3==0){print $1}'**
    
    - Finds UID 0 accounts (root equivalents).
        
- **Why important?**
    
    - Detects backdoors, service accounts, and potential escalation paths.
        
    - Identifies multiple root‑level accounts (security red flag).
        
    - Helps map attack surface (users with real shells vs. system accounts).
        

# 📜 Automating Recon with Script

### Script

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

### Run

bash

```
chmod +x fingerprint.sh
./fingerprint.sh
cat $REPORT
```

### Explanation

- **chmod +x**
    
    - Makes script executable.
        
- **./fingerprint.sh**
    
    - Runs the script.
        
- **cat $REPORT**
    
    - Reads the generated report.
        
- **Why important?**
    
    - Automates recon, saves time, ensures consistent logging.
        
    - Timestamped reports → reproducibility and evidence collection.
        
    - Forms the baseline for privilege escalation planning.
        

# ✅ Why This Matters Overall

- **Pentester workflow:** Every command logs directly into a timestamped report.
    
- **Reproducibility:** Ensures findings can be reviewed later or presented as evidence.
    
- **Privilege escalation prep:** Identifies kernel, users, groups, environment variables, and potential misconfigurations.
    
- **Efficiency:** Script automation avoids human error and speeds up recon.