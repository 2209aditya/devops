# Shell Scripting – A Complete Guide 🚀  

## **📌 What is Shell Scripting?**  
Shell scripting is the process of writing a series of commands in a **shell script** file to automate tasks in **Linux/Unix environments**. It helps DevOps engineers, system administrators, and developers automate system tasks, deployments, monitoring, and more.  

---

## **1️⃣ Why Use Shell Scripting?**  
✅ **Automates repetitive tasks** (e.g., backups, user management).  
✅ **Simplifies complex commands** into scripts.  
✅ **Schedules jobs** using cron.  
✅ **Efficient log management** and system monitoring.  
✅ **Integrates with DevOps tools** (Jenkins, Ansible, Docker, Kubernetes).  

---

## **2️⃣ Shell Scripting Basics**  
A shell script is a text file containing **commands executed sequentially** by a shell (Bash, Zsh, etc.).  

### **2.1 Writing Your First Shell Script**  
1. **Create a file** (e.g., `script.sh`):  
   ```sh
   #!/bin/bash
   echo "Hello, World!"
   ```
2. **Make it executable:**  
   ```sh
   chmod +x script.sh
   ```
3. **Run the script:**  
   ```sh
   ./script.sh
   ```

---

## **3️⃣ Variables in Shell Scripting**  
Variables store data and can be used dynamically.  

```sh
#!/bin/bash
NAME="DevOps Engineer"
echo "Hello, $NAME!"
```

### **Types of Variables**  
| **Variable Type** | **Description** |
|------------------|----------------|
| **Local Variable** | Available only in the script where it's defined. |
| **Environment Variable** | Available globally across sessions. |
| **Special Variables** | System-defined variables (e.g., `$0`, `$1`, `$?`). |

#### **Special Variables in Shell Scripts**  
| **Variable** | **Description** |
|------------|----------------|
| `$0` | Script name |
| `$1, $2, ...` | Positional arguments |
| `$#` | Number of arguments passed |
| `$@` | All arguments as separate words |
| `$*` | All arguments as a single string |
| `$$` | Process ID (PID) of the script |
| `$?` | Exit status of last command |

---

## **4️⃣ Conditional Statements in Shell Scripts**  
### **4.1 If-Else Statement**  
```sh
#!/bin/bash
echo "Enter a number:"
read num

if [ $num -gt 10 ]; then
    echo "Number is greater than 10"
else
    echo "Number is 10 or less"
fi
```

### **4.2 Case Statement**  
```sh
#!/bin/bash
echo "Enter a choice (start/stop/restart):"
read action

case $action in
  start) echo "Starting service...";;
  stop) echo "Stopping service...";;
  restart) echo "Restarting service...";;
  *) echo "Invalid option";;
esac
```

---

## **5️⃣ Loops in Shell Scripting**  
### **5.1 For Loop**  
```sh
#!/bin/bash
for i in {1..5}; do
    echo "Iteration $i"
done
```

### **5.2 While Loop**  
```sh
#!/bin/bash
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    ((count++))
done
```

---

## **6️⃣ Functions in Shell Scripts**  
Functions help reuse code and improve readability.  

```sh
#!/bin/bash
greet() {
    echo "Hello, $1!"
}

greet "DevOps Engineer"
```

---

## **7️⃣ File Handling in Shell Scripts**  
### **7.1 Reading a File**  
```sh
#!/bin/bash
while read line; do
    echo $line
done < filename.txt
```

### **7.2 Writing to a File**  
```sh
#!/bin/bash
echo "This is a log entry" >> logfile.txt
```

---

## **8️⃣ Process Management in Shell Scripting**  
### **8.1 Running a Command in the Background**  
```sh
some_command &
```
### **8.2 Killing a Process by Name**  
```sh
pkill -f process_name
```

---

## **9️⃣ Scheduling Shell Scripts (Cron Jobs)**  
### **9.1 Creating a Cron Job**  
Run `crontab -e` and add:  
```sh
0 3 * * * /path/to/script.sh   # Runs at 3 AM daily
```

### **9.2 Viewing Cron Jobs**  
```sh
crontab -l
```

---

## **🔟 Shell Scripting Use Cases in DevOps**  
🚀 **Automating server provisioning** (Ansible, Terraform).  
🚀 **Monitoring logs** and alerting (ELK, Prometheus).  
🚀 **Automating deployments** (CI/CD pipelines in Jenkins).  
🚀 **System backups** and database management.  
🚀 **Managing Docker containers & Kubernetes clusters.**  

---

## **🚀 Conclusion**  
Shell scripting is a **powerful tool** for **automating** tasks in Linux/Unix environments. It plays a crucial role in **DevOps, cloud infrastructure, and CI/CD pipelines**.  


