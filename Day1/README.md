# Day 1 – Understanding Linux (RHCSA Preparation)

This document is part of my **RHCSA/RHCE preparation journey**.
Day 1 focuses on **Linux fundamentals**, which are essential before working with files, users, services, and automation.

---

## 1. What is Linux?

Linux is an **open-source, Unix-like operating system kernel**, originally created by **Linus Torvalds** in 1991.

Important points:
- Linux is a **kernel**, not a full operating system
- A complete Linux OS includes:
  - Linux kernel
  - GNU utilities
  - Shell
  - System libraries
- Linux is widely used in:
  - Servers
  - Cloud platforms
  - Containers
  - DevOps and security environments

---

## 2. Brief History of Linux

- UNIX was powerful but proprietary
- Linux was created as a free alternative
- Combined with GNU tools, Linux became a full OS
- Today, Linux powers:
  - Most cloud infrastructure
  - Supercomputers
  - Android devices

---

## 3. Linux Distributions

A **Linux distribution (distro)** is a complete operating system built using the Linux kernel.

Common distributions:

| Distribution | Package Manager | Usage |
|-------------|----------------|------|
| RHEL | dnf | Enterprise servers, RHCSA/RHCE |
| CentOS Stream | dnf | Upstream RHEL |
| Rocky / AlmaLinux | dnf | RHEL compatible |
| Ubuntu | apt | Cloud & DevOps |
| Debian | apt | Stable servers |
| Fedora | dnf | Latest features |

> RHCSA/RHCE exams are **RHEL-based**.

---

## 4. Why Command Line is Important

Linux administrators rely on the **command line** because:
- Servers often have no GUI
- Commands are faster and scriptable
- Remote administration requires CLI

RHCSA expects strong command-line skills.

---

## 5. Linux File System Structure

Linux uses a **single directory tree** starting at `/`.

Key directories:

| Directory | Purpose |
|---------|--------|
| / | Root directory |
| /bin | Essential commands |
| /sbin | System admin commands |
| /etc | Configuration files |
| /home | User home directories |
| /root | Root user home |
| /var | Logs and variable data |
| /tmp | Temporary files |
| /usr | User programs |
| /dev | Devices |
| /proc | Kernel information |

> In Linux, **everything is a file**.

---

## 6. Users and Root

- Linux is a **multi-user OS**
- `root` has full privileges
- Normal users have limited access
- Permissions control access to files and commands

---

## 7. Kernel Space vs User Space

- **Kernel Space**: hardware, memory, CPU, drivers
- **User Space**: shell, commands, applications

User commands interact with the kernel indirectly.

---

## 8. Shell in Linux

A shell allows users to interact with Linux.

Common shells:
- bash (default for RHCSA)
- sh
- zsh

All examples in this repo use **bash**.

---

## 9. What’s Next

**Day 2: File System & Basic Commands**
- ls
- cd
- pwd
- touch
- cat
- cp
- mv
- rm
- mkdir
