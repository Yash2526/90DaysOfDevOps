# Automate Backups with Shell Scripting

## Task Overview
We need to create a shell script that will:
1. Create a backup of the `/devops_workspace` directory.
2. Save the backup file in `/backups` with a timestamped filename.
3. Display a success message in green text.
4. Schedule the script to run automatically using cron.

## Step-by-Step Solution

### Step 1: Creating the Backup Script

Create a shell script named `backup.sh` in your home directory or another suitable location.

#### 1.1 Open a terminal and create the script file:
```bash
vim backup.sh
```

#### 1.2 Write the script inside `backup.sh`:

![img](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/backup.png)

### Step 2: Grant Execution Permission
Make the script executable by running:
```bash
chmod 764 backup.sh
```

### Step 3: Testing the Script
Run the script manually to check if it works:
```bash
./backup.sh
```
If the script runs successfully, it will create a backup file in `/backups` and display a green success message.

![img](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Green%20.png)

### Step 4: Automating with Cron
To schedule the script to run daily, follow these steps:

#### 4.1 Open the crontab editor:
```bash
crontab -e
```

#### 4.2 Add the following line at the end of the file to run the script every day every hour at every two min.
```bash
*/2 * * * * /bin/bash ~/backup.sh /home/ubuntu/90DaysOfDevOps/week_2/devops_workspace /home/ubuntu/backups
```

Save and exit the crontab editor.

### Step 5: Verifying Cron Job
List the cron jobs to confirm the script is scheduled:
```bash
crontab -l
```
![img](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Crontab.png)

