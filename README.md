# Kubernetes – A Complete Guide 🚀

## **📌 What is Kubernetes?**  
Kubernetes (K8s) is an **open-source container orchestration platform** that automates the **deployment, scaling, and management** of containerized applications. It enables running applications efficiently across **clusters of machines**.

🔹 Developed by Google, now maintained by **Cloud Native Computing Foundation (CNCF)**.  
🔹 Works with **Docker**, **containerd**, and other container runtimes.  

---

## **1️⃣ Why Use Kubernetes?**  
✅ **Automated Deployment & Scaling** – Auto-scales apps based on traffic.  
✅ **Self-Healing** – Restarts failed containers automatically.  
✅ **Load Balancing** – Distributes traffic among containers.  
✅ **Rolling Updates & Rollbacks** – Zero-downtime deployments.  
✅ **Service Discovery** – Containers can find each other easily.  
✅ **Multi-Cloud & Hybrid Support** – Works on AWS, Azure, GCP, or on-prem.  

---

## **2️⃣ Kubernetes Architecture**  
Kubernetes follows a **Master-Worker** architecture.  

### **2.1 Master Node (Control Plane) Components**  
🖥️ **API Server** – Entry point for all Kubernetes commands.  
🖥️ **Scheduler** – Assigns workloads (pods) to worker nodes.  
🖥️ **Controller Manager** – Ensures desired state is maintained.  
🖥️ **ETCD** – Distributed key-value store (stores cluster data).  

### **2.2 Worker Node Components**  
🔹 **Kubelet** – Talks to the master, runs pods on the node.  
🔹 **Container Runtime** – Runs containers (Docker, containerd, etc.).  
🔹 **Kube Proxy** – Manages networking and service discovery.  

---

## **3️⃣ Installing Kubernetes (Minikube for Local Testing)**  
### **Step 1: Install Minikube & kubectl**  
```sh
curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube-linux-amd64
sudo mv minikube-linux-amd64 /usr/local/bin/minikube
```

### **Step 2: Start Minikube Cluster**  
```sh
minikube start
kubectl get nodes
```

---

## **4️⃣ Key Kubernetes Concepts**  
### **4.1 Pods** 🛑  
- The smallest deployable unit in Kubernetes.  
- A pod can contain **one or more containers**.  

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  containers:
    - name: nginx-container
      image: nginx
```

Deploy the pod:  
```sh
kubectl apply -f pod.yaml
kubectl get pods
kubectl describe pod my-pod
```

### **4.2 Deployments** 🚀  
- Manages multiple replicas of a pod for high availability.  
- Ensures **zero-downtime updates**.  

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
        - name: nginx
          image: nginx
```

Apply the deployment:  
```sh
kubectl apply -f deployment.yaml
kubectl get deployments
kubectl scale deployment my-deployment --replicas=5
```

### **4.3 Services** 🌐  
- Exposes pods to the outside world or other pods.  

```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  selector:
    app: myapp
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: NodePort  # Exposes service on a random high port
```

Deploy the service:  
```sh
kubectl apply -f service.yaml
kubectl get services
```

---

## **5️⃣ Kubernetes Scaling & Autoscaling**  
🔹 **Manual Scaling**  
```sh
kubectl scale deployment my-deployment --replicas=10
```

🔹 **Horizontal Pod Autoscaler (HPA)**  
Automatically scales pods based on CPU usage.  
```sh
kubectl autoscale deployment my-deployment --cpu-percent=50 --min=2 --max=10
```

Check HPA status:  
```sh
kubectl get hpa
```

---

## **6️⃣ Kubernetes Logging & Monitoring**  
🔹 **Get Pod Logs**  
```sh
kubectl logs my-pod
kubectl logs -f my-pod   # Live logs
```

🔹 **Describe a Pod (Debugging)**  
```sh
kubectl describe pod my-pod
```

🔹 **Monitor Cluster Metrics**  
Install **metrics-server** for resource monitoring.  
```sh
kubectl top nodes
kubectl top pods
```

---

## **7️⃣ Kubernetes in DevOps (CI/CD)**  
Kubernetes is widely used in CI/CD pipelines.  
Example: **Jenkins + Kubernetes Deployment**  
```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t myapp .'
                sh 'docker push myapp'
            }
        }
        stage('Deploy') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
            }
        }
    }
}
```

---

## **8️⃣ Kubernetes vs Docker Swarm**  
| Feature | Kubernetes | Docker Swarm |
|---------|-----------|--------------|
| Scaling | Auto-scaling | Manual Scaling |
| Load Balancing | Built-in | Needs manual setup |
| Self-healing | Yes | No |
| Networking | Complex but powerful | Simple |

---

## **🔟 Conclusion**  
Kubernetes is the **gold standard** for managing **containerized applications at scale**. It offers **self-healing, auto-scaling, and high availability**, making it ideal for **cloud-native** applications.  


