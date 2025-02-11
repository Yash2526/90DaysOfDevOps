
# 📌 Task5 - Process Management & Monitoring

## 🏆 **Task Overview**
In this task, we will:
- Start a **background process**.
- Use **ps, top, and htop** to monitor it.
- Kill the process and verify its termination.

---

## 🛠️ **Step-by-Step Solution**

### **Step 1: Start a Background Process**
Start a continuous ping process and redirect output to a log file:

```bash
ping google.com > ping_test.log &
```

🔹 **Explanation:**
- `ping google.com` sends continuous ICMP requests.
- `>` redirects output to `ping_test.log`.
- `&` runs the command in the **background**.

✅ **Verify:**
```bash
jobs
```

---

### **Step 2: Monitor the Process**
Use different commands to track the running process:

1. **Check running processes:**
   ```bash
   ps aux | grep ping
   ```
2. **Real-time monitoring with top:**
   ```bash
   top
   ```
3. **Better visualization with htop (if installed):**
   ```bash
   htop
   ```
   🔹 Use arrow keys to navigate & `F9` to kill a process.

✅ **Verify:** The ping process should be visible in the process list.

---

### **Step 3: Kill the Process**
Find the **PID (Process ID)**:
```bash
ps aux | grep ping
```

Kill the process using its PID:
```bash
sudo kill <PID>
```

Or force kill if needed:
```bash
sudo kill -9 <PID>
```

✅ **Verify:**
```bash
ps aux | grep ping
```
If no output, the process is successfully killed. 🎯

![IMG](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Ping-Kill.png)
---


Happy Learning! 🚀💡

