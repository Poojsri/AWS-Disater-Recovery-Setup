# AWS Disaster Recovery Project

This repository documents the **Disaster Recovery (DR) setup on AWS** through step-by-step screenshots. The project demonstrates how to implement a fault-tolerant and highly available architecture to ensure business continuity in case of failures.  

---

## 📌 Objective
The main goal of this project is to:
- Understand the **importance of Disaster Recovery (DR)** in cloud environments.  
- Implement DR strategies using **AWS services**.  
- Demonstrate failover, replication, and recovery mechanisms with practical examples.  

---

## ⚙️ AWS Services Used
The following AWS services were used in the setup:
- **Amazon EC2** – for hosting the primary and secondary application servers.  
- **Amazon S3** – for storing static assets and backups.  
- **Amazon RDS** – database replication between primary and DR region.  
- **Amazon Route 53** – DNS routing and failover.  
- **VPC & Subnets** – secure networking and isolation across regions.  
- **CloudWatch** – monitoring and health checks.  

---

## 📂 Repository Contents
This repository contains **screenshots only**, which visually document the setup process. Each screenshot corresponds to a step in the Disaster Recovery implementation.

**Folders / Files:**  
- `/screenshots` – contains all images of the AWS console configuration.  
- `README.md` – this file, which explains the project.  

---

## 🛠️ Setup Workflow

Below is the step-by-step workflow of the Disaster Recovery setup, explained alongside the screenshots:

### 1. VPC and Networking Setup
- Created a **VPC** with public and private subnets.  
- Configured **Internet Gateway** and **Route Tables** for connectivity.  
📸 *[Refer to screenshot: VPC_Setup.png]*  

---

### 2. Primary Region Deployment
- Launched **EC2 instances** in the primary region for the application.  
- Configured **RDS** database in the primary region.  
📸 *[Refer to screenshot: Primary_Region_EC2.png]*  
📸 *[Refer to screenshot: RDS_Primary.png]*  

---

### 3. Disaster Recovery (Secondary Region)
- Set up **EC2 and RDS replicas** in the secondary (DR) region.  
- Enabled **cross-region replication** for backups and snapshots.  
📸 *[Refer to screenshot: Secondary_Region_EC2.png]*  
📸 *[Refer to screenshot: RDS_Replication.png]*  

---

### 4. S3 Cross-Region Replication
- Configured **S3 bucket replication** between primary and secondary regions.  
📸 *[Refer to screenshot: S3_Replication.png]*  

---

### 5. Route 53 DNS Failover
- Configured **Route 53 health checks** and failover routing policies.  
- Primary endpoint serves traffic until a failure occurs, then traffic is routed to the DR region.  
📸 *[Refer to screenshot: Route53_Failover.png]*  

---

### 6. Monitoring & Alerts
- Set up **CloudWatch alarms** for EC2 and RDS health.  
- Notifications sent via **SNS** in case of failure.  
📸 *[Refer to screenshot: CloudWatch_Alarms.png]*  

---

## 🚀 Testing the Disaster Recovery
- Simulated a **failure in the primary region** by stopping EC2 / making DB unavailable.  
- Verified that Route 53 automatically routed traffic to the **DR region**.  
📸 *[Refer to screenshot: Failover_Test.png]*  

---

## 📊 Key Learnings
- Importance of **multi-region architecture** in achieving high availability.  
- Practical understanding of **RTO (Recovery Time Objective)** and **RPO (Recovery Point Objective)**.  
- Hands-on with **Route 53 failover policies**, **RDS replication**, and **S3 replication**.  

---

## 📌 Future Enhancements
- Automate the entire setup using **Terraform or CloudFormation**.  
- Integrate with **AWS Backup** for more granular recovery.  
- Extend monitoring with **AWS Security Hub** for compliance checks.  

---

## 🖼️ Screenshots
All screenshots are available in the `/screenshots` folder. Refer to them while following the above steps.  

---

## 👩‍💻 Author
Project by **[Your Name]** – for academic/learning purposes.  
