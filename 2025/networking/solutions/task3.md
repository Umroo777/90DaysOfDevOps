# 🔐 AWS EC2 & Security Groups – A Step-by-Step Guide

In cloud computing, **security is critical**. AWS provides **Security Groups** as virtual firewalls to control inbound and outbound traffic for your EC2 instances.

This guide walks you through launching an EC2 instance and configuring Security Groups.

---

## 🚀 Step 1: Launch an EC2 Instance (Free Tier)

1. **Log in** to [AWS Console](https://console.aws.amazon.com/)
2. Navigate to **EC2** under the "Compute" category.
3. Click **Launch Instance**
4. Fill in the details:
   - Name: `My-DevOps-Instance`
   - AMI: `Amazon Linux 2023` (or Ubuntu)
   - Instance Type: `t2.micro` (Free Tier eligible)
5. Key Pair:
   - Create a new key pair (e.g., `devops-key`)
   - Download the `.pem` file (you’ll need this to SSH)
6. Under **Network Settings**, click **Edit** to configure the Security Group

---

## 🛡️ Step 2: Configure a Security Group

### 🔧 What is a Security Group?

A **Security Group** acts like a firewall at the instance level. It **controls inbound and outbound traffic** using rules.

---

### ✅ Default Security Group Rules

| Type         | Protocol | Port Range | Source            | Description             |
|--------------|----------|-------------|--------------------|--------------------------|
| SSH          | TCP      | 22          | My IP              | Allows SSH from your IP |
| HTTP (Web)   | TCP      | 80          | Anywhere (0.0.0.0/0) | Public web traffic     |
| HTTPS (Secure Web) | TCP | 443       | Anywhere (0.0.0.0/0) | Secure traffic         |

---

### 📥 Inbound Rules

Inbound rules control **incoming** traffic to the instance.

Example configuration:

| Rule Name | Port | Source       | Use Case                    |
|-----------|------|--------------|-----------------------------|
| SSH       | 22   | My IP        | Secure remote login         |
| HTTP      | 80   | Anywhere     | Serve a website or app      |
| HTTPS     | 443  | Anywhere     | Secure web communication    |

---

### 📤 Outbound Rules

Outbound rules control **outgoing** traffic **from** the instance.

By default, **all outbound traffic is allowed**, which is fine in most cases unless you're hardening security.

---

## 🧪 Step 3: Test the Configuration

1. After launch, go to **EC2 > Instances**
2. Copy the **Public IPv4 address**
3. SSH into the instance:

```bash
chmod 400 devops-key.pem
ssh -i devops-key.pem ec2-user@<your-public-ip>

->>If connected, your Security Group is working!
->>If you enabled HTTP (port 80), you can install a web server:
-> then

sudo yum install -y httpd (*In linux for (apachi) web-server used httpd*)
sudo systemctl start httpd
sudo systemctl enable httpd
Then open your browser and visit:
http://<your-public-ip>


