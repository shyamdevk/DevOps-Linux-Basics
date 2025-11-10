# 🚀 DevOps (Linux Only)

Comprehensive notes covering **DevOps basics, Linux administration, shell scripting, process management, permissions, and automation** — perfect for both beginners 🧑‍💻 and professionals 👨‍💻.

---

## 📘 1. DevOps Basics

### 🔹 What is DevOps?

**DevOps** combines **Development (Dev)** and **Operations (Ops)** practices to:

- ⚡ Deliver applications faster  
- 🤝 Improve collaboration between teams  
- 🤖 Automate repetitive processes  
- ✅ Ensure continuous delivery with reliability  

> 💡 **Goal:** Break down silos between development and operations to achieve faster, more reliable software delivery.

---

## 🧩 2. Software Development Life Cycle (SDLC)

### 🪜 Steps:

1. **Requirement Analysis** – Collect and analyze business needs.  
2. **Planning** – Define scope, resources, and timeline.  
3. **Design** – Create architecture and design the system.  
4. **Development** – Write actual program code.  
5. **Testing** – Identify and fix bugs.  
6. **Deployment** – Release software to users.  
7. **Maintenance** – Provide updates and support.

> 📌 SDLC ensures structured software development with consistent quality.

---

## 🧱 3. SDLC Models

### **1️⃣ Waterfall Model**
Linear and sequential — each phase must finish before the next begins.

✅ Simple and easy to manage  
❌ Rigid; difficult to go back once a stage is done  

---

### **2️⃣ Big Bang Model**
Start coding immediately with minimal planning.

✅ Quick start, good for small projects  
❌ High failure risk for complex systems  

---

### **3️⃣ V-Model (Verification & Validation)**
Each development stage has a matching testing stage.

✅ Early bug detection  
❌ Rigid and expensive  

---

### **4️⃣ Iterative Model**
Develop software in small, incremental iterations.

✅ Early working prototype available  
❌ Needs careful planning and resources  

---

### **5️⃣ Spiral Model**
Combines iterative development with risk analysis.

✅ Best for high-risk, large-scale projects  
❌ Complex and costly  

---

### **6️⃣ Agile Model**
Works in short cycles (sprints) with continuous feedback.

✅ Highly flexible and customer-centric  
❌ Requires constant client involvement  

---

## ⚙️ 4. DevOps Methodology & Life Cycle

### 🔄 DevOps Life Cycle:

**Plan → Code → Build → Test → Deploy → Operate → Monitor**

| Stage | Purpose |
|:--|:--|
| Plan | Gather requirements & plan development |
| Code | Develop application |
| Build | Compile + package code |
| Test | Automated/manual testing |
| Deploy | Push to production |
| Operate | Run application |
| Monitor | Track performance and errors |


### 🧰 Key DevOps Practices

- **CI (Continuous Integration)** — merge and test code frequently  
- **CD (Continuous Delivery/Deployment)** — automate software releases  
- **IaC (Infrastructure as Code)** — manage infra via code (Terraform, CloudFormation)  
- **Monitoring & Logging** — observe performance and system health  
- **Microservices** — break applications into independent services  
- **Containers** — isolate apps using Docker/Kubernetes  

> ⚠️ **Tip:** Always integrate CI/CD with monitoring and rollback plans.

---

## 🧠 5. Linux Fundamentals

### 🧩 What is Linux?

**Linux** is an **open-source UNIX-like operating system** used for servers, desktops, and embedded systems.

> 🧑‍💻 Linux is the backbone of modern DevOps environments (cloud servers, containers, etc.).

---

### 🧠 Kernel and Its Functions

The **kernel** is the *core* of Linux that connects hardware ↔ software.

| Function | Description |
|:--|:--|
| 🧮 Process Management | Handles process creation & scheduling |
| 💾 Memory Management | Allocates and tracks RAM usage |
| 🧠 Device Management | Manages input/output devices |
| 📂 File System Management | Organizes data on disk |
| 🔐 Security & System Calls | Controls permissions and user interactions |

