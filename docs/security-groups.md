# Security Group Configuration

## 1. Application Load Balancer Security Group (alb-sg)

### Inbound Rule
- Type: HTTP  
- Protocol: TCP  
- Port: 80  
- Source: 0.0.0.0/0  

### Outbound Rule
- Type: All Traffic  
- Protocol: All  
- Port: All  
- Destination: 0.0.0.0/0  

---

## 2. EC2 Instance Security Group (ec2-sg)

### Inbound Rule
- Type: HTTP  
- Protocol: TCP  
- Port: 80  
- Source: ALB Security Group  

### Outbound Rule
- Type: All Traffic  
- Protocol: All  
- Port: All  
- Destination: 0.0.0.0/0  

---

## 3. Security Design Explanation

- EC2 instances are deployed in private subnets without public IP addresses.  
- Only the Application Load Balancer can access the EC2 instances.  
- Internet users can access the application only through the ALB.  
- Direct access to EC2 instances is restricted.  

### Benefits:
- Improved security  
- Controlled access  
- Network isolation  

---

## 4. Best Practices Followed

- Principle of Least Privilege  
- No direct SSH access to EC2 instances  
- Secure access using Systems Manager  
- Restricted inbound traffic to required ports only  

---

## 5. Summary

- ALB is internet-facing  
- EC2 instances are private  
- Secure communication via security groups  
