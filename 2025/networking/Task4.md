# Task 4: Hands-On with Networking Commands

## Introduction
Understanding networking commands is essential for troubleshooting, monitoring, and ensuring smooth network communication. Below is a cheat sheet covering some of the most commonly used networking commands.

## Essential Networking Commands

### 1. **ping**
- **Purpose**: Checks connectivity between your system and a remote server.
- **Usage**:
  ```bash
  ping google.com
  ```
  This sends packets to Google's server and waits for a response.

### 2. **traceroute / tracert**
- **Purpose**: Traces the route packets take to reach a destination.
- **Usage**:
  - Linux/macOS:
    ```bash
    traceroute google.com
    ```
  - Windows:
    ```bash
    tracert google.com
    ```
  This helps diagnose network path issues.

### 3. **netstat**
- **Purpose**: Displays network statistics, active connections, and listening ports.
- **Usage**:
  ```bash
  netstat -an
  ```
  This lists all active connections and open ports.

### 4. **curl**
- **Purpose**: Transfers data using various protocols (HTTP, FTP, etc.).
- **Usage**:
  ```bash
  curl -I https://google.com
  ```
  This fetches header information from Google's website.

### 5. **dig**
- **Purpose**: Queries DNS records to resolve domain names.
- **Usage**:
  ```bash
  dig google.com
  ```
  This retrieves DNS information for google.com.

### 6. **nslookup**
- **Purpose**: Resolves domain names to IP addresses.
- **Usage**:
  ```bash
  nslookup google.com
  ```
  This provides the IP address of google.com.

### 7. **ifconfig (Linux/macOS) / ipconfig (Windows)**
- **Purpose**: Displays network interface configurations.
- **Usage**:
  - Linux/macOS:
    ```bash
    ifconfig
    ```
  - Windows:
    ```bash
    ipconfig
    ```
  This shows IP addresses, subnet masks, and other network details.

### 8. **netcat (nc)**
- **Purpose**: Reads and writes data over network connections.
- **Usage**:
  ```bash
  nc -zv google.com 80
  ```
  This checks if port 80 is open on google.com.

### 9. **arp**
- **Purpose**: Displays and manipulates the ARP cache.
- **Usage**:
  ```bash
  arp -a
  ```
  This lists MAC addresses associated with IP addresses on the local network.

### 10. **nmap**
- **Purpose**: Scans networks for open ports and services.
- **Usage**:
  ```bash
  nmap -sS google.com
  ```
  This performs a stealth scan on google.com.

---

# Docker Networking Cheat Sheet

## 1. **docker network ls**
   **Purpose:** Lists all the networks available in Docker.
   **Usage:** 
   ```bash
   docker network ls
   ```
   **Example Output:**
   ```
   NETWORK ID          NAME                DRIVER              SCOPE
   9a2f7b1e2d87        bridge              bridge              local
   2a1dbf8f6981        host                host                local
   6b52ef234ac4        none                null                local
   ```

## 2. **docker network inspect <network_name_or_id>**
   **Purpose:** Provides detailed information about a specific Docker network, including connected containers.
   **Usage:**
   ```bash
   docker network inspect <network_name_or_id>
   ```
   **Example:**
   ```bash
   docker network inspect bridge
   ```

## 3. **docker network create <network_name>**
   **Purpose:** Creates a new Docker network.
   **Usage:**
   ```bash
   docker network create <network_name>
   ```
   **Example:**
   ```bash
   docker network create my_network
   ```

## 4. **docker network rm <network_name_or_id>**
   **Purpose:** Removes a Docker network.
   **Usage:**
   ```bash
   docker network rm <network_name_or_id>
   ```
   **Example:**
   ```bash
   docker network rm my_network
   ```

## 5. **docker run --network <network_name> <image>**
   **Purpose:** Runs a Docker container with a specified network.
   **Usage:**
   ```bash
   docker run --network <network_name> <image>
   ```
   **Example:**
   ```bash
   docker run --network my_network nginx
   ```

## 6. **docker network connect <network_name> <container_name_or_id>**
   **Purpose:** Connects an existing container to a specified network.
   **Usage:**
   ```bash
   docker network connect <network_name> <container_name_or_id>
   ```
   **Example:**
   ```bash
   docker network connect my_network my_container
   ```

## 7. **docker network disconnect <network_name> <container_name_or_id>**
   **Purpose:** Disconnects a container from a specified network.
   **Usage:**
   ```bash
   docker network disconnect <network_name> <container_name_or_id>
   ```
   **Example:**
   ```bash
   docker network disconnect my_network my_container
   ```

## 8. **docker network prune**
   **Purpose:** Removes all unused networks.
   **Usage:**
   ```bash
   docker network prune
   ```
   **Example:** 
   ```bash
   docker network prune
   ```

## 9. **docker run --network host**
   **Purpose:** Runs a container in the host’s network stack. This allows the container to share the host’s network interfaces.
   **Usage:**
   ```bash
   docker run --network host <image>
   ```
   **Example:**
   ```bash
   docker run --network host nginx
   ```

## 10. **docker run --network none**
   **Purpose:** Runs a container without any network. The container will have no access to external resources.
   **Usage:**
   ```bash
   docker run --network none <image>
   ```
   **Example:**
   ```bash
   docker run --network none alpine
   ```

---

### Docker Network Types

- **Bridge:** The default network driver. Used when no network is specified. Containers on the same bridge network can communicate.
- **Host:** Removes network isolation between the container and the host machine. Containers share the host’s network.
- **None:** No network access for the container.
- **Overlay:** Used in Docker Swarm mode for multi-host networking.

----

## Resources 📚
- [Docker Networking Cheat Sheet](https://docs.docker.com/engine/network/)

---
## Updates 🔗
**Follow my journey:** [LinkedIn Profile](https://www.linkedin.com/in/yashbharitkar25learns-cloud/)



