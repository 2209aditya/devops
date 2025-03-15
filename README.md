# Docker – A Complete Guide 🐳  

## **📌 What is Docker?**  
Docker is an **open-source containerization platform** that allows developers and DevOps engineers to package applications and their dependencies into **lightweight, portable containers**. These containers can run consistently across different environments, eliminating the "it works on my machine" problem.  

---

## **1️⃣ Why Use Docker?**  
✅ **Lightweight & Fast** – Containers share the host OS, unlike virtual machines.  
✅ **Portable** – Works across different environments (local, cloud, CI/CD pipelines).  
✅ **Scalable** – Easily scale applications up or down.  
✅ **Efficient Resource Usage** – Runs multiple applications without extra OS overhead.  
✅ **Isolation** – Each container runs independently, preventing conflicts.  

---

## **2️⃣ Key Docker Components**  
### **2.1 Docker Engine**  
The core component that runs and manages containers.  

### **2.2 Docker Images**  
A **read-only template** that contains everything needed to run an application (OS, dependencies, code).  

### **2.3 Docker Containers**  
A **runtime instance** of a Docker image, similar to a lightweight virtual machine.  

### **2.4 Docker Hub**  
A cloud-based registry where pre-built Docker images are stored and shared.  

### **2.5 Dockerfile**  
A script with instructions to build a Docker image.  

---

## **3️⃣ Installing Docker**  
### **On Ubuntu**  
```sh
sudo apt update
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
docker --version
```

### **On CentOS**  
```sh
sudo yum install -y docker
sudo systemctl start docker
sudo systemctl enable docker
```

### **On Windows & Mac**  
Download **Docker Desktop** from [Docker's official website](https://www.docker.com/get-started).  

---

## **4️⃣ Basic Docker Commands**  
### **4.1 Check Docker Installation**  
```sh
docker --version       # Check installed Docker version
docker info            # Display system-wide Docker info
```

### **4.2 Managing Containers**  
```sh
docker run hello-world     # Run a test container
docker ps                  # List running containers
docker ps -a               # List all containers
docker stop <container_id>  # Stop a running container
docker rm <container_id>    # Remove a stopped container
docker logs <container_id>  # View logs of a container
```

### **4.3 Working with Images**  
```sh
docker images                      # List downloaded images
docker pull nginx                   # Download an image from Docker Hub
docker rmi <image_id>               # Remove an image
```

### **4.4 Running Containers**  
```sh
docker run -d -p 8080:80 nginx      # Run an Nginx container in detached mode
docker exec -it <container_id> bash # Access a running container's shell
```

### **4.5 Building Custom Images**  
Create a **Dockerfile**:  
```dockerfile
FROM ubuntu:latest
RUN apt update && apt install -y nginx
CMD ["nginx", "-g", "daemon off;"]
```
Build and run the image:  
```sh
docker build -t my-nginx .
docker run -d -p 8080:80 my-nginx
```

---

## **5️⃣ Docker Compose – Multi-Container Management**  
Docker Compose allows defining and running multi-container applications using a `docker-compose.yml` file.  

### **Example: Running a Web App with a Database**  
Create `docker-compose.yml`:  
```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: example
```
Run the stack:  
```sh
docker-compose up -d
docker-compose ps
docker-compose down
```

---

## **6️⃣ Docker Volumes – Persistent Storage**  
By default, Docker containers are **ephemeral** (data is lost when a container stops). Volumes provide **persistent storage**.  

### **Creating and Using a Volume**  
```sh
docker volume create mydata
docker run -d -v mydata:/app busybox
docker volume ls
docker volume inspect mydata
docker volume rm mydata
```

---

## **7️⃣ Docker Networking**  
Docker provides **three types of networks**:  
- **Bridge** (default) – For communication between containers on the same host.  
- **Host** – Shares the host's network namespace.  
- **None** – No network (for isolated containers).  

### **Creating a Custom Network**  
```sh
docker network create my_network
docker run -d --network=my_network --name=my_container nginx
docker network ls
docker network inspect my_network
```

---

## **8️⃣ Docker in DevOps & CI/CD**  
🚀 **Continuous Integration (CI)** – Build, test, and deploy using Docker images.  
🔄 **Continuous Deployment (CD)** – Automate production deployments.  
⚙ **Infrastructure as Code (IaC)** – Define infrastructure using Docker Compose or Kubernetes.  

Example **Jenkins + Docker Pipeline**:  
```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t myapp .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 8080:80 myapp'
            }
        }
    }
}
```

---

## **9️⃣ Kubernetes vs Docker**  
| **Feature**   | **Docker**  | **Kubernetes**  |
|--------------|------------|---------------|
| Purpose | Containerization | Orchestration |
| Scaling | Manual | Automatic |
| Networking | Simple | Advanced |
| Load Balancing | Limited | Built-in |

**Note:** Docker itself does **not replace Kubernetes**; instead, Kubernetes manages and orchestrates multiple Docker containers in a **production environment**.  

---

## **🔟 Conclusion**  
Docker is a **powerful containerization tool** that revolutionizes how applications are developed, tested, and deployed. It enables **fast, consistent, and scalable application management** across different environments.  


