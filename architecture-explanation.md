## Architecture Explanation

### Flow
- User sends request to Application Load Balancer (ALB)
- ALB distributes traffic across EC2 instances in multiple Availability Zones
- EC2 instances process requests (Nginx web server)
- EC2 instances interact with RDS (MySQL) for dynamic data
- EC2 instances upload/read objects from S3 using IAM Role
- RDS is deployed in private subnets and not publicly accessible

### High Availability
- Multi-AZ deployment across 2 Availability Zones
- Application Load Balancer ensures traffic distribution
- Auto Scaling Group maintains desired number of instances
- Failed instances are automatically replaced

### Networking
- Custom VPC (10.0.0.0/16)
- Public subnets: ALB and Bastion host
- Private subnets: EC2 and RDS
- Internet Gateway allows inbound/outbound traffic for public resources
- Route tables separate public and private traffic

### Security
- EC2 instances do not have public IPs
- Bastion host used for secure SSH access
- Security Groups restrict traffic (least privilege)
- RDS accepts connections only from EC2 Security Group
- IAM Role used for secure S3 access (no credentials stored)

### Admin Access
- Laptop → Bastion Host → Private EC2 → RDS
- SSH ProxyCommand used for secure access to private instances

### Storage
- Amazon S3 used for object storage
- Access controlled via IAM Role attached to EC2