---

### 🐧 Linux Distributions

| Distribution | Description |
|:--|:--|
| Ubuntu | User-friendly and widely used |
| CentOS / RHEL | Enterprise-grade servers |
| Debian | Stable and open-source |
| Fedora | Cutting-edge features |
| openSUSE | Developer and system admin friendly |

> 💡 **Tip:** Choose Ubuntu for ease of use or CentOS/RHEL for enterprise servers.

---

### 📂 File System in Linux

**Definition:** A file system organizes and stores data on disks so the OS can locate and manage files efficiently.

#### 🗂️ Common File System Types
| Type | Description |
|:--|:--|
| ext2/3/4 | Standard Linux file systems |
| XFS | High performance, good for large files |
| Btrfs | Supports snapshots and scalability |
| F2FS | Optimized for flash storage |
| exFAT | Cross-platform (Windows/USB drives) |
| tmpfs | Stores temporary data in RAM |

---

### 🧭 Linux File System Hierarchy

```

/       → Root directory (base of all files)
│
├── /bin    → Essential commands (ls, cp, mv)
├── /sbin   → System admin tools
├── /etc    → Configuration files
├── /home   → User directories
├── /root   → Root user’s home
├── /var    → Variable data (logs, cache)
├── /tmp    → Temporary files
├── /usr    → User applications and libraries
├── /boot   → Bootloader & kernel files
├── /dev    → Device files
├── /proc   → Process information
└── /sys    → System/device information

````


> 🧩 **Tip:** Use `df -h` to check mounted file systems and disk usage.

---

#### 🧾 Example Commands

```bash
pwd
# Explanation: Prints the current working directory.
# Example Output:
# /home/shyam

ls -l
# Explanation: Lists files in long format (showing permissions, owner, size, and timestamp).
# Example Output:
# -rw-r--r-- 1 user user 1.0K Nov 10 notes.txt

df -h
# Explanation: Shows disk space usage in human-readable format.
# Example Output:
# Filesystem   Size  Used  Avail Use% Mounted on
# /dev/sda1    50G   12G    35G   25% /

du -sh *
# Explanation: Shows directory sizes in the current path.
# Example Output:
# 120M  project
# 4.0K  notes.txt
````

---
---

## 👥 6. Users in Linux

In Linux, everything is user-based 👤. Each user has a unique ID, home directory, and specific permissions.

### 🧑‍💼 User Types

| Type | Description |
|:--|:--|
| **System Users** | Created automatically during system/software installation (e.g., `mysql`, `apache`). Used for running services. |
| **Normal Users** | Created manually for human interaction (e.g., `ec2-user`, `student`). Used for login, SSH, and commands. |

---

## 🧑‍💻 7. User & Group Commands

All user-related operations are managed using Linux commands.  

---

### 🔹 View Current User

```bash
whoami
# Explanation: Displays the username of the current logged-in user.
# Example Output:
# shyamdev
````

---

### 🔹 Switch to Root User (Superuser)

```bash
sudo su
# Explanation: Switches to the root user with administrative privileges.
# Example Output:
# [root@localhost ~]#
```

> ⚠️ **Warning:** Use root privileges carefully — system-level commands can delete or modify critical files.

---

### 🔹 Create a New User

```bash
sudo adduser tester
# Explanation: Creates a new user named 'tester'.
# Example Output:
# Adding user `tester` ...
# Creating home directory `/home/tester` ...
# New UNIX password: ********
```

---

### 🔹 Set or Change User Password

```bash
sudo passwd tester
# Explanation: Sets or updates the password for 'tester'.
# Example Output:
# New password: ****
# Retype new password:
# passwd: password updated successfully
```

---

### 🔹 Delete a User (Keep or Remove Home Directory)

```bash
sudo userdel tester
# Explanation: Deletes user 'tester' but keeps their home directory.

