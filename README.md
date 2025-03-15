# Jenkins – CI/CD Automation Server

## 📌 What is Jenkins?
Jenkins is an **open-source automation server** used for **Continuous Integration (CI) and Continuous Deployment (CD)**. It automates **building, testing, and deploying** applications, making the DevOps process **faster, more reliable, and scalable**.

---

## **1️⃣ Key Features of Jenkins**
✅ **Open-source** and widely used in DevOps.  
✅ **Extensible** with 1800+ plugins.  
✅ **Distributed Builds** for scalability.  
✅ **Supports Various SCMs** (Git, SVN, etc.).  
✅ **Integrates with Tools** (Docker, Kubernetes, Ansible, Terraform).  
✅ **Pipeline as Code** using Groovy.  

---

## **2️⃣ Jenkins Architecture**  

### **2.1 Components of Jenkins**
| **Component** | **Description** |
|--------------|----------------|
| **Jenkins Master** | Controls and schedules jobs, distributes builds. |
| **Jenkins Agents (Nodes)** | Execute tasks on distributed machines. |
| **Jobs/Pipelines** | Define build/test/deploy workflows. |
| **Plugins** | Extend Jenkins functionalities (e.g., GitHub, Slack, Docker). |

### **2.2 How Jenkins Works**  
1. **Developers push code** to a repository (GitHub, GitLab, etc.).  
2. **Jenkins pulls code** from the repository.  
3. **Build triggers** (e.g., commit, schedule) start the process.  
4. **Jenkins runs tests** and builds the project.  
5. **Deployment** is automated using tools like Docker/Kubernetes.  

---

## **3️⃣ Installing Jenkins**  

### **3.1 Install on Ubuntu**  
```sh
sudo apt update
sudo apt install openjdk-11-jdk -y
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install jenkins -y
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

### **3.2 Access Jenkins Web Interface**  
Visit: `http://<server-ip>:8080`  
Retrieve the **admin password**:  
```sh
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

---

## **4️⃣ Jenkins Jobs & Pipelines**  

### **4.1 Create a Freestyle Job**  
1. Go to **Jenkins Dashboard** → **New Item**.  
2. Select **Freestyle project** and click **OK**.  
3. Configure **Source Code Management (SCM)** (Git URL).  
4. Define **Build Steps** (Shell script, Maven, Gradle).  
5. Save and **Build Now**.  

### **4.2 Create a Pipeline (Groovy Script)**  
1. **Go to Dashboard** → **New Item** → **Pipeline**.  
2. Paste the following **Jenkinsfile**:  
```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to production...'
            }
        }
    }
}
```
3. Click **Save & Build Now**.  

---

## **5️⃣ Jenkins Plugins**  
Install plugins to extend Jenkins functionalities.  

| **Plugin** | **Purpose** |
|------------|------------|
| Git Plugin | Integrates with Git repositories |
| Docker Plugin | Builds and deploys Docker containers |
| Kubernetes Plugin | Automates Kubernetes deployments |
| Slack Plugin | Sends notifications to Slack |
| Ansible Plugin | Runs Ansible playbooks in Jenkins pipelines |

To install:  
- Go to **Manage Jenkins** → **Manage Plugins** → **Available** → Search & Install.  

---

## **6️⃣ Jenkins Best Practices**  
✅ **Use Pipelines as Code** (Jenkinsfile for version control).  
✅ **Run Jenkins in Docker** for easy deployment.  
✅ **Use Agents** for distributed builds.  
✅ **Automate Backups** of Jenkins configurations.  
✅ **Secure Jenkins** (RBAC, SSL, restricted access).  

---

## **🔟 Jenkins Use Cases**  
🚀 **CI/CD Pipelines** – Automate build, test, deploy.  
🚀 **Infrastructure as Code** – Automate Terraform/Ansible.  
🚀 **Monitoring & Alerts** – Integrate with Prometheus/Grafana.  
🚀 **Cloud Deployments** – AWS, Azure, Kubernetes.  

---

## **🚀 Conclusion**  
Jenkins is a powerful **CI/CD automation tool** that helps DevOps teams **automate software development, testing, and deployment**. Whether you're managing **bare-metal servers, virtual machines, or cloud-native environments**, Jenkins simplifies workflows and increases efficiency.  

