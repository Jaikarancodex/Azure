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
