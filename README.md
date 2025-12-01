# 🌐 Azure

# 💥 Core Azure Architectural Components

## ✔  1.1 Regions, Availability Zones, Resource Groups

### 🔹 **Azure Region**
A Region is a geographical area containing one or more datacenters.  
Used for: low latency, compliance, disaster recovery.

### 🔹  **Availability Zones (AZs)**
Physically separate datacenters within the same region.  
Each zone has independent power, cooling, networking.  
Provides high availability.

### 🔹  **Resource Groups (RGs)**
A logical container for Azure resources.  
Used for organizing, managing permissions, applying policies.

---

## ✔  1.2 Azure Resource Manager (ARM)

**ARM (Azure Resource Manager)** is the deployment and management layer of Azure.

Functions:
- Deploys, updates, and deletes resources
- Provides Role-Based Access Control (RBAC)
- Uses ARM templates for Infrastructure as Code
- Ensures consistent deployment

---

## ✔  1.3 Azure Compute Options

### 🔹**Virtual Machines (VMs)**
Full control over OS, networking, runtime.

### 🔹 **App Services**
Platform-as-a-Service (PaaS) for hosting web apps, APIs.

### 🔹 **Containers**
Lightweight, portable compute.  
Azure services: ACI, AKS.

### 🔹 **Azure Functions**
Serverless compute.  
Pay-per-execution.

---

# 💥 RBAC – Role-Based Access Control

RBAC controls:
- **WHO** (Security Principal)
- **WHAT** (Role Definition)
- **WHERE** (Scope)

### 🔹 Security Principal (WHO?)
- User
- Group
- Service Principal
- Managed Identity

### 🔹 Role Definitions (WHAT?)
- Owner
- Contributor
- Reader
- VM Contributor
- Storage Blob Reader

### 🔹 Scope (WHERE?)
- Management Group
- Subscription
- Resource Group
- Resource

### Example:
Assign “VM Contributor” to a Developer at Resource Group level →  
They can manage VMs but cannot modify permissions or access other services.

---

# 💥 Cloud Concepts

## ✔  2.1 IaaS, PaaS, SaaS (Service Models)

### 🔹 2.1.1 IaaS — Infrastructure as a Service
You manage the OS, apps, and runtime. The cloud provides hardware.

 Examples:
- Virtual Machines (VMs)
- Virtual Networks (VNet)
- Load Balancers
- Disks & Storage

 Use Case:
Full control over servers.

---

### 🔹 2.1.2 PaaS — Platform as a Service
Cloud provides the platform; you manage only the application.

Examples:
- Azure App Services
- Azure SQL Database
- Azure Functions
- Azure Kubernetes Service (AKS)

Use Case:
Focus on code, not servers.

---

### 🔹 2.1.3 SaaS — Software as a Service
Fully managed applications delivered over the internet.

Examples:
- Microsoft 365
- Dynamics 365
- Outlook.com
- Teams

Use Case:
End users consume the application directly.

---

## ✔  2.2 Cloud Deployment Models

### 🔹 Public Cloud
Services delivered via the internet; shared physical hardware.

Examples:
- Azure
- AWS
- Google Cloud

Pros: Low cost, scalable  
Cons: Less isolation

---

### 🔹 Private Cloud
Dedicated cloud environment for one organization.

Examples:
- On-prem datacenter (VMware, Hyper‑V)
- Azure Stack Hub

Pros: Maximum control  
Cons: Expensive

---

### 🔹 Hybrid Cloud
Mix of public + private cloud.

Examples:
- On‑prem + Azure connected via VPN/ExpressRoute

Pros: Flexible, compliant  
Use Case: Banking, healthcare, govt.

---

## ✔ 2.3 CapEx vs OpEx

### 🔹 CapEx — Capital Expenditure
Upfront investment in physical assets.

Examples:
- Buying servers
- Datacenter hardware
- Power & cooling

Characteristics:
- One‑time large cost
- You maintain everything

---

### 🔹 OpEx — Operational Expenditure
Pay‑as‑you‑go cloud billing.

Examples:
- Azure VM hourly cost
- Storage, network, databases

---

# 💥 Azure Compute Services

## ✔  3.1 Virtual Machines (VMs)

