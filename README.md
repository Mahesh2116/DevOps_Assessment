# Nginx Deployment
## Project Overview

This project demonstrates the deployment of a simple **Hello World web application** on AWS using a secure and scalable architecture.

The application is hosted on EC2 instances running Nginx inside private subnets and is exposed to the internet via an Application Load Balancer.

---

## Architecture

* VPC with public and private subnets
* Application Load Balancer (Public Subnets)
* EC2 Instances with Nginx (Private Subnets)
* Secure access using Security Groups
* No direct internet access to EC2

---

## Architecture Diagram

AWS_Simple_Architecture.png

```
Internet → ALB → EC2 (Private Subnets)
```

---

## Tech Stack

* AWS (VPC, EC2, ALB, IAM)
* Nginx
* Linux (Amazon Linux 2023, t2.micro)
* Systems Manager (SSM)

---

## Security

* EC2 instances are in private subnets
* No public IP assigned to EC2
* Only ALB can access EC2 instances
* Internet traffic is routed through ALB only
* Used Security Groups for controlled access

---

## Application Access

* Application is accessible via ALB DNS

http://nginx-alb-1987962117.ap-south-1.elb.amazonaws.com/

Example Output:

```
Hello World!
Instance ID: i-091ab26492f978d8f
Availability Zone: ap-south-1a
Served by: Nginx
```

---

## Project Structure

```
.
├── docs/
│   ├── deployment_steps.pdf
│   └── security-groups.md
├── nginx/
│   └── nginx.conf
│   └── index.html
└── README.md
└── AWS_Simple_Architecture.png

```

---

## Deployment Steps

Detailed steps available here:
 `docs/deployment_steps.pdf`

---

## Security Configuration

Security group details available here:
 `docs/security-groups.md`

---

## Configuration Files

### Nginx

* Located at: `/etc/nginx/nginx.conf`

### HTML Page

* Path: `/usr/share/nginx/html/index.html`

---

## Features Implemented

* Custom VPC with subnet design
* Private EC2 deployment
* Application Load Balancer setup
* Nginx web server configuration
* Secure architecture (no public EC2 access)
* Systems Manager access (no SSH required)

---

## Learnings

* Hands-on experience with AWS networking (VPC, subnets, routing)
* Secure infrastructure design using private subnets
* Load balancing using ALB
* EC2 configuration and Nginx setup
* Troubleshooting connectivity and health checks

---

## Screenshots

 `docs/deployment_steps.pdf`

* ALB DNS working
* Target group healthy
* Web application output

---

## Conclusion

Successfully deployed a secure and scalable web application architecture on AWS following DevOps best practices.

---

## Author

Mahesh Deshmukh

