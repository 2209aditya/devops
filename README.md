# Linux – A Complete Guide 🐧  

## **📌 What is Linux?**  
Linux is an **open-source, Unix-like operating system** based on the **Linux kernel**, developed by Linus Torvalds in **1991**. It is widely used in **servers, cloud computing, DevOps, cybersecurity, embedded systems, and desktops** due to its stability, security, and flexibility.  

---

## **1️⃣ Why Use Linux?**  
✅ **Free & Open Source** – No licensing cost, customizable.  
✅ **Highly Secure** – Minimal virus threats.  
✅ **Stable & Reliable** – Used in servers, cloud, and mission-critical applications.  
✅ **Lightweight & Fast** – Efficient use of system resources.  
✅ **Multi-User & Multi-Tasking** – Supports multiple users/processes simultaneously.  
✅ **Great for Developers & DevOps** – Supports tools like Git, Docker, Kubernetes, Ansible, etc.  

---

## **2️⃣ Linux Distributions (Distros)**  
Different flavors of Linux cater to different needs.  

| **Category** | **Popular Distros** |
|-------------|---------------------|
| **General Purpose** | Ubuntu, Debian, Fedora |
| **Enterprise** | Red Hat Enterprise Linux (RHEL), CentOS, SUSE Linux Enterprise |
| **Lightweight** | Alpine Linux, Arch Linux, Puppy Linux |
| **Security-Focused** | Kali Linux, Parrot OS |
| **For Developers** | Ubuntu, Fedora, Arch Linux |

---

## **3️⃣ Linux File System Structure**  
Linux follows a hierarchical directory structure.  

| **Directory** | **Description** |
|-------------|----------------|
| `/` | Root directory (base of file system) |
| `/bin` | Essential binary files (commands) |
| `/etc` | Configuration files |
| `/home` | User home directories |
| `/var` | Logs, spool files, and variable data |
| `/tmp` | Temporary files |
| `/usr` | User-installed software & libraries |
| `/root` | Root user’s home directory |
| `/boot` | Bootloader & kernel files |

---

## **4️⃣ Basic Linux Commands**  
### **4.1 File & Directory Management**  
```sh
ls        # List files & directories
pwd       # Show current directory
cd /path  # Change directory
mkdir dir # Create a directory
rm file   # Delete a file
rmdir dir # Remove an empty directory
rm -r dir # Remove a directory and its contents
cp src dest  # Copy file or directory
mv src dest  # Move/Rename a file or directory
```

### **4.2 File Viewing & Editing**  
```sh
cat file      # View file content
less file     # View large files page by page
nano file     # Edit file using nano editor
vim file      # Edit file using Vim editor
```

### **4.3 Process Management**  
```sh
ps aux      # List running processes
top         # Show active processes in real-time
kill PID    # Kill a process by PID
pkill name  # Kill a process by name
```

### **4.4 User & Permission Management**  
```sh
whoami         # Show current user
id             # Show user ID & group ID
chmod 755 file # Change file permissions
chown user file # Change file owner
sudo command   # Run command as superuser
```

### **4.5 Network & Connectivity**  
```sh
ping google.com    # Check network connectivity
ifconfig          # Show network interfaces (deprecated)
ip addr show      # Show IP addresses
netstat -tulnp    # Show active network connections
```

### **4.6 System Monitoring**  
```sh
df -h    # Show disk usage
du -sh * # Show folder size
free -m  # Show memory usage
uptime   # Show system uptime
```

---

## **5️⃣ Linux User & Group Management**  
### **5.1 Adding & Managing Users**  
```sh
adduser username   # Add a new user
passwd username    # Set/change password
deluser username   # Delete a user
```

### **5.2 Managing Groups**  
```sh
groupadd devops     # Create a group
usermod -aG devops username  # Add user to group
groups username     # Show user’s groups
```

---

## **6️⃣ File Permissions in Linux**  
### **6.1 Understanding Permissions**  
```sh
ls -l file
```
Output example:  
```
-rwxr--r--  1 user user  1234 Mar 16 10:00 script.sh
```
| **Character** | **Meaning** |
|--------------|------------|
| `-` | File type (`-` for file, `d` for directory) |
| `rwx` | Owner permissions (read/write/execute) |
| `r--` | Group permissions (read-only) |
| `r--` | Others' permissions (read-only) |

### **6.2 Changing Permissions**  
```sh
chmod 755 script.sh  # Give owner full access, others read & execute
```

---

## **7️⃣ Package Management in Linux**  
Different distros use different package managers.  

| **Distro** | **Package Manager** | **Command** |
|-----------|--------------------|------------|
| Ubuntu/Debian | APT | `apt install package` |
| RHEL/CentOS | YUM/DNF | `yum install package` or `dnf install package` |
| Arch Linux | Pacman | `pacman -S package` |

---

## **8️⃣ Shell Scripting in Linux**  
Linux allows automation using shell scripts.  

### **Example Shell Script**  
```sh
#!/bin/bash
echo "Hello, Linux User!"
date
```

---

## **9️⃣ Linux Process Management**  
### **9.1 Running Processes in Background**  
```sh
command &  # Run in background
jobs       # List background jobs
fg %1      # Bring job to foreground
bg %1      # Resume job in background
```

### **9.2 Finding & Killing Processes**  
```sh
ps aux | grep nginx  # Find nginx process
kill -9 PID          # Force kill process
```

---

## **🔟 Linux in DevOps & Cloud**  
💻 **Server Management** – Runs most web servers (Nginx, Apache).  
☁ **Cloud Computing** – Used in AWS, Azure, Google Cloud.  
🐳 **Containerization** – Docker, Kubernetes rely on Linux.  
📦 **Automation & Scripting** – Shell scripting, Ansible.  
🛡 **Security & Penetration Testing** – Kali Linux for ethical hacking.  

---

## **🚀 Conclusion**  
Linux is a **powerful, flexible, and secure operating system** used in **servers, cloud computing, cybersecurity, DevOps, and development**.  

