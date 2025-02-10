# Week 2:Task 3- Log File Analysis with AWK, Grep & Sed 

## Overview 📖
Log file analysis is essential in DevOps for monitoring and debugging. This task involves using `grep`, `awk`, and `sed` to extract insights from log files efficiently.

---

## Step 1: Downloading the Log File 📂

Download the log file from the LogHub repository:
```bash
wget https://raw.githubusercontent.com/logpai/loghub/master/Linux/Linux_2k.log
```
📌 **Explanation:**
- `wget`: Fetches the file from the given URL.
-  `Linux_2k.log` Download the file in your current directory.


![Image](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Log%20File.png)

---

## Step 2: Finding All Occurrences of "authentication failure" ❗

Use `grep` to search for authentication failure messages:
```bash
grep -i "authentication failure" Linux_2k.log
```
📌 **Explanation:**
- `-i`: Makes the search case-insensitive.
- Displays all lines containing "authentication failure".


![Image](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/grep%20-i.png)

---

## Step 3: Extracting Timestamps & Log Levels ⏳

Use `awk` to extract timestamps and log levels:
```bash
awk '{print $1, $2, $3}' Linux_2k.log | head -10
```
📌 **Explanation:**
- Extracts the first three fields (assuming timestamp and log level are in these positions).
- `head -10`: Shows only the first 10 entries.

![Image](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/AWK%20.png)
---

## Step 4: Replacing IP Addresses with [REDACTED] 🔒

Use `sed` to anonymize IP addresses:
```bash
sed -E 's/[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}/[REDACTED]/g' Linux_2k.log 
```
##  Verify the Changes
- To check if the replacement worked without modifying the file:
- grep -oE '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' Linux_2k.log
- If no IPs appear in the output, it means they have been replaced.


📌 **Explanation:**
- Finds patterns that match IPv4 addresses.
- Replaces them with `[REDACTED]` for security.

![Image](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Sed%20%5BREDACTED%5D%20.png)
---

## Bonus: Finding the Most Frequent Log Entry 🔍

To find the **most frequent log entry** in a log file using `awk` or `sort | uniq -c | sort -nr | head -10`, follow these steps:

---

### **Using `sort | uniq -c | sort -nr | head -10`**
This method works by sorting the log lines first, counting unique occurrences, sorting them numerically in descending order, and showing the top 10.

```bash
sort Linux_2k.log | uniq -c | sort -nr | head -10
```

#### **Explanation:**
1. **`sort Linux_2k.log`** → Sorts the log file alphabetically.
2. **`uniq -c`** → Counts duplicate entries.
3. **`sort -nr`** → Sorts numerically (`-n`), in reverse order (`-r`).
4. **`head -10`** → Displays the top 10 most frequent log entries.

---

### **Using `awk`**
If you want more flexibility, use `awk`:

```bash
awk '{count[$0]++} END {for (entry in count) print count[entry], entry}' Linux_2k.log | sort -nr | head -10
```

#### **Explanation:**
1. **`awk '{count[$0]++}'`** → Creates an associative array `count` where each log entry (`$0`) is a key, and its occurrences are counted.
2. **`END {for (entry in count) print count[entry], entry}'`** → At the end of processing, it prints the count and the corresponding log entry.
3. **`| sort -nr | head -10`** → Sorts results by frequency in descending order and shows the top 10.

![Image](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Bonus%20.png)
---

## Resources 📚
- [AWK Command Guide](https://www.geeksforgeeks.org/awk-command-unixlinux-examples/)
- [Grep Usage & Examples](https://www.howtogeek.com/518270/how-to-use-the-grep-command-on-linux/)
- [Sed Command Tutorial](https://www.baeldung.com/linux/sed-command)

---

## Updates 🔗
📢 Follow my journey: [LinkedIn Profile](https://www.linkedin.com/in/yashbharitkar25learns-cloud/)

---

✅ **Task Completed!** 🚀
