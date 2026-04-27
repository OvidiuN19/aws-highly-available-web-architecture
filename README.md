# aws-highly-available-web-architecture
AWS project demonstrating high availability, load balancing, auto scaling and secure networking

AWS Highly Available Web Architecture
📌 Overview
This project demonstrates a production-style AWS architecture focused on high availability, scalability, and security best practices.

🏗️ Architecture
    • Multi-AZ deployment
    • Application Load Balancer
    • Auto Scaling Group
    • Private RDS database
    • Bastion host for secure access
    • S3 integration via IAM Role
    • Architecture flow:
Internet → ALB → EC2 (Auto Scaling Group) → RDS 

🌐 Networking
    • Custom VPC (10.0.0.0/16)
    • 2 Public Subnets (ALB, Bastion)
    • 2 Private Subnets (EC2, RDS)
    • Internet Gateway
    • Route Tables

🖥️ Compute
    • EC2 instances (Amazon Linux 2023)
    • Nginx installed via User Data
    • Instances launched via Launch Template

⚖️ Load Balancer
    • Application Load Balancer (public)
    • Distributes traffic across instances
    • Health checks configured

🔄 Auto Scaling
    • Auto Scaling Group used for high availability
    • Min: 1 / Max: 2
    • Automatic instance replacement (self-healing)

🗄️ Database
    • Amazon RDS (MySQL)
    • Private subnet deployment
    • Access only from EC2 Security Group

📦 Storage
    • Amazon S3
    • Access via IAM Role (no credentials stored)
    • Tested from EC2

🔐 Security
    • Bastion host for SSH access
    • Private instances without public IP
    • Security Groups (least privilege)

🧪 Testing
    • Load balancing verified
    • Instance failover tested
    • RDS connection tested
    • S3 upload tested
    • NAT Gateway tested and removed

💰 Cost Optimization
    • NAT Gateway removed
    • RDS deleted after testing
    • EC2 instances terminated

🧠 Key Concepts
    • High Availability
    • Load Balancing
    • Auto Scaling
    • Secure Networking
    • IAM Roles
    • Private Database Access

✅ Conclusion
This project simulates a real-world AWS architecture suitable for entry-level cloud engineering roles.
