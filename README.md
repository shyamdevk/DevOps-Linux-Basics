# DevOps and Linux Basics Study Guide

> **Author:** Shyamdev
> **Purpose:** A complete DevOps + Linux basics study material formatted for GitHub repositories.

---

## 📘 Overview

This repository contains beginner-to-intermediate level notes on **DevOps**, **Linux administration**, **Shell scripting**, and **system monitoring**. The content has been formatted into Markdown for better readability and sharing.

You can upload related diagrams in the `images/` folder and replace placeholders like `![Image](images/example.png)`.

---

## 🧩 What is DevOps?

DevOps is a set of **practices combining development (Dev)** and **operations (Ops)** to deliver applications faster, improve collaboration, automate processes, and ensure continuous delivery with better reliability.

---

## ⚙️ Software Development Life Cycle (SDLC)

### Steps:

1. **Requirement analysis** – Collect and analyze needs.
2. **Planning** – Define scope, resources, and timeline.
3. **Design** – Create system architecture.
4. **Development** – Write actual code.
5. **Testing** – Find and fix bugs.
6. **Deployment** – Release to users.
7. **Maintenance** – Support and updates.

---

## 🧱 SDLC Methodologies

### 1. Waterfall Model

* **Process:** Linear and sequential.
* **Advantages:** Simple, easy to manage.
* **Disadvantages:** Rigid, issues found late.

### 2. Big Bang Model

* **Advantages:** Quick, simple for small projects.
* **Disadvantages:** Risky, lacks structure.

### 3. V-Model (Verification & Validation)

* **Advantages:** Testing at every stage.
* **Disadvantages:** Costly, rigid.

### 4. Iterative Model

* **Advantages:** Early system available.
* **Disadvantages:** Needs good planning.

### 5. Spiral Model

* **Advantages:** Focus on risk management.
* **Disadvantages:** Complex, expensive.

### 6. Agile Model

* **Advantages:** Flexible, quick delivery.
* **Disadvantages:** Hard to predict cost/time.

---

## 🔁 DevOps Life Cycle

**Phases:**

* Plan → Code → Build → Test → Deploy → Operate → Monitor

---

## 🚀 Key DevOps Concepts

* **CI/CD:** Continuous integration & deployment for automation.
* **IaC:** Infrastructure as Code (manage infra using scripts).
* **Monitoring:** Track performance & uptime.
* **Logging:** Record system/app activity.
* **Microservices:** Modular service-based architecture.
* **Containers:** Lightweight isolated environments (e.g., Docker).

---

## 🧠 Kernel & Its Functions

The **kernel** is the core of Linux OS, managing hardware and software communication.

* Process management
* Memory management
* Device management
* File system management
* Security & system calls

---

## 🐧 Linux and Distributions

Linux is an **open-source operating system** based on UNIX.

**Popular distros:** Ubuntu, Fedora, RedHat, CentOS, Debian.

---

## 📂 Linux File System Types

* **ext4:** Most common, reliable.
* **XFS:** High performance for large files.
* **Btrfs:** Modern, supports snapshots.
* **F2FS:** Optimized for flash storage.
* **exFAT:** Cross-platform.
* **tmpfs:** RAM-based temporary storage.

---

## 🏗 Linux File System Hierarchy

```
/       - Root directory
/bin    - Essential user commands
/sbin   - System admin commands
/etc    - Configuration files
/home   - User directories
/root   - Root user home
/var    - Variable data
/tmp    - Temporary files
/usr    - User applications
/boot   - Bootloader files
/dev    - Device files
/proc   - Process info
/sys    - System device info
```

![Image](images/linux-hierarchy.png)

---

## 👥 Linux Users & Groups

### 1. System Users

* Created by OS or services.
* UIDs 0–999 (root = 0).

### 2. Normal Users

* Created manually.
* UIDs start from 1000.

**Commands:**

```bash
whoami
sudo su
su <user>
adduser <username>
getent passwd
userdel -r <username>
```

---

## 🔐 Permission Management

Each file has permissions for **owner**, **group**, and **others**.

| Permission  | Value |
| ----------- | ----- |
| Read (r)    | 4     |
| Write (w)   | 2     |
| Execute (x) | 1     |

**Examples:**

```bash
chmod 755 script.sh
chmod u+x file.txt
sudo chown user:group file.txt
```

---

## 📦 Package Managers

| Distro        | Package Manager | Example                |
| ------------- | --------------- | ---------------------- |
| Ubuntu/Debian | APT             | sudo apt install nginx |
| Fedora        | DNF             | sudo dnf update        |
| CentOS        | YUM             | sudo yum remove nano   |

---

## 📁 File and Directory Management

```bash
pwd                      # show current directory
cd /etc                  # navigate
ls -lah /var/log          # list contents
mkdir project             # create directory
touch notes.txt           # create file
rm -rf folder             # delete forcefully
```

---

## 🔍 Searching & Archiving

```bash
find /etc -name hosts
locate passwd
grep "error" logfile.log
tar -cvf backup.tar myfolder/
zip -r project.zip project_dir
```

---

## ⚙️ Process Management

```bash
ps aux                    # list processes
top / htop                # monitor live
kill -9 <pid>             # terminate process
nice -n 10 ./task.sh      # set low priority
renice -n -5 -p 1234      # increase priority
```

**Monitoring Commands:**

```bash
vmstat 1
sar -u 2 3
lsof -p <pid>
iostat 2 3
```

---

## 🧠 Memory & CPU Management

```bash
free -h                   # show memory usage
cat /proc/meminfo         # detailed memory info
uptime                    # system uptime & load
```

---

## 🐚 Shell & Shell Scripting

**Shell:** Interface between user and kernel.

**Common Shells:** bash, zsh, sh, fish, csh

**Example Script:**

```bash
#!/bin/bash
echo "Hello, DevOps!"
date
```

### Conditional Example

```bash
if [ $age -ge 18 ]; then
  echo "Adult"
else
  echo "Minor"
fi
```

### Loops Example

```bash
for i in 1 2 3; do
  echo "Count: $i"
done
```

---

## 📊 Monitoring Data in Linux

| Type    | Description               | Example       |
| ------- | ------------------------- | ------------- |
| Logs    | Records of events         | journalctl    |
| Metrics | System performance values | top, sar      |
| Traces  | Path of execution         | tracing tools |

---

## 🔗 Hard vs Soft Links

**Hard Link:** Points to same inode.

```bash
ln file.txt hardlink.txt
```

**Soft Link (Symbolic):** Shortcut to a file.

```bash
ln -s file.txt softlink.txt
```

![Image](images/links.png)

---

## ⏰ Cron Jobs

Automate tasks on a schedule.

```bash
* * * * * /path/to/script.sh
```

**Examples:**

* `0 5 * * *` → Every day at 5 AM
* `*/10 * * * *` → Every 10 minutes
* `0 0 * * 0` → Every Sunday midnight

---

## 📎 Notes

* Upload missing images into the `images/` folder.
* Replace placeholders accordingly.
* Use this README for DevOps/Linux study, projects, or portfolio purposes.

---

## 🧩 Contribute

Contributions, examples, and corrections are welcome! Fork this repo and submit a pull request.

> *This README is auto-formatted from study notes for educational use.*