sudo userdel -r tester
# Explanation: Deletes user 'tester' along with their home directory.
```

---

### 🔹 View All Users

```bash
getent passwd
# Explanation: Displays all user account entries from the /etc/passwd file.
# Example Output:
# root:x:0:0:root:/root:/bin/bash
# tester:x:1001:1001::/home/tester:/bin/bash
```

---

### 🔹 View Current Logged-in Users

```bash
who
# Explanation: Lists all users currently logged in.
# Example Output:
# shyamdev  tty1  2025-11-10 10:00
```

---

### 🧩 Create and Switch to a New User Example

```bash
sudo su        # Switch to root
adduser tester # Create new user
passwd tester  # Set password
exit            # Exit to previous user
su tester       # Switch to tester
# Example Output:
# [tester@localhost ~]$
```

---

## 🔐 8. Managing Passwords and Expiry (chage Command)

The **chage** command is used to manage password aging — forcing users to change passwords periodically for better security 🔒.

### 📘 Syntax

```bash
sudo chage [options] [username]
```

### 🔹 Common Examples

```bash
sudo chage -l tester
# Explanation: Lists password aging information for 'tester'.
# Example Output:
# Last password change : Nov 10, 2025
# Password expires     : never

sudo chage -M 30 tester
# Explanation: Sets maximum days (30) before password must be changed.

sudo chage -E 2025-12-31 tester
# Explanation: Sets account expiration date for the user.
```

---

## 👨‍🔧 9. Modifying Users (usermod Command)

`usermod` modifies existing user accounts — name, UID, home directory, group, etc.

### 📘 Syntax

```bash
sudo usermod [options] [username]
```

### 🔹 Common Examples

```bash
sudo usermod -l demouser demo
# Explanation: Changes username from 'demo' to 'demouser'.

sudo usermod -u 1050 demouser
# Explanation: Changes the UID of 'demouser' to 1050.

sudo usermod -g developers demouser
# Explanation: Changes the primary group of 'demouser' to 'developers'.

sudo usermod -d /home/newdemo demouser
# Explanation: Changes the home directory of 'demouser' to /home/newdemo.
```

---

## 👥 10. Group Management in Linux

Groups make permission management easier by grouping users 👨‍👩‍👦.

---

### 🔹 Create a New Group

```bash
sudo groupadd developers
# Explanation: Creates a new group called 'developers'.
```

---

### 🔹 Delete a Group

```bash
sudo groupdel developers
# Explanation: Deletes the group named 'developers'.
```

---

### 🔹 Modify a Group (Rename or Change GID)

```bash
sudo groupmod -n devteam developers
# Explanation: Renames 'developers' group to 'devteam'.

sudo groupmod -g 1600 devteam
# Explanation: Changes the group ID (GID) of 'devteam' to 1600.
```

---

### 🔹 Add or Remove a User to/from a Group

```bash
sudo gpasswd -a tester devteam
# Explanation: Adds user 'tester' to group 'devteam'.
# Example Output:
# Adding user tester to group devteam

sudo gpasswd -d tester devteam
# Explanation: Removes user 'tester' from group 'devteam'.
```

---

### 🔹 View All Groups or Specific Group Info

```bash
getent group
# Explanation: Lists all groups on the system.
# Example Output:
# root:x:0:
# devteam:x:1600:tester

getent group devteam
# Explanation: Shows details of the group 'devteam'.
```

---

### 🔹 Show Groups a User Belongs To

```bash
groups tester
# Explanation: Displays all groups the user 'tester' belongs to.
# Example Output:
# tester : devteam docker
```

---

> 💡 **Pro Tip:** Use `sudo usermod -aG groupname username` to add a user to a group without removing existing memberships.

---

## 🔐 11. Permission Management in Linux

Linux uses file permissions to control who can read, write, or execute files.
Every file/directory has 3 sets of permissions — for **User**, **Group**, and **Others** 👇

---

### 📘 Permission Types

| Symbol | Meaning | Numeric Value |
| :----- | :------ | :------------ |
| r      | Read    | 4             |
| w      | Write   | 2             |
| x      | Execute | 1             |

---

### 🔹 View Permissions

```bash
ls -l
# Explanation: Lists files and their permissions.
# Example Output:
# -rw-r--r-- 1 tester devteam 1.2K Nov 10 notes.txt
# drwxr-xr-x 2 tester devteam 4.0K Nov 10 projects
```

---

### 🔹 Change Permissions (chmod)

```bash
chmod u+x script.sh
# Explanation: Adds execute permission for the owner.

