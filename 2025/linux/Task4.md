#  Week2 -Task4 - Linux Volume Management & Disk Usage

## Step 1: List Available Storage Devices
Before proceeding, check the available storage devices attached to your system. This helps identify the correct disk for partitioning and logical volume creation.
```bash
lsblk  # List block devices and their mount points
```

## Step 2: Check Disk Space
Check the available disk space on the system to ensure there is enough room for creating new logical volumes.
```bash
df -h  # Display human-readable disk usage
```

## Step 3: Create Physical Volume
A Physical Volume (PV) is the first step in setting up LVM. It prepares the disk for volume group creation.
```bash
pvcreate /dev/xvdf /dev/xvdg /dev/xvdh  # Initialize the physical volumes
```
Verify the physical volume creation:
```bash
pvs  # Display physical volumes
```
![Img](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/Attach%20Volume.png)

## Step 4: Create Volume Group
A Volume Group (VG) combines multiple physical volumes into a single storage pool.
```bash
vgcreate tws-vg /dev/xvdf /dev/xvdg  # Create a volume group named tws-vg
```
Verify the volume groups:
```bash
vgs  # Display volume groups
```

## Step 5: Create Logical Volume
A Logical Volume (LV) is created from the volume group. Here, a 10GB logical volume is created.
```bash
lvcreate -L 10G -n tws-lv tws-vg  # Create a 10GB logical volume named tws-lv
```
Verify the logical volume:
```bash
lvs  # Display logical volumes
```

## Step 6: Format the Logical Volume
The logical volume needs to be formatted before it can be used.
```bash
mkfs.ext4 /dev/tws-vg/tws-lv  # Format the LV with ext4 filesystem
```

## Step 7: Create Mount Directory
A directory is needed to mount the logical volume and access its contents.
```bash
mkdir /mnt/tws-lv-mount  # Create a mount directory
```

## Step 8: Mount the Logical Volume
Mount the logical volume to make it accessible for file operations.
```bash
mount /dev/tws-vg/tws-lv /mnt/tws-lv-mount  # Mount LV to the directory
```
Verify the mount:
```bash
df -h  # Check if the volume is mounted successfully
mount | grep tws-lv-mount  # Confirm mount point
```

## Step 9: Create Subdirectory & File
Once mounted, create a directory and a file inside the logical volume.
```bash
cd /mnt/tws-lv-mount
mkdir devops  # Create a directory named 'devops'
cd devops
vim hello-dosto.txt  # Create a text file
```
Verify the file creation:
```bash
cat /mnt/tws-lv-mount/devops/hello-dosto.txt  # Check file contents
```

## Step 10: Unmount the Volume
To safely detach the logical volume, unmount it.
```bash
umount /mnt/tws-lv-mount  # Unmount the logical volume
```
![Img](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/mount-umount.png)

## Step 11: Mount a New Disk
If a new disk is available, format and mount it for additional storage.

Create a new mount directory:
```bash
mkdir /mnt/tws-disk-mount  # Create a mount directory for the new disk
```
Format the new disk:
```bash
mkfs.ext4 /dev/xvdh  # Format the disk with ext4 filesystem
```
Mount the new disk:
```bash
mount /dev/xvdh /mnt/tws-disk-mount  # Mount the disk
```
Verify the mount:
```bash
df -h  # Check if the new disk is mounted
mount | grep tws-disk-mount  # Confirm mount point
```
![Img](https://github.com/Yash2526/90DaysOfDevOps/blob/master/2025/linux/Task%20Images/disk-mount.png)

## Step 12: Extend the Logical Volume
To increase storage capacity, extend the logical volume by adding 5GB.
```bash
lvextend -L +5G /dev/tws-vg/tws-lv  # Extend LV by 5GB
```
Resize the filesystem to reflect the new size:
```bash
resize2fs /dev/tws-vg/tws-lv  # Resize the filesystem
```
Verify the changes:
```bash
df -h  # Check new size
```

## Conclusion
This guide covers:
- Creating a Physical Volume (PV)
- Creating a Volume Group (VG)
- Creating a Logical Volume (LV)
- Mounting and Unmounting Volumes
- Extending Storage Capacity
