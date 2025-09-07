# Terraform AWS Webserver Stack

This repository contains Terraform code to provision a simple yet production-style web server stack on AWS.  
The project builds networking from scratch (VPC, Subnet, Route Table, Internet Gateway) and launches an EC2 instance running **Nginx**, accessible over **HTTP (port 80)**.

---

## 🚀 Overview
- **Goal:** Automate AWS infrastructure setup for a basic web server.
- **Stack:** VPC, Public Subnet, Route Table, Internet Gateway, EC2, Security Group, and Nginx.
- **Result:** A reachable web page served from an EC2 instance within your custom VPC.

---

## 🛠️ Steps Performed

1. **Created a VPC**  
   Defined a custom VPC to isolate and manage all resources in a single network.

2. **Configured a Public Subnet**  
   Provisioned a subnet within the VPC to host the EC2 instance.

3. **Set Up Internet Gateway & Route Table**  
   - Attached an Internet Gateway to allow outbound internet access.  
   - Created and associated a Route Table with a default route to the Internet Gateway.

4. **Launched an EC2 Instance**  
   - Used Terraform to provision an EC2 instance in the public subnet.  
   - Added a Security Group allowing inbound **HTTP (80)** and **SSH (22)** for administration.

5. **Installed & Configured Nginx**  
   Added user data (or provisioner) to install and start **Nginx** automatically on boot.

6. **Verified HTTP Access**  
   Accessed the instance’s public IP in a browser to confirm the default Nginx welcome page.

---

## 📂 Repository Structure
.
├── main.tf # Core Terraform configuration
├── variables.tf # Input variables (VPC CIDR, subnet, instance type, etc.)
├── outputs.tf # Outputs (public IP, VPC ID, etc.)
└── README.md # Project documentation

yaml
Copy code

---

## 🔑 Prerequisites
- Terraform installed (v1.0+)
- AWS CLI configured with valid credentials
- An active AWS account

---

## ▶️ How to Use
1. Clone the repository  
   ```bash
   git clone https://github.com/khaleeluddin9912/iac-aws-vpc-ec2-nginx.git
Initialize Terraform

bash
Copy code
terraform init
Preview the changes

bash
Copy code
terraform plan
Apply to create resources

bash
Copy code
terraform apply
After creation, check the output for the public IP of the EC2 instance and open it in a browser.

🧹 Cleanup
To avoid charges, destroy resources when done:

bash
Copy code
terraform destroy

👤 Author
Khaleel Uddin
