## 🐧 What is Linux?

- **Operating System (OS)** → manages hardware + software communication.
    
- **Open-source** → free to use, modify, and distribute.
    
- **Distributions (distros)** → customized versions (Ubuntu, Debian, Fedora, Parrot OS, etc.).
    
- **Widely used** → servers, desktops, embedded systems, Android smartphones.
    

## 📜 History

- **1970** → Unix created by Ken Thompson & Dennis Ritchie.
    
- **1977** → BSD released, but legal issues limited growth.
    
- **1983** → Richard Stallman starts GNU project → GPL license.
    
- **1991** → Linus Torvalds creates Linux kernel.
    
- **Today** → 23M+ lines of code, 600+ distros.
    

## 🌱 Philosophy (Linux Culture)

1. **Everything is a file** → devices, processes, connections.
    
2. **Small, single-purpose programs** → each tool does one job well.
    
3. **Chain programs together** → combine tools for complex tasks.
    
4. **Avoid captive interfaces** → focus on shell/terminal.
    
5. **Configuration in text files** → e.g., `/etc/passwd`.
    

## ⚙️ Components

- **Bootloader** → starts OS (e.g., GRUB).
    
- **Kernel** → core, manages hardware resources.
    
- **Daemons** → background services (printing, scheduling).
    
- **Shell** → CLI interface (Bash, Zsh, Fish).
    
- **Graphics Server** → X-server for GUI.
    
- **Window Manager** → GUI environments (GNOME, KDE, Cinnamon).
    
- **Utilities** → apps/tools for user tasks.
    

## 🏗️ Linux Architecture (Layered View)

Code

```
Hardware → Kernel → Shell → System Utilities → Applications
```

- **Hardware** → CPU, RAM, disk.
    
- **Kernel** → controls hardware, allocates resources.
    
- **Shell** → user interface (commands).
    
- **System Utilities** → OS functions exposed to user.
    
- **Applications** → browsers, editors, etc.
    

## 📂 File System Hierarchy (Tree Structure)

Code

```
/
├── bin   → essential binaries
├── boot  → bootloader + kernel
├── dev   → device files
├── etc   → configuration files
├── home  → user directories
├── lib   → shared libraries
├── media → external devices
├── mnt   → temporary mounts
├── opt   → optional software
├── root  → root user’s home
├── sbin  → system admin binaries
├── tmp   → temporary files
├── usr   → user programs, docs
└── var   → logs, mail, web data
```

## 🌍 Real-World Example (Cybersecurity Context)

- **Parrot OS (Debian-based)** → used in penetration testing labs.
    
- **/etc/passwd** → file storing user accounts → critical for privilege management.
    
- **Daemons** → SSH service running in background for secure remote access.
    
- **Logs in** `/var/log` → essential for forensic analysis.
    

## 🔄 Analogy

Think of **Linux as a company**:

- **Kernel** → CEO (controls resources).
    
- **Daemons** → employees working in background.
    
- **Shell** → manager communicating tasks.
    
- **File System** → office filing system.
    
- **Philosophy** → company culture (simplicity, modularity, openness).