chmod go-w myfile.txt
# Explanation: Removes write permission for group and others.

chmod 755 app.sh
# Explanation: Gives owner rwx (7), group rx (5), others rx (5).
```

---

### 🔹 Change Ownership (chown / chgrp)

```bash
sudo chown tester myfile.txt
# Explanation: Changes owner of file to 'tester'.

sudo chown tester:devteam myfile.txt
# Explanation: Changes both owner and group.

sudo chgrp devteam project/
# Explanation: Changes the group ownership of directory 'project' to 'devteam'.
```

---

### 🔹 Example Output

```bash
ls -l
# -rwxr-xr-- 1 tester devteam 2.1K Nov 10 app.sh
```

> ✅ **Interpretation:**
> Owner (tester): read, write, execute
> Group (devteam): read, execute
> Others: read only

---

## 📦 12. Package Managers in Linux

Package managers make installing, updating, and removing software easy 🧠.

| Distribution    | Package Manager | Example Command           |
| :-------------- | :-------------- | :------------------------ |
| Ubuntu / Debian | APT             | `sudo apt install nginx`  |
| CentOS / Fedora | YUM / DNF       | `sudo dnf update`         |
| openSUSE        | Zypper          | `sudo zypper install git` |

---

### 🔹 Common Examples

```bash
sudo apt install vim
# Explanation: Installs the 'vim' text editor.

sudo yum remove nano
# Explanation: Removes the 'nano' package on RHEL-based systems.

sudo dnf update
# Explanation: Updates all installed packages to their latest versions.
```

---

### 🔹 Additional Commands

```bash
apt list --installed
# Explanation: Lists all installed packages.

yum info httpd
# Explanation: Shows detailed info about the 'httpd' (Apache) package.

dnf history
# Explanation: Displays a log of package install/remove history.
```

---

> 💡 **Tip:** Always update your repositories before installing packages:

```bash
sudo apt update
sudo dnf check-update
```

---

### 🧩 Short Summary

* 🧱 **Install software:** `sudo apt install <pkg>`
* 🔄 **Update software:** `sudo apt update && sudo apt upgrade`
* ❌ **Remove software:** `sudo apt remove <pkg>`
* 🔍 **Search package:** `apt search <pkg>`

---

````markdown
---

## 🧭 13. File & Directory Management in Linux

Everything in Linux is treated as a file 📂 — even directories and devices.  
Here are the most useful commands to navigate and manipulate files.

---

### 🗺️ Navigation Commands

```bash
pwd
# Explanation: Prints the absolute path of the current working directory.
# Example Output:
# /home/shyam/projects

cd /etc
# Explanation: Moves into the '/etc' directory.

cd ..
# Explanation: Moves one level up in the directory tree.

cd ~
# Explanation: Returns to your home directory.

cd -
# Explanation: Switches to your previous working directory.
````

---

### 📋 Listing Files and Directories

```bash
ls
# Explanation: Lists files and directories in the current folder.

ls -l
# Explanation: Long listing format showing permissions, owner, size, and modification date.

ls -a
# Explanation: Displays hidden files (those starting with a dot).

ls -lh
# Explanation: Displays file sizes in human-readable format (KB, MB, GB).

ls -R
# Explanation: Lists all files recursively including subdirectories.
```

> 💡 **Pro Tip:** Combine options like `ls -lah` for full details.

---

### 🏗️ Create Files and Directories

```bash
touch notes.txt
# Explanation: Creates an empty file or updates the modification time if it already exists.

mkdir project
# Explanation: Creates a new directory named 'project'.

mkdir -p project/src/assets
# Explanation: Creates nested directories (if they don’t exist).
```