###  🔹 3.1.1 VM Sizing, Pricing, and Scaling
- **VM Sizing:** Choose CPU, RAM, storage, and GPU based on workloads.  
  Examples: B-series (basic), D-series (general purpose), F-series (compute optimized), NV-series (GPU).

- **Pricing:** Pay per second/minute depending on VM type.  
  Factors affecting cost: size, OS type, region, storage, networking.

- **Scaling:**  
  - **Manual scaling:** Increase or decrease VM count manually.  
  - **Auto-scale:** Automatically adds/removes VMs based on CPU/memory rules using **Scale Sets**.

---

### 🔹 3.1.2 VM Deployment and Management
- Deploy via **Azure Portal**, **Azure CLI**, **ARM Templates**, or **Terraform**.  
- Management includes:  
  - Start/stop/restart  
  - OS patching  
  - Disk management  
  - Networking (VNet, NSG, Public IP)  
  - Backup and monitoring using Azure Monitor

---

## ✔  3.2 Azure App Services
🔹 A fully managed **Platform-as-a-Service (PaaS)** for hosting:
- Web apps  
- Mobile backends  
- REST APIs  

🔹 Features:
- Auto-scaling  
- Deployment slots  
- CI/CD integration  
- Custom domains & SSL  
- Built-in authentication

---

##  ✔  3.3 Azure Functions
🔹 A **serverless compute** service.  
You run small pieces of code (functions) that trigger on:
- HTTP requests  
- Timers  
- Queue messages  
- Blob uploads  

🔹 Benefits:
- No server management  
- Pay only per execution  
- Auto-scaling  
- Great for event-driven workflows

---

##  ✔  3.4 Azure Kubernetes Service (AKS)
A managed Kubernetes orchestration service.

🔹 Features:
- Automated upgrades  
- Scaling & self-healing  
- Containerized application deployment  
- Integration with monitoring & CI/CD  
- Node pools and GPU support

🔹 Use Cases:
- Microservices  
- Large-scale containerized applications

---

##  ✔ 3.5 Cloud Service Models
### 🔹 IaaS — Infrastructure as a Service
Virtual Machines, Networking, Storage.

### 🔹 PaaS — Platform as a Service
App Services, Azure SQL, AKS (partially).

### 🔹 SaaS — Software as a Service
Microsoft 365, Dynamics 365, Outlook.com.

Cloud service models determine **how much control** vs **how much management** the cloud handles.

Characteristics:
- No upfront cost
- Scales with usage
- Cloud provider maintains infra

---

# 💥  Azure Storage Services

Azure Storage provides scalable, durable, secure cloud storage for apps and data.  
This document covers:

- **4.1 Blob Storage**
- **4.2 Storage Tiers & Replication**
- **4.3 Access Control & Shared Access Signatures (SAS)**

---

## 4.1 Blob Storage

Blob = **Binary Large Object** → used for storing unstructured data.

### 🔹 What can you store?
- Images, videos, PDFs
- Application logs
- Backups
- Website static content

### ⚡ Blob Storage Types
| Blob Type | Purpose |
|----------|----------|
| **Block Blob** | General files (images, videos, docs). Most common. |
| **Append Blob** | Optimized for logs where data is appended. |
| **Page Blob** | Used for **Azure VM disks**. |

### 🔹 Storage Structure
 
- **Storage Account** = parent container  
- **Container** = folder  
- **Blob** = actual file  

---

## ✔ 4.2 Storage Tiers & Replication

### 🔹 A. Storage Tiers (Performance + Cost Levels)

Azure offers three tiers based on how often you access data:

| Tier | When to Use | Cost |
|------|-------------|------|
| **Hot Tier** | Frequently accessed data | Higher storage cost, low access cost |
| **Cool Tier** | Infrequently accessed (≥ 30 days) | Lower storage cost |
| **Archive Tier** | Rarely accessed (≥ 180 days) | Lowest storage cost, highest access cost |

---

### 🔹 B. Replication (Data Protection & Durability)

Replication determines how many **copies** of your data exist and **where** they are stored.

