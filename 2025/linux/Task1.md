
# Week 2 : Task1-User & Group Management

## Overview 📖
Understanding user and group management in Linux is essential for security and access control. This task involves creating users, managing groups, setting permissions, and restricting SSH login.

### Step 1: Creating a User and Group 👥
Create a User devops_user  
Run the following command to create a new user:

```bash
sudo useradd -m devops_user
```

📌 **Explanation:**

`-m`: Creates a home directory for the user.

Create a Group devops_team

```bash
sudo groupadd devops_team
```

📌 **Explanation:**

This creates a new group named devops_team.

Add devops_user to devops_team

```bash
sudo usermod -aG devops_team devops_user
```

📌 **Explanation:**

`-aG`: Appends the user to the specified group.

![User and Group](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/user_group.png)

### Step 2: Granting Sudo Access 🛡️
Add devops_user to sudo group

```bash
sudo usermod -aG sudo devops_user
```

📌 **Explanation:**

Grants admin privileges to the user.

![Grant Sudo Access](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/grand%20sudo%20access.png)

![DevOps User](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/devops_user.png)

![DevOps Team](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/devops_team.png)

### Step 3: Restricting SSH Login
Edit SSH Configuration  
Open the SSH configuration file:

```bash
sudo nano /etc/ssh/sshd_config
```

Find the AllowUsers or DenyUsers section and modify it as follows:

```bash
DenyUsers devops_user
```

Save the file and restart SSH:

```bash
sudo systemctl restart sshd
```

📌 **Explanation:**

Prevents devops_user from logging in via SSH.

![Restrict SSH](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Restrict%20SSH.png)

![Deny SSH](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Deny%20SSH(2).png)

![Allow SSH](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Allow%20SSH.png(1).png)

## Resources 📚
- [Linux User Management Guide](https://example.com)
- [Give SUDO Access to a User using SUDOERS](https://example.com)
- [Allow Or Deny Selected Users/Groups To Login Via SSH in Linux](https://example.com)

## Updates 🔗
📢 Follow my journey: [LinkedIn Profile](https://www.linkedin.com/in/yash2526)

✅ **Task Completed!** 🚀
```