---

### ❌ Remove Files or Directories

```bash
rm file.txt
# Explanation: Deletes a file named 'file.txt'.

rm -r folder
# Explanation: Deletes a directory and its contents recursively.

rm -rf folder
# Explanation: Forcefully deletes directory and all contents (⚠️ Use with caution).

rmdir tempdir
# Explanation: Deletes an empty directory only.
```

---

### 📖 View File Content

```bash
cat file.txt
# Explanation: Displays the content of 'file.txt' in the terminal.
# Example Output:
# Welcome to DevOps Notes!

tac file.txt
# Explanation: Displays content of a file in reverse order (from last line to first).

less bigfile.txt
# Explanation: Views large files one page at a time. Press 'q' to quit, '/' to search.

head -n 10 file.txt
# Explanation: Displays the first 10 lines of a file.

tail -n 20 log.txt
# Explanation: Displays the last 20 lines of a log file.

tail -f /var/log/syslog
# Explanation: Continuously monitors new lines added to a file (useful for logs).
```

---

### 🔁 Copying, Moving, and Renaming

```bash
cp source.txt destination.txt
# Explanation: Copies a file from source to destination.

cp -r project backup/
# Explanation: Copies directories recursively.

mv oldname.txt newname.txt
# Explanation: Renames a file.

mv notes.txt /tmp/
# Explanation: Moves file to /tmp/ directory.
```

---

## 🧮 14. Searching and Archiving Files

Linux provides several tools to find, compress, and bundle files efficiently 🎯.

---

### 🔍 Searching for Files

```bash
find /etc -name hosts
# Explanation: Searches for files named 'hosts' inside /etc.

find . -type f -size +10M
# Explanation: Finds all files larger than 10 MB in the current directory.

locate passwd
# Explanation: Quickly finds files using a pre-built index database (update with 'sudo updatedb').
```

---

### 🔎 Searching Within Files

```bash
grep "root" /etc/passwd
# Explanation: Searches for the word "root" inside /etc/passwd file.
# Example Output:
# root:x:0:0:root:/root:/bin/bash

ls | grep ".txt"
# Explanation: Lists only .txt files from the ls command output using pipe.
```

---

### 📦 Archiving and Compression

#### 🧱 Using `tar` (Tape Archive)

```bash
tar -cvf backup.tar myfolder/
# Explanation: Creates an archive named 'backup.tar' containing files from 'myfolder/'.

tar -xvf backup.tar
# Explanation: Extracts all files from 'backup.tar'.

tar -tvf backup.tar
# Explanation: Lists contents of the tar archive without extracting.
```

---

#### 🗜️ Using `gzip` and `gunzip`

```bash
gzip file.txt
# Explanation: Compresses 'file.txt' into 'file.txt.gz'.

gunzip file.txt.gz
# Explanation: Decompresses 'file.txt.gz' back to 'file.txt'.
```

---

#### 🧳 Using `zip` and `unzip`

```bash
zip -r project.zip project/
# Explanation: Compresses the 'project' directory into a .zip file.

unzip project.zip
# Explanation: Extracts contents of 'project.zip'.
```

---

> 💡 **Tip:** To combine tar + gzip:

```bash
tar -czvf archive.tar.gz folder/
# Compress
tar -xzvf archive.tar.gz
# Extract
```

---

## ⚙️ 15. Process Management in Linux

Processes are the lifeblood of Linux — every command or program runs as a process 🧩.

---

### 🧾 Viewing Processes

```bash
ps
# Explanation: Lists processes running in the current shell.

ps -e
# Explanation: Lists all system processes.

ps aux
# Explanation: Detailed view showing user, PID, CPU%, memory%, and command.

top
# Explanation: Displays real-time resource usage (CPU, memory, etc.).
# Example Output:
# PID   USER   PR  NI  VIRT  RES  SHR S  %CPU %MEM TIME+ COMMAND
# 1340  root   20   0  456M  53M  23M S   5.0  2.1  0:23  apache2
```

