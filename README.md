### Architecture Overview


 ## Network Layer
1. Custom VPC (10.0.0.0/16)

2. Public Subnets (one per Availability Zone)

3. 2 Private Subnets for application servers

### Internet Gateway for public traffic

NAT Gateways in each AZ for secure outbound access from private instances



###  Load Balancing
Application Load Balancer (ALB) distributes traffic across instances in multiple AZs

Integrated health checks automatically detect and remove unhealthy servers



### Compute Layer
Auto Scaling Groups deployed across private subnets

Automatically:

Launches new EC2 instances when load increases

Replaces unhealthy instances (auto-healing)



### Data Layer
Amazon RDS deployed in private subnet

Used for persistent backend data storage

Secured from direct internet access



###  Storage & Backup
Amazon S3 used for backup/static storage

Designed for durability and disaster recovery support



## DNS
Amazon Route 53 routes traffic to the ALB endpoint

##  How Auto-Healing Works
- ALB performs continuous health checks on EC2 instances

- If an instance fails:

- It is marked unhealthy

- Auto Scaling Group terminates and replaces it automatically

- Traffic is only routed to healthy instances



## Result: No manual intervention required — the system heals itself.

🛠 ## AWS Services Used

- VPC

- Subnets (Public & Private)

- Internet Gateway

- NAT Gateway

- Route Tables

- EC2

- Auto Scaling Groups

- Application Load Balancer

- Amazon RDS

- Route 53

- S3


## 🎯 Key Skills Demonstrated


## Cloud Network Design

- High Availability Architecture

-  Auto Scaling & Self-Healing Systems

- Secure VPC Design

- Load Balancing & Health Monitoring

- Multi-AZ Deployment Strategy

## Live Testing


Below shows the application responding through the Load Balancer endpoint:

## 💡 What I Learned
How to design production-style resilient infrastructure

Importance of private vs public subnet separation

Real implementation of auto-healing using ASG + ALB

How AWS networking components work together
