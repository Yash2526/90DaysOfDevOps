# **Task 3: AWS EC2 and Security Groups: A Step-by-Step Guide**

## **Introduction**
Amazon EC2 (Elastic Compute Cloud) is a core service in AWS that allows you to run virtual servers in the cloud. It provides scalable computing capacity and is widely used in DevOps for hosting applications, testing environments, and automating deployments.

Security Groups in AWS act as virtual firewalls that control inbound and outbound traffic for EC2 instances. They play a crucial role in securing cloud resources by defining rules that allow or deny access based on IP addresses, protocols, and ports.

In this guide, we will go through the process of launching an EC2 instance and configuring Security Groups to ensure secure and controlled access.

---

## **Step 1: Launch an AWS EC2 Instance**

### **1. Sign in to AWS Management Console**
1. Go to [AWS Console](https://aws.amazon.com/console/).
2. Sign in with your AWS credentials.
3. Navigate to the **EC2 Dashboard**.

### **2. Choose an Amazon Machine Image (AMI)**
1. Click on **Launch Instance**.
2. Select an AMI (Amazon Machine Image). For a free-tier instance, choose **Amazon Linux 2** or **Ubuntu**.

### **3. Choose an Instance Type**
1. Select **t2.micro** (Free Tier Eligible).
2. Click **Next: Configure Instance Details**.

### **4. Configure Instance Details**
1. Leave the default settings for now.
2. Click **Next: Add Storage**.

### **5. Add Storage**
1. Keep the default 8 GB storage (or increase if needed).
2. Click **Next: Add Tags**.

### **6. Add Tags (Optional)**
1. Click **Add Tag**.
2. Set a key as `Name` and value as `MyEC2Instance`.
3. Click **Next: Configure Security Group**.

---

## **Step 2: Configure Security Groups**

### **1. Create a New Security Group**
1. Choose **Create a new security group**.
2. Name it **MySecurityGroup**.
3. Add a description (e.g., `Security group for my EC2 instance`).

### **2. Define Inbound Rules**
Inbound rules control which traffic can enter your instance.

| **Type**  | **Protocol** | **Port Range** | **Source**          | **Purpose**               |
|-----------|-------------|---------------|--------------------|---------------------------|
| SSH       | TCP         | 22            | My IP (your IP)    | Secure remote access      |
| HTTP      | TCP         | 80            | Anywhere (0.0.0.0/0) | Web server access        |
| HTTPS     | TCP         | 443           | Anywhere (0.0.0.0/0) | Secure web traffic       |

### **3. Define Outbound Rules**
Outbound rules control which traffic can leave your instance. The default rule allows all outbound traffic.
1. Leave the default setting: **Allow all traffic (0.0.0.0/0)**.
2. Click **Review and Launch**.

### **4. Launch and Connect**
1. Click **Launch**.
2. Choose an existing key pair or create a new one.
3. Download the key file (`.pem`) and keep it secure.
4. Click **Launch Instances**.

---

## **Step 3: Connect to Your EC2 Instance**

### **1. Use SSH to Connect**
On your local machine, open a terminal and use the following command:

```bash
ssh -i /path/to/key.pem ec2-user@<EC2-PUBLIC-IP>
```

For Ubuntu instances, use:

```bash
ssh -i /path/to/key.pem ubuntu@<EC2-PUBLIC-IP>
```

### **2. Verify Security Group Rules**
1. Try accessing the instance from a blocked IP (it should fail).
2. Test HTTP/HTTPS access using a web browser.

---

## **Best Practices for Security Groups**
1. **Use the Least Privilege Principle:** Only open necessary ports.
2. **Restrict SSH Access:** Use specific IPs instead of `0.0.0.0/0`.
3. **Regularly Audit Security Groups:** Remove unused rules.
4. **Enable VPC Flow Logs:** Monitor network traffic for anomalies.
5. **Use AWS IAM Roles:** Avoid storing credentials on EC2 instances.

---
## Updates 🔗
**Follow my journey:** [LinkedIn Profile](https://www.linkedin.com/in/yashbharitkar25learns-cloud/)
