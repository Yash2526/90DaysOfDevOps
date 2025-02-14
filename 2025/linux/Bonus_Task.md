# Log Analysis and File Search in Linux

## Task Overview
We will perform three key operations using Linux command-line tools:
1. Find the top 5 most common log messages in `Linux_2k.log` using `awk` and `sort`.
2. List all files modified in the last 7 days using `find`.
3. Write a script to extract and display only `ERROR` and `WARNING` logs from `Linux_2k.log`.

---

## Step-by-Step Solution

### Step 1: Find the Top Most Common Log Messages
We will use `awk`, `sort`, and `uniq` to extract and count log messages.

#### **Command to Run:**
```bash
awk '{print $NF}' Linux_2k.log | sort | uniq -c | sort -nr | head 
```
![img](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/New%20AWK%20.png)

#### **Explanation:**
- `awk '{print $NF}' Linux_2k.log` → Extracts the last field (assumed to be the log message).
- `sort` → Sorts the extracted log messages.
- `uniq -c` → Counts the occurrences of each unique log message.
- `sort -nr` → Sorts results numerically in descending order.
- `head ` → Displays the top most frequent messages.

---

### Step 2: List Files Modified in the Last 5 Days
We will use the `find` command to locate recently modified files.

#### **Command to Run:**
```bash
find /path/to/search -type f -mtime -5
```
![img](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/find.png)

#### **Explanation:**
- `/path/to/search` → Replace this with the actual directory to search.
- `-type f` → Searches only for files (not directories).
- `-mtime -5` → Finds files modified within the last 5 days.

---

### Step 3: Extract and Display Only `authentication failure` Logs
We will write a shell script to filter out only `authentication failure` messages from `Linux_2k.log`.

#### **Script: `filter_logs.sh`**

![img](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Bonus%20.png)

## Updates 🔗
📢 Follow my journey: [LinkedIn Profile](https://www.linkedin.com/in/yashbharitkar25learns-cloud/)

✅ **Task Completed!** 🚀
