# Week 2: File & Directory Permissions 

## Overview 📖
Understanding file and directory permissions in Linux is crucial for security and access control. In this task, we will create a directory, add a file, and set specific permissions for different users.

---

## Step 1: Creating a Directory 📂
### Create `/devops_workspace` Directory
```bash
mkdir /devops_workspace
```
📌 **Explanation:**
- `mkdir`: Creates a new directory.
- `/devops_workspace`: The name of the directory being created.

---

## Step 2: Creating a File 📄
### Create `project_notes.txt` inside `/devops_workspace`
```bash
sudo touch /devops_workspace/project_notes.txt
```
📌 **Explanation:**
- `touch`: Creates a new empty file.
- `/devops_workspace/project_notes.txt`: File path where the new file is created.

---

## Step 3: Setting Permissions 🔐
### Change File Permissions
```bash
sudo chmod 640 /devops_workspace/project_notes.txt
```
📌 **Explanation:**
- `chmod 640`: Sets the following permissions:
  - **Owner:** Read & Write (6)
  - **Group:** Read (4)
  - **Others:** No Access (0)

---

## Step 4: Verifying Permissions ✅
### Use `ls -l` to Check File Permissions
```bash
ls -l /devops_workspace/project_notes.txt
```
📌 **Explanation:**
- `ls -l`: Lists detailed file information, including permissions.
- Example output:
  ```bash
  -rw-r----- 1 root root 0 Feb 6 10:00 /devops_workspace/project_notes.txt
  ```
  - `rw-` (Owner: Read & Write)
  - `r--` (Group: Read Only)
  - `---` (Others: No Access)

![User and Group](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Creating_dir%20%26%20file.png)

---

## Updates 🔗
📢 Follow my journey: [LinkedIn Profile](https://www.linkedin.com/in/yashbharitkar25learns-cloud/)

---

✅ **Task Completed!** 🚀
