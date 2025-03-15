# Azure Cloud Administration & Fundamentals

## 📌 Overview
Microsoft Azure is a cloud computing platform providing services such as computing, networking, storage, databases, security, and DevOps solutions. This guide covers Azure fundamentals, administration tasks, best practices, and learning resources.

---

## 1️⃣ Azure Cloud Fundamentals
### **1.1 What is Azure?**
Azure is a cloud platform offering **Infrastructure as a Service (IaaS), Platform as a Service (PaaS), and Software as a Service (SaaS)** solutions.

### **1.2 Core Azure Services**
| **Category**  | **Services** |
|--------------|-------------|
| Compute | Virtual Machines, App Services, AKS, Azure Functions |
| Storage | Blob Storage, Azure Files, Disk Storage |
| Networking | Virtual Networks, Load Balancer, NSG, ExpressRoute |
| Databases | Azure SQL, Cosmos DB, MySQL, PostgreSQL |
| Security | Azure AD, Key Vault, Security Center, Defender |
| Monitoring | Azure Monitor, Log Analytics, Application Insights |

---

## 2️⃣ Azure Identity & Access Management (IAM)
### **2.1 Azure Active Directory (Azure AD)**
Azure AD manages identity and access control, supporting **SSO, MFA, and Conditional Access**.

### **2.2 Role-Based Access Control (RBAC)**
| **Role** | **Permissions** |
|---------|---------------|
| Owner | Full access to all resources |
| Contributor | Can manage resources but not change access |
| Reader | View-only access |
| User Access Admin | Manages user access |

✅ **Best Practice:** Apply **Least Privilege Access (LPA)**.

---

## 3️⃣ Azure Compute Services
- **Virtual Machines (VMs)** – Windows & Linux VMs
- **Azure Kubernetes Service (AKS)** – Managed container orchestration
- **Azure Functions** – Serverless event-driven execution

✅ **Best Practices:**
- Use **Managed Disks** for reliability.
- Enable **Auto Shutdown** to reduce costs.
- Use **Availability Sets & Zones** for high availability.

---

## 4️⃣ Azure Networking
### **4.1 Virtual Networks & Components**
| **Component** | **Purpose** |
|--------------|------------|
| VNet | Secure network for Azure resources |
| NSG | Controls inbound/outbound traffic |
| Load Balancer | Distributes traffic efficiently |
| ExpressRoute | Private connection between on-prem and Azure |

✅ **Best Practices:**
- Use **NSGs & Firewalls** for security.
- Implement **DDoS Protection**.
- Use **VNet Peering** for inter-networking.

---

## 5️⃣ Azure Storage & Databases
### **5.1 Storage Services**
| **Storage Type** | **Description** |
|---------------|----------------|
| Blob Storage | Unstructured data like images and videos |
| File Storage | Managed SMB and NFS file shares |
| Table Storage | NoSQL key-value store |
| Queue Storage | Message queue for applications |

✅ **Best Practices:**
- Use **Lifecycle Policies** for cost optimization.
- Enable **Geo-Replication** for redundancy.
- Use **Azure Backup** for disaster recovery.

---

## 6️⃣ Security & Compliance
- **Azure Security Center** – Centralized security monitoring
- **Azure Sentinel** – Cloud-native SIEM for threat detection
- **Azure Key Vault** – Secure storage for secrets & keys

✅ **Security Best Practices:**
- Enable **MFA** for all users.
- Implement **Zero Trust Architecture**.
- Perform regular security audits.

---

## 7️⃣ Monitoring & Automation
- **Azure Monitor & Log Analytics** – Performance tracking & logs
- **Azure CLI & PowerShell** – Command-line automation
- **Terraform & ARM Templates** – Infrastructure as Code (IaC)

✅ **Monitoring Best Practices:**
- Set up **Kusto Query Language (KQL)** for log analysis.
- Use **Azure Alerts** for anomaly detection.

---

## 8️⃣ Azure DevOps & CI/CD
- **Azure DevOps** – Continuous integration & delivery (CI/CD)
- **Terraform & Bicep** – Automate infrastructure provisioning
- **GitHub Actions** – Workflow automation

✅ **Best Practices:**
- Use **Blue-Green Deployment** to minimize downtime.
- Implement **Azure Policy & Governance**.

---

## 9️⃣ Learning Path & Certifications
### **Recommended Certifications**
| **Cert** | **Level** | **Purpose** |
|---------|----------|-------------|
| AZ-900 | Beginner | Azure Fundamentals |
| AZ-104 | Intermediate | Azure Administrator |
| AZ-305 | Advanced | Azure Architect |
| AZ-500 | Security | Azure Security Engineer |
| AZ-400 | DevOps | Azure DevOps Engineer |

✅ **Learning Steps:**
1️⃣ Learn **Azure Basics** (IAM, Networking, Compute, Storage)
2️⃣ Practice **Azure CLI & PowerShell**
3️⃣ Set up **VMs, VNets, NSGs, and RBAC policies**
4️⃣ Explore **Backup, Disaster Recovery, and Monitoring**
5️⃣ Take **AZ-104** certification practice exams

---

## Conclusion
Mastering Azure Administration requires expertise in **identity management, security, networking, storage, compute, and automation**. By following best practices and obtaining relevant certifications, you can manage **scalable, secure, and high-performance** cloud environments.

