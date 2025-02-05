# **Task 2: Protocols and Ports for DevOps**

## **Introduction**

### **What is a Protocol?**
A protocol is a set of rules that govern how data is transmitted over a network. It defines the format, timing, sequencing, and error control mechanisms to ensure successful communication between devices or applications.

### **What is a Port?**
A port is a logical endpoint in networking used for identifying specific processes or services running on a device. Ports allow multiple applications to use the network simultaneously without interfering with each other.

### **Types of Protocols**
1. **Network Protocols** - Used for communication between devices (e.g., TCP/IP, UDP, ICMP).
2. **Security Protocols** - Ensure safe data transmission (e.g., SSL/TLS, HTTPS, SSH).
3. **Application Layer Protocols** - Enable applications to communicate over a network (e.g., HTTP, FTP, SMTP).
4. **Data Transfer Protocols** - Handle the exchange of files and data (e.g., FTP, SFTP, SCP).
5. **Cloud & DevOps-Specific Protocols** - Used for cloud and infrastructure automation (e.g., Kubernetes API, Docker API).

Understanding these protocols and their associated ports is crucial for DevOps engineers to manage infrastructure, automate processes, and secure deployments effectively.

---

## **Table of Contents**

- [Networking and Communication Protocols](#networking-and-communication-protocols)
- [DevOps Tools and Services](#devops-tools-and-services)
- [Cloud Service Providers](#cloud-service-providers)
- [Monitoring and Logging Tools](#monitoring-and-logging-tools)
- [Database and Messaging Services](#database-and-messaging-services)
- [Security and Authentication](#security-and-authentication)
- [CI/CD and Configuration Management](#cicd-and-configuration-management)
- [Load Balancing and Reverse Proxy](#load-balancing-and-reverse-proxy)
- [Networking Services and VPN](#networking-services-and-vpn)
- [Remote Access and Management](#remote-access-and-management)

---

## **Networking and Communication Protocols**

| **Protocol**       | **Port**         | **Purpose**              | **DevOps Use Case**                                 |
| ------------------ | ---------------- | ------------------------ | --------------------------------------------------- |
| SSH (Secure Shell) | 22 (TCP)         | Secure remote access     | Remote login, executing commands, and file transfer |
| HTTP               | 80 (TCP)         | Web communication        | Web applications, REST APIs                         |
| HTTPS              | 443 (TCP)        | Secure web communication | Secure access to APIs, websites, and DevOps tools   |
| FTP                | 21 (TCP)         | File transfer            | Transferring configuration files and logs           |
| SFTP               | 22 (TCP)         | Secure file transfer     | Secure data transfer in automation workflows        |
| DNS                | 53 (UDP/TCP)     | Domain name resolution   | Connecting services using domain names              |
| ICMP               | No specific port | Network troubleshooting  | Ping requests for checking server availability      |
| NTP (Network Time Protocol) | 123 (UDP) | Time synchronization | Syncing server and container clocks |

---

## **DevOps Tools and Services**

| **Tool**                      | **Port**                  | **Purpose**                  | **DevOps Use Case**                              |
| ----------------------------- | ------------------------- | ---------------------------- | ------------------------------------------------ |
| Git (GitHub/GitLab/Bitbucket) | 22 (SSH), 443 (HTTPS)     | Version control              | Repository management, CI/CD integration         |
| Docker                        | 2375 (No TLS), 2376 (TLS) | Container management         | Running, managing, and orchestrating containers  |
| Kubernetes                    | 6443, 10250, 10255        | Cluster management           | Orchestrating containerized applications         |
| Jenkins                       | 8080 (UI), 50000 (Agent)  | CI/CD automation             | Automating build, test, and deployment pipelines |
| Ansible                       | 22 (SSH)                  | Configuration management     | Automating system setup and provisioning         |
| Terraform                     | Uses cloud provider APIs  | Infrastructure as Code (IaC) | Automating infrastructure provisioning           |
| Helm                          | N/A                       | Kubernetes package management | Deploying applications on Kubernetes             |

---

## **Cloud Service Providers**

| **Service** | **Port**            | **Purpose**      | **DevOps Use Case**                             |
| ----------- | ------------------- | ---------------- | ----------------------------------------------- |
| AWS         | 443, 22, 3306, 5432 | Cloud API access | Managing cloud services, database access        |
| Azure       | 443, 22, 1433       | Cloud API access | Provisioning resources, managing services       |
| GCP         | 443, 22             | Cloud API access | Automating deployments, managing infrastructure |

---

## **Monitoring and Logging Tools**

| **Tool**   | **Port**               | **Purpose**            | **DevOps Use Case**                          |
| ---------- | ---------------------- | ---------------------- | -------------------------------------------- |
| Prometheus | 9090, 9100             | Metrics collection     | Monitoring system health and performance     |
| Grafana    | 3000                   | Data visualization     | Creating dashboards for system monitoring    |
| ELK Stack  | 9200, 9300, 5044, 5601 | Log analysis           | Centralized logging and monitoring           |
| Datadog    | 8125                   | Performance monitoring | Application monitoring and security insights |
| Zabbix     | 10050, 10051           | Infrastructure monitoring | Monitoring network and server performance |

---

## **Database and Messaging Services**

| **Service** | **Port**    | **Purpose**         | **DevOps Use Case**                      |
| ----------- | ----------- | ------------------- | ---------------------------------------- |
| MySQL       | 3306 (TCP)  | Relational database | Storing application data                 |
| PostgreSQL  | 5432 (TCP)  | Relational database | Cloud and container-based applications   |
| MongoDB     | 27017 (TCP) | NoSQL database      | Storing unstructured data                |
| Redis       | 6379 (TCP)  | Caching & messaging | Caching for performance improvement      |
| RabbitMQ    | 5672, 15672 | Message queuing     | Asynchronous processing in microservices |
| Kafka       | 9092, 2181  | Event streaming     | Processing real-time data streams        |
| Cassandra   | 9042        | NoSQL database      | Distributed data storage                 |

---
## Resources 📚
- [Beginner's Guide to Network Ports](https://en.wikipedia.org/wiki/Lists_of_network_protocols)
- [Ports And Protocols In Depth!!!](https://youtu.be/Ne631DEe1TA?si=KE9is_tYHmln8x8b)


---
## Updates 🔗
**Follow my journey:** [LinkedIn Profile](https://www.linkedin.com/in/yashbharitkar25learns-cloud/)