> 💡 Press `q` to quit `top`. Use `htop` for a colorized and interactive interface.

---

### 🧠 Searching for Processes

```bash
pgrep nginx
# Explanation: Searches for process IDs matching the name 'nginx'.

pidof sshd
# Explanation: Displays the PID(s) of the 'sshd' process.
# Example Output:
# 1305
```

---

### 🔚 Killing Processes

```bash
kill -9 1305
# Explanation: Forcefully terminates the process with PID 1305.

pkill nginx
# Explanation: Terminates all processes with the name 'nginx'.

killall firefox
# Explanation: Kills all instances of 'firefox'.
```

> ⚠️ **Warning:** Always try `kill <pid>` (graceful) before `kill -9` (forceful).

---

### 🌳 Viewing Process Tree

```bash
pstree -p
# Explanation: Displays processes in a hierarchical tree structure with PIDs.
```

---

### ⚡ Changing Process Priority

Linux uses a **niceness value** (-20 to +19).
Lower = higher priority 🔺, higher = lower priority 🔻.

```bash
nice -n 10 ./task.sh
# Explanation: Starts a process with lower priority.

renice -n -5 -p 1340
# Explanation: Changes priority of running process with PID 1340 to higher (-5).
```

---

### 🧩 Monitoring Resource Usage

```bash
time ./script.sh
# Explanation: Measures execution time of a script.

lsof -p 1340
# Explanation: Lists all open files by process ID 1340.

vmstat 2 5
# Explanation: Displays memory, process, and CPU stats every 2 seconds for 5 iterations.

iostat 2 3
# Explanation: Shows CPU and I/O statistics.

sar -u 2 3
# Explanation: Displays CPU utilization over time (3 samples every 2 seconds).
```

---

### 📉 Example Output (vmstat)

```
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 1  0      0 204800  36000 320000    0    0     1     2  125  300  2  1 97  0  0
```

> 🧠 **Tip:** Monitor memory and CPU regularly on servers to prevent bottlenecks.

---

## 🧠 16. Memory & CPU Management

The Linux kernel handles both memory and CPU scheduling intelligently — but you can check and control it manually.

---

### 🧩 Memory Monitoring Commands

```bash
free -h
# Explanation: Displays used, free, and available memory in human-readable format.
# Example Output:
#               total   used   free   shared  buff/cache  available
# Mem:           8.0G   2.3G   4.5G     200M       1.2G       5.0G

cat /proc/meminfo
# Explanation: Shows detailed memory stats including swap and buffer sizes.

vmstat 1
# Explanation: Continuously reports memory, CPU, and I/O every 1 second.
```

---

### 🧩 CPU Management Commands

```bash
uptime
# Explanation: Displays system uptime, number of users, and load averages.
# Example Output:
# 10:32:45 up 5 days, 3 users, load average: 0.10, 0.15, 0.12

taskset -c 0,1 python3 script.py
# Explanation: Runs the Python script only on CPU cores 0 and 1.
```

---

> 💡 **Tip:** Load average indicates system load over 1, 5, and 15 minutes.

* A value ≤ number of CPU cores → system is healthy
* A value > number of cores → system is overloaded ⚠️

---

## 🐚 17. Shell & Shell Scripting

Shell scripting automates repetitive tasks by combining Linux commands in a file executed by a shell interpreter 🧾.

---

### 🧩 What is a Shell?

A **Shell** is the bridge between you and the kernel — it executes your commands.

| Shell Type | Description                           |
| :--------- | :------------------------------------ |
| sh         | Original Bourne Shell                 |
| bash       | Bourne Again Shell (default on Linux) |
| zsh        | Z Shell (modern and customizable)     |
| fish       | Friendly Interactive Shell            |
| csh        | C Shell (C-like syntax)               |

---

### 🧾 Example Script

```bash
#!/bin/bash
echo "Hello, DevOps World!"
date
```

> 📘 Save it as `hello.sh`, make it executable:

