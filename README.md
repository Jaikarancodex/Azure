# 🌐 Azure

# 💥 Core Azure Architectural Components

## 1.1 Regions, Availability Zones, Resource Groups

### **Azure Region**
A Region is a geographical area containing one or more datacenters.  
Used for: low latency, compliance, disaster recovery.

### **Availability Zones (AZs)**
Physically separate datacenters within the same region.  
Each zone has independent power, cooling, networking.  
Provides high availability.

### **Resource Groups (RGs)**
A logical container for Azure resources.  
Used for organizing, managing permissions, applying policies.

---

## 1.2 Azure Resource Manager (ARM)

**ARM (Azure Resource Manager)** is the deployment and management layer of Azure.

Functions:
- Deploys, updates, and deletes resources
- Provides Role-Based Access Control (RBAC)
- Uses ARM templates for Infrastructure as Code
- Ensures consistent deployment

---

## 1.3 Azure Compute Options

### **Virtual Machines (VMs)**
Full control over OS, networking, runtime.

### **App Services**
Platform-as-a-Service (PaaS) for hosting web apps, APIs.

### **Containers**
Lightweight, portable compute.  
Azure services: ACI, AKS.

### **Azure Functions**
Serverless compute.  
Pay-per-execution.

---

# 💥 RBAC – Role-Based Access Control

RBAC controls:
- **WHO** (Security Principal)
- **WHAT** (Role Definition)
- **WHERE** (Scope)

### Security Principal (WHO?)
- User
- Group
- Service Principal
- Managed Identity

### Role Definitions (WHAT?)
- Owner
- Contributor
- Reader
- VM Contributor
- Storage Blob Reader

### Scope (WHERE?)
- Management Group
- Subscription
- Resource Group
- Resource

### Example:
Assign “VM Contributor” to a Developer at Resource Group level →  
They can manage VMs but cannot modify permissions or access other services.

---

# 💥 Cloud Concepts

## 2.1 IaaS, PaaS, SaaS (Service Models)

### 2.1.1 IaaS — Infrastructure as a Service
You manage the OS, apps, and runtime. The cloud provides hardware.

Examples:
- Virtual Machines (VMs)
- Virtual Networks (VNet)
- Load Balancers
- Disks & Storage

Use Case:
Full control over servers.

---

### 2.1.2 PaaS — Platform as a Service
Cloud provides the platform; you manage only the application.

Examples:
- Azure App Services
- Azure SQL Database
- Azure Functions
- Azure Kubernetes Service (AKS)

Use Case:
Focus on code, not servers.

---

### 2.1.3 SaaS — Software as a Service
Fully managed applications delivered over the internet.

Examples:
- Microsoft 365
- Dynamics 365
- Outlook.com
- Teams

Use Case:
End users consume the application directly.

---

## 2.2 Cloud Deployment Models

### Public Cloud
Services delivered via the internet; shared physical hardware.

Examples:
- Azure
- AWS
- Google Cloud

Pros: Low cost, scalable  
Cons: Less isolation

---

### Private Cloud
Dedicated cloud environment for one organization.

Examples:
- On-prem datacenter (VMware, Hyper‑V)
- Azure Stack Hub

Pros: Maximum control  
Cons: Expensive

---

### Hybrid Cloud
Mix of public + private cloud.

Examples:
- On‑prem + Azure connected via VPN/ExpressRoute

Pros: Flexible, compliant  
Use Case: Banking, healthcare, govt.

---

## 2.3 CapEx vs OpEx

### CapEx — Capital Expenditure
Upfront investment in physical assets.

Examples:
- Buying servers
- Datacenter hardware
- Power & cooling

Characteristics:
- One‑time large cost
- You maintain everything

---

### OpEx — Operational Expenditure
Pay‑as‑you‑go cloud billing.

Examples:
- Azure VM hourly cost
- Storage, network, databases

---

# 💥 Azure Compute Services

## 3.1 Virtual Machines (VMs)

### 3.1.1 VM Sizing, Pricing, and Scaling
- **VM Sizing:** Choose CPU, RAM, storage, and GPU based on workloads.  
  Examples: B-series (basic), D-series (general purpose), F-series (compute optimized), NV-series (GPU).

- **Pricing:** Pay per second/minute depending on VM type.  
  Factors affecting cost: size, OS type, region, storage, networking.

- **Scaling:**  
  - **Manual scaling:** Increase or decrease VM count manually.  
  - **Auto-scale:** Automatically adds/removes VMs based on CPU/memory rules using **Scale Sets**.

---

### 3.1.2 VM Deployment and Management
- Deploy via **Azure Portal**, **Azure CLI**, **ARM Templates**, or **Terraform**.  
- Management includes:  
  - Start/stop/restart  
  - OS patching  
  - Disk management  
  - Networking (VNet, NSG, Public IP)  
  - Backup and monitoring using Azure Monitor

---

## 3.2 Azure App Services
A fully managed **Platform-as-a-Service (PaaS)** for hosting:
- Web apps  
- Mobile backends  
- REST APIs  

Features:
- Auto-scaling  
- Deployment slots  
- CI/CD integration  
- Custom domains & SSL  
- Built-in authentication

---

## 3.3 Azure Functions
A **serverless compute** service.  
You run small pieces of code (functions) that trigger on:
- HTTP requests  
- Timers  
- Queue messages  
- Blob uploads  

Benefits:
- No server management  
- Pay only per execution  
- Auto-scaling  
- Great for event-driven workflows

---

## 3.4 Azure Kubernetes Service (AKS)
A managed Kubernetes orchestration service.

Features:
- Automated upgrades  
- Scaling & self-healing  
- Containerized application deployment  
- Integration with monitoring & CI/CD  
- Node pools and GPU support

Use Cases:
- Microservices  
- Large-scale containerized applications

---

## 3.5 Cloud Service Models
### IaaS — Infrastructure as a Service
Virtual Machines, Networking, Storage.

### PaaS — Platform as a Service
App Services, Azure SQL, AKS (partially).

### SaaS — Software as a Service
Microsoft 365, Dynamics 365, Outlook.com.

Cloud service models determine **how much control** vs **how much management** the cloud handles.



Characteristics:
- No upfront cost
- Scales with usage
- Cloud provider maintains infra
