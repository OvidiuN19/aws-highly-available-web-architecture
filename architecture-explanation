# Architecture Explanation

## Flow
- User sends request to Application Load Balancer (ALB)
- ALB distributes traffic across EC2 instances in multiple Availability Zones
- EC2 instances process requests (Nginx web server)
- Data is stored in RDS (MySQL) in a private subnet
- Static files can be stored in S3

## Admin Access
- Laptop → Bastion → Private EC2 / RDS

## Security
- EC2 instances are not publicly exposed
- RDS is not publicly accessible
- Security Groups restrict access between components