| Replication Type | Meaning | No. of Copies | Location |
|------------------|----------|----------------|----------|
| **LRS** (Locally Redundant Storage) | 3 copies in **one** datacenter | 3 | 1 AZ |
| **ZRS** (Zone Redundant Storage) | Copies across **three AZs** | 3 | Same region |
| **GRS** (Geo‑Redundant Storage) | LRS + copy to secondary region | 6 | Two regions |
| **GZRS** (Geo‑Zone Redundant Storage) | ZRS + geo copy | 6 | Multi‑AZ + DR region |

### 🔹 Replication Summary
- **LRS** → Cheapest, single data center  
- **ZRS** → Protects against AZ failure  
- **GRS** → Protects against regional disaster  
- **GZRS** → Highest durability + geo + zone redundancy  

---

## ✔ 4.3 Access Control & SAS (Shared Access Signatures)

### 🔹A. Access Control Options

#### 1. Role-Based Access Control (RBAC)
Controls **who** can access the storage account at the Azure level.

Common roles:
- Storage Blob Reader  
- Storage Blob Contributor  
- Storage Blob Owner  

#### 2. ACLs (Access Control Lists)
Set permissions on:
- Containers
- Directories
- Specific blobs  

Useful for granular permissions.

---

### 🔹 B. SAS — Shared Access Signature

SAS = **Temporary secure link** that grants limited access to storage resources **without exposing account keys**.

### 🔹 SAS lets you control:
- **What** → read, write, delete, list  
- **Where** → specific blob or container  
- **When** → expiry times  
- **How** → IP restrictions, HTTPS only  

### 🔹 Types of SAS:
| SAS Type | Description |
|----------|-------------|
| **User Delegation SAS** | Generated with Azure AD identity (most secure) |
| **Service SAS** | Access to specific storage service (Blob/File/Queue/Table) |
| **Account SAS** | Broad access across services in an account |

### 🔹  Example Use Case
You want to allow a client to download a file for **1 hour**:
1. Generate a **read‑only SAS URL**  
2. Send it  
3. Access expires automatically  

---

##  ✔  Quick Revision Summary

- **Blob Storage** stores unstructured data (block, append, page).  
- **Tiers:** Hot → Cool → Archive (cost decreases, latency increases).  
- **Replication:** LRS < ZRS < GRS < GZRS (in durability).  
- **SAS:** Gives temporary, restricted access without sharing account keys.

---

# 💥 Azure Key Vault, Azure Functions, Azure Logic Apps

## ✔  1. Azure Key Vault

A secure service to store:
- Secrets  
- Passwords  
- Keys  
- Certificates  

### 🔹 Why We Use It
- Prevent hardcoding secrets in code  
- Protect sensitive information  
- Centralized key and secret management  

### 🎯 Definition
Azure Key Vault securely stores and manages secrets, keys, and certificates to prevent sensitive data exposure.

---

## ✔  2. Azure Functions

A serverless compute service that runs code only when triggered.

### 🔹 What It Does
- Executes code based on events  
- Auto-scales automatically  
- Pay only when it runs  

### 🎯 Definition
Azure Functions is an event-driven serverless compute platform that runs code automatically when triggered, with auto-scaling and pay-per-use pricing.

---

## ✔  3. Azure Logic Apps

A no‑code workflow automation and integration service.

### 🔹 What It Does
- Connects services together  
- Automates workflows  
- Integrates apps like Teams, SAP, SQL, Gmail, Salesforce  

### 🔹 Examples
- When an email arrives → upload attachment to Blob  
- When a file lands in Storage → send notification  
- Scheduled jobs without writing code  

### 🎯 Definition
Azure Logic Apps is a no-code integration and workflow automation service that connects systems and automates business processes.

---

## ⚡ How They Work Together

- **Logic Apps** → orchestrate workflows  
- **Functions** → run custom code inside the workflow  
- **Key Vault** → securely store secrets used by both  

### 🔹 Example Flow
A Logic App triggers → calls Azure Function → Function retrieves a secret from Key Vault.

---

# 💥 Azure Data Factory (ADF)

ADF = Azure’s **ETL / ELT orchestration service**.
It **moves**, **copies**, and **transforms** data between systems.

Think of it like **Databricks Workflows + Copy tool + Orchestrator** in one place.

## ✔ **6.1.1 Data Ingestion & Transformation – What Actually Happens**

