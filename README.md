# Ansible – Overview & Fundamentals

## 📌 What is Ansible?
Ansible is an **open-source automation tool** used for **configuration management, application deployment, orchestration, and infrastructure automation**. It follows an **agentless architecture**, using SSH or WinRM for communication with remote machines.

---

## **1️⃣ Key Features of Ansible**
✅ **Agentless:** No need to install an agent on managed nodes.  
✅ **Idempotent:** Ensures consistency by only applying necessary changes.  
✅ **Declarative & Procedural:** Supports both declarative (desired state) and procedural (step-by-step) approaches.  
✅ **Scalable:** Manages thousands of nodes efficiently.  
✅ **Extensible:** Supports **modules, roles, and plugins** for custom automation.  
✅ **Secure:** Uses **YAML-based Playbooks** and SSH encryption.

---

## **2️⃣ Ansible Architecture**  

### **2.1 Components of Ansible**
| **Component** | **Description** |
|--------------|----------------|
| **Control Node** | The system where Ansible is installed and run. |
| **Managed Nodes** | The remote machines configured by Ansible. |
| **Inventory** | A list of managed nodes (hosts) defined in a file. |
| **Playbook** | A YAML file that defines automation tasks. |
| **Modules** | Predefined functions that perform tasks like package installation, service management, etc. |
| **Roles** | A structured way to organize playbooks for reusability. |
| **Plugins** | Extend Ansible's functionality (e.g., callback, connection, lookup). |

---

## **3️⃣ Ansible Installation**  
Ansible can be installed on **Linux/macOS** (Windows requires WSL).  

### **3.1 Install on Ubuntu**  
```sh
sudo apt update
sudo apt install ansible -y
```

### **3.2 Install on RHEL/CentOS**  
```sh
sudo yum install epel-release -y
sudo yum install ansible -y
```

### **3.3 Verify Installation**  
```sh
ansible --version
```

---

## **4️⃣ Ansible Inventory & Configuration**  

### **4.1 Inventory File (`/etc/ansible/hosts`)**  
Defines managed nodes (hosts) in a simple text file.  
Example:  
```ini
[webservers]
web1.example.com
web2.example.com

[dbservers]
db1.example.com ansible_user=root ansible_host=192.168.1.10
```

### **4.2 Test Connectivity**  
```sh
ansible all -m ping
```

✅ **Expected Output:**  
```json
web1.example.com | SUCCESS => {"ping": "pong"}
```

---

## **5️⃣ Writing Ansible Playbooks**  

### **5.1 Basic Playbook Structure**  
```yaml
---
- name: Install Nginx on Web Servers
  hosts: webservers
  become: yes  # Run as root
  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present
```

### **5.2 Run the Playbook**
```sh
ansible-playbook nginx_install.yml
```

---

## **6️⃣ Ansible Modules**  
Modules are built-in functions that automate tasks.

| **Module** | **Purpose** | **Example** |
|------------|------------|-------------|
| `ping` | Checks connectivity | `ansible all -m ping` |
| `copy` | Copies files | `copy: src=/file dest=/etc/file` |
| `service` | Manages services | `service: name=nginx state=started` |
| `package` | Installs packages | `package: name=git state=present` |
| `user` | Creates users | `user: name=devops state=present` |

---

## **7️⃣ Ansible Roles (For Large Projects)**  
Roles allow **modular automation** by organizing tasks, handlers, variables, templates, and files.

### **7.1 Create a Role**  
```sh
ansible-galaxy init myrole
```

### **7.2 Role Directory Structure**  
```sh
myrole/
├── tasks/
│   ├── main.yml
├── handlers/
│   ├── main.yml
├── templates/
├── files/
├── vars/
│   ├── main.yml
├── defaults/
│   ├── main.yml
```

### **7.3 Use a Role in a Playbook**  
```yaml
---
- hosts: webservers
  roles:
    - myrole
```

---

## **8️⃣ Ansible Vault (Encrypt Sensitive Data)**  
Ansible Vault secures passwords, keys, and sensitive data.

### **8.1 Create an Encrypted File**
```sh
ansible-vault create secrets.yml
```

### **8.2 Encrypt an Existing File**  
```sh
ansible-vault encrypt secrets.yml
```

### **8.3 Decrypt a File**
```sh
ansible-vault decrypt secrets.yml
```

### **8.4 Run a Playbook with Vault**
```sh
ansible-playbook secure_playbook.yml --ask-vault-pass
```

---

## **9️⃣ Ansible Best Practices**
✅ **Use Roles** for better organization.  
✅ **Store Inventory Separately** (e.g., dynamic inventory for cloud environments).  
✅ **Use Ansible Vault** for sensitive data.  
✅ **Test Playbooks** in a staging environment before production.  
✅ **Use `ansible-lint`** to check for syntax errors.

---

## **🔟 Ansible Use Cases**
🚀 **Server Provisioning** – Automate infrastructure setup.  
🚀 **Configuration Management** – Ensure consistent server configurations.  
🚀 **CI/CD Pipelines** – Automate software deployments.  
🚀 **Cloud Management** – Manage AWS, Azure, GCP instances.  
🚀 **Security Automation** – Enforce compliance policies.  

---

## **📌 Learning Path & Certifications**
🎯 **Practice Commands:** Use `ansible-doc -l` to explore modules.  
🎯 **Hands-on Labs:** Set up a test environment with VMs.  
🎯 **Certifications:**  
- **Red Hat Certified Engineer (RHCE)** – Focus on Ansible automation.  
- **Ansible for DevOps** (Free resources available on GitHub).  

---

## **Conclusion**
Ansible is a powerful tool for **automation, configuration management, and orchestration**. Whether managing **bare-metal servers, virtual machines, or cloud environments**, Ansible simplifies workflows and improves **efficiency**.

