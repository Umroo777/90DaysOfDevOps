---
title: Protocols & Ports for DevOps
(e.g., HTTP, HTTPS, FTP, SSH, DNS) and their port numbers.
And their relevance to DevOps workflows.
---

# 🌐 Protocols and Ports for DevOps

Understanding protocols and their associated port numbers is crucial in DevOps. These protocols help with server access, configuration management, CI/CD, networking, and cloud service integration.

## 📋 Commonly Used Protocols and Port Numbers

| Protocol | Port Number | Description | DevOps Relevance |
|----------|-------------|-------------|------------------|
| **HTTP**  | 80          | HyperText Transfer Protocol – used for unencrypted web communication | Used for accessing web apps, REST APIs, and internal tools |
| **HTTPS** | 443         | Secure HTTP – encrypts communication over the web | Ensures secure data transfer between services, pipelines, and dashboards |
| **SSH**   | 22          | Secure Shell – encrypted remote login | Used for remote server access, configuration, deployments, and automation (e.g., Ansible, Git over SSH) |
| **FTP**   | 21          | File Transfer Protocol – used for file transfers | Occasionally used to upload/download files during deployment or backups |
| **SFTP**  | 22          | Secure File Transfer Protocol – FTP over SSH | Securely transfers files to/from servers in CI/CD pipelines |
| **DNS**   | 53          | Domain Name System – translates domain names to IP addresses | Important for service discovery, resolving domain names in scripts and cloud configs |
| **SMTP**  | 25, 587     | Simple Mail Transfer Protocol – sends emails | Used for alerts, monitoring notifications, or app-generated emails |
| **SNMP**  | 161         | Simple Network Management Protocol – monitors devices on a network | Used for monitoring server/network health in production |
| **NTP**   | 123         | Network Time Protocol – syncs time across systems | Ensures accurate logging and coordination between distributed systems |
| **MySQL** | 3306        | MySQL database port | Access and manage databases during deployment or backups |
| **PostgreSQL** | 5432    | PostgreSQL database port | Similar to MySQL; used in app development and automation |
| **Docker API** | 2375 (unencrypted), 2376 (TLS) | Docker daemon communication | Used in container orchestration, CI/CD, and infrastructure automation |
| **Kubernetes API** | 6443 | Secure communication with the Kubernetes control plane | Required in DevOps for managing clusters and deploying workloads |

## 🔧 Why This Matters in DevOps

- **CI/CD Pipelines**: Communicate with servers and APIs using HTTP/HTTPS.
- **Automation Tools**: Tools like Ansible, Terraform, and Jenkins rely on SSH, HTTP, and DNS.
- **Monitoring & Alerts**: Use protocols like SNMP and SMTP for system health and notifications.
- **Secure Communication**: SSH and HTTPS ensure safe handling of sensitive operations.
- **Database Management**: Ports like 3306 (MySQL) and 5432 (PostgreSQL) are used during migrations, backups, and data seeding.

## ✅ Summary Table

| Use Case                | Protocol | Port |
|-------------------------|----------|------|
| Access web dashboard    | HTTP     | 80   |
| Secure API connection   | HTTPS    | 443  |
| Deploy to Linux server  | SSH      | 22   |
| Trigger monitoring alert| SMTP     | 25/587 |
| Time synchronization    | NTP      | 123  |
| Resolve DNS records     | DNS      | 53   |

 Always ensure proper firewall and security group configurations for the necessary ports in cloud environments like AWS, Azure, or GCP.