```bash
chmod +x hello.sh
./hello.sh
```

**Output:**

```
Hello, DevOps World!
Mon Nov 10 10:45:32 IST 2025
```

---

### 🧩 Variables in Shell

```bash
name="Shyam"
echo "Hello $name"
# Output:
# Hello Shyam
```

---

### 🧩 Taking User Input

```bash
echo "Enter your city:"
read city
echo "You live in $city"
# Example Output:
# Enter your city:
# Kochi
# You live in Kochi
```

---

### 🧩 Conditional Statements

```bash
age=20
if [ $age -ge 18 ]; then
  echo "You are an adult"
else
  echo "You are a minor"
fi
# Output: You are an adult
```

---

### 🧩 Loops in Shell

```bash
for i in 1 2 3 4 5; do
  echo "Iteration $i"
done
# Output:
# Iteration 1
# Iteration 2
# Iteration 3
# Iteration 4
# Iteration 5
```

---

### 🧩 Functions in Shell

```bash
greet() {
  echo "Welcome, $1!"
}
greet "Shyam"
# Output: Welcome, Shyam!
```

---

### 🧩 Exit Status

```bash
ls /nonexistent
echo $?
# Explanation: Returns exit status of previous command (0 = success, non-zero = failure).
# Output: 2
```

---

> 💡 **Pro Tip:** Always start scripts with `#!/bin/bash` (called a **shebang**) to specify the interpreter.

---

---

## 📊 18. System Monitoring Data

System monitoring ensures that servers and applications run smoothly and that issues are detected early ⚡.

---

### 🧾 Types of Monitoring Data

| Type | Description | Purpose |
|:--|:--|:--|
| **Logs** | Records of events and system activities | Helps identify errors and events |
| **Metrics** | Numerical data representing system performance | Track trends like CPU load or memory use |
| **Traces** | Show how requests flow across services | Debug and optimize distributed applications |

---

### 🔹 Log Monitoring

```bash
journalctl
# Explanation: Displays logs from the systemd journal (system-wide logs).
# Example Output:
# Nov 10 10:50:20 localhost systemd[1]: Started Session 2 of user tester.
````

> 💡 Use filters like:

```bash
journalctl -u ssh
# View only SSH-related logs
```

---

### 🔹 Metrics Monitoring

Use tools like:

* `vmstat` → Monitor memory and process stats
* `iostat` → Monitor CPU and disk usage
* `top` / `htop` → Real-time process and resource usage
* `sar` → Historical performance data

---

### 🔹 Tracing Example (for debugging services)

```bash
strace -p <pid>
# Explanation: Traces system calls made by a process (great for debugging errors).
# Example Output (partial):
# open("/etc/hosts", O_RDONLY) = 3
# read(3, "127.0.0.1 localhost\n", 512) = 22
# close(3) = 0
```

---

## 🔗 19. Hard Link and Soft Link in Linux

Links allow multiple references to the same file 📎.
There are two types of links — **Hard Links** and **Soft Links (Symbolic Links)**.

---

### 🧱 1️⃣ Hard Link

```bash
ln original.txt hardlink.txt
# Explanation: Creates a hard link 'hardlink.txt' pointing to 'original.txt'.
# Example Output:
# (No output, but a new link is created)
```

> ✅ Both files now share the same inode number.

* Deleting one will **not** affect the other.
* Only works within the same filesystem.

```bash
ls -li
# Example Output:
# 105123 -rw-r--r-- 2 shyam users 1.0K Nov 10 original.txt
# 105123 -rw-r--r-- 2 shyam users 1.0K Nov 10 hardlink.txt
```

---

### 🧷 2️⃣ Soft Link (Symbolic Link)

```bash
ln -s /home/shyam/original.txt shortcut.txt
# Explanation: Creates a symbolic (soft) link named 'shortcut.txt' pointing to the original file.
# Example Output:
# (No output, but shortcut.txt appears as a link)
```

> ❌ If the original file is deleted, the soft link becomes **broken**.

```bash
ls -l
# Example Output:
# lrwxrwxrwx 1 shyam users 20 Nov 10 shortcut.txt -> /home/shyam/original.txt
```

---

> 🧠 **Quick Summary:**
> | Type | Same Inode | Works Across File Systems | Breaks If Target Deleted | Use Case |
> |:--|:--|:--|:--|:--|
> | Hard Link | ✅ Yes | ❌ No | ❌ No | Redundancy |
> | Soft Link | ❌ No | ✅ Yes | ✅ Yes | Shortcuts |

---

## ⏰ 20. Cron Jobs in Linux

A **cron job** automates tasks by running commands or scripts at scheduled times 🕒.
Perfect for backups, updates, and maintenance.

---

### ⚙️ Cron Service

The cron daemon (`crond`) runs in the background and reads scheduling tables called **crontabs**.

---

### 🔹 Cron Syntax

```
*  *  *  *  *  command_to_run
│  │  │  │  │
│  │  │  │  └── Day of week (0–7; Sunday = 0 or 7)
│  │  │  └───── Month (1–12)
│  │  └──────── Day of month (1–31)
│  └─────────── Hour (0–23)
└────────────── Minute (0–59)
```

---

### 🧩 Examples

```bash
0 5 * * * /home/user/backup.sh
# Explanation: Runs backup.sh every day at 5:00 AM.