### 🔹 ** Data Ingestion (Copying Data)**

ADF ingests data from:

* On-prem SQL Server
* Azure SQL
* Blob Storage
* Data Lake
* SaaS apps (Salesforce, Dynamics)
* REST APIs
* File shares, SFTP

The main tool used here is **Copy Activity**.

It reads from **Source** → writes to **Sink (destination)**.

### 🔹 Example

Copy data from **SQL Server** to **Azure Data Lake** every 1 hour.

* Source: On-prem SQL
* Sink: ADLS Gen2
* Integration Runtime handles connectivity

---

### ** 🔹 Data Transformation Options in ADF**

ADF itself is NOT a compute engine (except Data Flows).
It triggers external compute like:

| Tool                            | When used                                                       |
| ------------------------------- | --------------------------------------------------------------- |
| **Mapping Data Flow**           | Drag-and-drop transformations (joins, filters, derived columns) |
| **Databricks Notebook**         | Big data transforms using Spark                                 |
| **Azure SQL Stored Procedures** | Small transformations in SQL                                    |
| **Azure Functions**             | Custom logic                                                    |
| **HDInsight / Synapse**         | Big analytics workloads                                         |

---

### 🔹  Simple Example

You want to clean sales data:

* Read raw CSV
* Filter invalid rows
* Add new calculated columns
* Write cleaned data to ADLS

→ Use **Mapping Data Flow** or trigger a **Databricks notebook**.

---

## ✔ **6.1.2 Pipelines & Activities – Backbone of ADF**

### 🔹 What is a Pipeline?

Pipeline = **container for your workflow**.
A pipeline holds a sequence of steps (activities) to run.

Think of it like:
📦 *A folder that contains all tasks to move or transform your data.*

---

### 🔹 What is an Activity?

Activity = **one task** inside a pipeline.

### 🔹 Types of Activities

| Category                | Examples                               |
| ----------------------- | -------------------------------------- |
| **Data movement**       | Copy Activity                          |
| **Data transformation** | Mapping Data Flow, Databricks Notebook |
| **Control**             | If, ForEach, Wait, Switch              |
| **External compute**    | Azure SQL, Synapse, HDInsight          |
| **General**             | Web activity, Lookup                   |

---

### 🔹 Example of a Pipeline

Pipeline: **Daily Sales ETL**

Activities inside the pipeline:
* 1️⃣ Lookup activity → Fetch date range
* 2️⃣ Copy activity → Move raw data to ADLS
* 3️⃣ Data Flow activity → Clean & transform data
* 4️⃣ Notebook activity → Run advanced logic
* 5️⃣ Email/Webhook → Send success notification

Pipeline executes everything in sequence or parallel.

---

### 🔹 How triggers work

Triggers start pipelines automatically:

| Trigger              | When used                          |
| -------------------- | ---------------------------------- |
| **Schedule Trigger** | every x mins/hours/days            |
| **Event Trigger**    | when a new file arrives in storage |
| **Manual Trigger**   | run on demand                      |

Example:
"Run pipeline at 2 AM daily" → Schedule Trigger.

---

## ✔ **6.2 Azure SQL Database – Simple & Clear**

Azure SQL Database = **fully managed relational database** in Azure.
It is the cloud version of Microsoft SQL Server.

#### 🔹 Key features

* No need to manage hardware or OS
* Auto backups
* Automatic patching
* Geo-replication for DR
* Built-in performance tuning
* Scales up or down easily

---

### 🔹 When to use Azure SQL Database?

Use it when you need:

* OLTP workloads (transactions)
* Highly available SQL engine
* Minimal admin work
* Automatic security and backup
* Integration with ADF, Synapse, Power BI

---

### 🔹 Simple Example Use Case

Your application stores:

* customer profiles
* orders
* inventory

Azure SQL Database stores these tables.
ADF then loads cleaned data from SQL into ADLS for analytics.

---

### ⚡ Quick Summary

* **ADF = ETL orchestration tool**
* **Pipelines = workflow**
* **Activities = tasks inside pipeline**
* **Copy Activity = ingestion**
* **Data Flow / Databricks = transformation**
* **Azure SQL Database = managed SQL Server in cloud**

---




