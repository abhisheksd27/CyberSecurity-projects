## What is Solaris?

Solaris is a **Unix-based** (not Linux-based) operating system originally developed by Sun Microsystems in the 1990s, now owned by Oracle. It's built for enterprise-grade reliability — think banks, government systems, large data centers. Unlike Linux, it's **proprietary** (closed source), which is a fundamental distinction.

Key domains where Solaris is deployed: database management, cloud computing, virtualization, financial sector infrastructure, and mission-critical services that cannot afford downtime.

---

## Solaris vs Linux — The Core Differences

![[Pasted image 20260320220148.png]]

---

## Command-by-Command Breakdown

### System Information

**Linux:**

bash

```bash
uname -a
# Output: Linux ubuntu 5.4.0-1045 ... x86_64 GNU/Linux
```

**Solaris:**

bash

```bash
showrev -a
# Output: OS version, patch level, hardware provider, kernel version
```

`showrev` gives significantly more detail — patch level tells you exactly which security patches have been applied, which is valuable during a pentest to identify unpatched vulnerabilities.

---

### Package Management

**Linux (Ubuntu):**

bash

```bash
sudo apt-get install apache2
```

**Solaris:**

bash

```bash
pkgadd -d SUNWapchr
```

Notice there's no `sudo` in the Solaris command. Solaris historically used **RBAC (Role-Based Access Control)** instead of the binary sudo model. With RBAC, users are assigned specific roles with fine-grained permissions — instead of "can run everything as root," a user might only be allowed to run specific administrative commands. `sudo` support was added in Solaris 11.

---

### Permission Management

Both use `chmod`. However, finding files with specific permissions differs:

**Linux:**

bash

```bash
find / -perm 4000     # Exact match: only files with permission 4000
```

**Solaris:**

bash

```bash
find / -perm -4000    # Match: files that HAVE the SUID bit set (plus any other bits)
```

The `-` before the permission value in Solaris means "at least these bits must be set." Without the `-` on Linux, it looks for an exact match. This is a subtle but important difference — on Linux, `find / -perm 4000` would only find files with _only_ the SUID bit and no other permissions. Using `-4000` (with the dash) is actually the correct way on both systems to find all SUID binaries.

---

### NFS (Network File System)

**Linux (Ubuntu):** NFS sharing is configured in `/etc/exports`

**Solaris:** NFS sharing uses the `share` command and is configured in `/etc/dfs/dfstab`

bash

```bash
# Share a directory over NFS with read/write access (Solaris)
share -F nfs -o rw /export/home

# Mount an NFS share (same syntax on both)
mount -F nfs 10.129.15.122:/nfs_share /mnt/local
```

The `-F nfs` flag specifies the filesystem type. The NFS config file `/etc/dfs/dfstab` is the Solaris equivalent of Linux's `/etc/exports` — it defines which directories are shared and with what options.

---

### Process Mapping — Open Files

Useful for seeing what files/sockets a process has open (great for pentesting to see what a service is doing):

**Linux:**

bash

```bash
sudo lsof -c apache2
```

**Solaris:**

bash

```bash
pfiles `pgrep httpd`
```

`pgrep httpd` finds the PID of the Apache process. `pfiles` then lists every file descriptor open by that process — regular files, network sockets, pipes. Very useful for understanding how a process interacts with the system.

---

### Syscall Tracing

One of the most powerful debugging and reconnaissance tools — traces every system call a process makes in real time:

**Linux:**

bash

```bash
sudo strace -p `pgrep apache2`
```

**Solaris:**

bash

```bash
truss ls
```

Both show you exactly what system calls a program makes — file opens, network connections, memory allocations. From a pentest perspective this can reveal:

- What files a process reads (config files, credential files)
- What network connections it makes
- What commands it spawns as child processes

Key difference: `truss` can also trace **signals sent to a process** and **syscalls of child processes** — capabilities `strace` doesn't have by default.

---

## Solaris-Specific Features Worth Knowing

**ZFS (Zettabyte File System)** — mentioned in the context of Linux distributions using it, but ZFS originated in Solaris. Provides snapshots, compression, built-in RAID, and checksumming. If you encounter a ZFS filesystem, snapshot data may contain old sensitive files.

**SMF (Service Management Facility)** — Solaris's equivalent of systemd. Manages services with dependency tracking and automatic restart on failure. Services are managed with `svcadm` and queried with `svcs`.

**RBAC** — more granular than Linux's sudo model. A user might have the `Network Management` role without full root access. When assessing Solaris systems, checking RBAC role assignments can reveal what each user is authorized to do.

**Oracle VM Server for SPARC** — built-in hypervisor for SPARC hardware. Allows logical domains (LDOMs) — essentially lightweight VMs. If you encounter a Solaris SPARC system, you may be in a logical domain rather than on bare metal.

---

## HTB / Pentest Takeaways

When you encounter a Solaris system:

- Use `showrev -a` to immediately get OS version and patch level — check for known CVEs on that exact version
- Check RBAC assignments: `roles` (lists roles for current user), `auths` (lists authorizations)
- SUID binary hunting: `find / -perm -4000` (with the dash)
- NFS shares: check `/etc/dfs/dfstab` for exported directories
- Use `pfiles` + `pgrep` instead of `lsof` for open file listing
- Use `truss` instead of `strace` for syscall tracing
- Service enumeration: `svcs -a` lists all SMF-managed services and their state
- Process listing: `ps -ef` works the same as Linux
- The closed-source nature means public kernel exploit code is rarer — but misconfigurations, RBAC weaknesses, and unpatched known CVEs are still valid vectors