*/10 * * * * /home/user/script.sh
# Explanation: Runs script.sh every 10 minutes.

0 0 * * 0 /home/user/cleanup.sh
# Explanation: Runs cleanup.sh every Sunday at midnight.
```

---

### 🔹 Manage Cron Jobs

```bash
crontab -e
# Explanation: Opens your crontab file for editing.

crontab -l
# Explanation: Lists all scheduled cron jobs for the current user.

crontab -r
# Explanation: Removes all cron jobs for the current user.
```

---

### 🧠 Example: Backup Every Day at 3 AM

1️⃣ Create a script `/home/shyam/backup.sh`:

```bash
#!/bin/bash
tar -czf /backup/project_$(date +\%F).tar.gz /home/shyam/project
```

2️⃣ Schedule it with cron:

```bash
crontab -e
# Add line:
0 3 * * * /home/shyam/backup.sh
```

3️⃣ Confirm:

```bash
crontab -l
# Output:
# 0 3 * * * /home/shyam/backup.sh
```

> 🧩 **Tip:** To view system-wide jobs, check `/etc/crontab` or `/etc/cron.*` directories.

---

### 🧰 Bonus: Systemd Timer Alternative (Modern Replacement)

```bash
systemctl list-timers
# Explanation: Lists all active systemd timers.

sudo systemctl enable myservice.timer
# Explanation: Enables an automated timer task.
```

---

## 🧠 21. Quick DevOps + Linux Recap

✅ **Core DevOps Concepts**

* CI/CD, Automation, Monitoring, IaC, Containers
* Collaboration between Development & Operations

✅ **Linux Essentials**

* User & Group management
* File permissions & ownership
* Package management
* Process & resource monitoring
* Shell scripting for automation

✅ **Key Tools**

* `git`, `docker`, `ansible`, `jenkins`, `terraform`, `kubernetes`
* `top`, `ps`, `grep`, `awk`, `sed`, `tar`, `cron`, `journalctl`

---

> 💡 **Pro Tip:** Combine your Linux skills with CI/CD tools (like Jenkins, Docker, Kubernetes) to master DevOps automation.

---

## 🧾 Author

👨‍💻 **Created by:** *Shyamdev K*
🧠 **Platform:** Linux (Fedora / Ubuntu)
🎯 **Purpose:** Comprehensive DevOps & Linux Reference Guide for learners and professionals

📘 *You can freely use, modify, and share these notes for educational or professional reference.*

---

> ⭐ **If you found this helpful:**
>
> * Give this repository a ⭐ on GitHub
> * Fork it and improve it
> * Share with your DevOps & Linux learning community!

---




