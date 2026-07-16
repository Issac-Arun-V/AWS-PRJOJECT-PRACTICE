Here's a professional, detailed GitHub README description that looks like a genuine portfolio project rather than a copied template.

---

# 🚀 Highly Available 3-Tier Web Application Architecture on AWS

## 📖 Overview

This project demonstrates the deployment of a **Highly Available 3-Tier Web Application Architecture** on **Amazon Web Services (AWS)** using industry-standard cloud infrastructure components.

The objective of this project was to design a secure, scalable, fault-tolerant, and production-style architecture by separating the **Presentation Layer**, **Application Layer**, and **Database Layer** into different network segments.

The infrastructure was designed to follow AWS best practices for networking, security, high availability, and automatic scaling.

---

# 🏗 Architecture

```
                    Internet
                        │
                Internet Gateway
                        │
          ┌─────────────────────────┐
          │ Application Load Balancer│
          └───────────┬─────────────┘
                      │
        ┌─────────────┴─────────────┐
        │                           │
   EC2 Instance                 EC2 Instance
 (Private App AZ-1)         (Private App AZ-2)
        │                           │
        └─────────────┬─────────────┘
                      │
              Auto Scaling Group
                      │
               Amazon RDS MySQL
               (Private Database)
```

---

# ☁ AWS Services Used

* Amazon VPC
* Amazon EC2
* Application Load Balancer (ALB)
* Auto Scaling Group (ASG)
* Amazon RDS MySQL
* Internet Gateway
* NAT Gateway
* Route Tables
* Public & Private Subnets
* Security Groups
* IAM
* CloudShell
* Launch Template

---

# 📂 Project Architecture

## VPC

* Custom VPC
* CIDR: **10.0.0.0/16**

---

## Public Subnets

* Public Subnet 1 (AZ-a)
* Public Subnet 2 (AZ-b)

Used for:

* Application Load Balancer
* NAT Gateway

---

## Private Application Subnets

* Private App Subnet 1
* Private App Subnet 2

Used for:

* EC2 Instances
* Auto Scaling Group

---

## Private Database Subnets

* Private DB Subnet 1
* Private DB Subnet 2

Used for:

* Amazon RDS MySQL

---

# 🔒 Security Design

### ALB Security Group

Allowed

* HTTP (80) from Internet

Outbound

* HTTP to App Server Security Group

---

### Application Server Security Group

Allowed

* HTTP (80) only from ALB Security Group

Outbound

* MySQL (3306) to Database Security Group

---

### Database Security Group

Allowed

* MySQL (3306) only from Application Server Security Group

No public access was allowed to the database.

---

# ⚙ Auto Scaling Configuration

Minimum Capacity

```
2
```

Desired Capacity

```
2
```

Maximum Capacity

```
4
```

Scaling Policy

* Target Tracking
* Average CPU Utilization: **50%**

---

# ⚖ Load Balancer Configuration

Application Load Balancer

Listener

```
HTTP : 80
```

Target Group

```
HTTP : 80
```

Health Check

```
/
```

Protocol

```
HTTP
```

---

# 🗄 Database

Engine

```
Amazon RDS MySQL
```

Deployment

```
Multi-AZ
```

Access

```
Private
```

---

# 🚀 Features

* Highly Available Architecture
* Multi-AZ Deployment
* Auto Scaling
* Load Balancing
* Secure Network Design
* Private Database
* Public/Private Subnet Architecture
* Security Group Isolation
* High Availability
* Fault Tolerance
* Production-style AWS Infrastructure

---

# 🛠 Challenges Faced

During this project, I encountered several real-world AWS issues and successfully resolved them, including:

* Incorrect Target Group port configuration
* Unhealthy EC2 instances
* ALB returning **504 Gateway Timeout**
* Security Group communication issues
* Auto Scaling target registration
* Route Table configuration errors
* NAT Gateway connectivity
* RDS networking configuration
* Resource dependency errors during infrastructure cleanup

Resolving these issues significantly improved my practical understanding of AWS networking and cloud troubleshooting.

---

# 📚 Skills Gained

* AWS Networking
* VPC Design
* High Availability Architecture
* Linux Administration
* EC2 Management
* Auto Scaling
* Load Balancing
* RDS Deployment
* IAM
* Security Groups
* Route Tables
* Cloud Infrastructure
* AWS CLI
* Cloud Troubleshooting

---

# 📸 Project Screenshots

You can add screenshots of:

* VPC Architecture
* Subnets
* Route Tables
* Security Groups
* EC2 Instances
* Launch Template
* Auto Scaling Group
* Application Load Balancer
* Target Group (Healthy Instances)
* Amazon RDS
* Successful Application Output

---

# 🎯 Learning Outcome

This project provided practical experience in designing and deploying a production-style AWS infrastructure using best practices for networking, security, scalability, and high availability.

Beyond deployment, it strengthened my troubleshooting skills by resolving real infrastructure issues involving networking, load balancing, target groups, security groups, and AWS resource dependencies.

---

## 👨‍💻 Author

**Issac Arun**

* 🎓 Electronics and Communication Engineering Graduate
* ☁️ AWS Cloud Learner
* 🌐 Networking Enthusiast
* 🐧 Linux Learner

⭐ **If you found this project useful, consider giving it a Star!**
