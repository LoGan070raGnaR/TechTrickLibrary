# Resolving Pen Drive Displaying Less Space Than Actual

## Understanding the Issue

If your pen drive is showing less storage capacity than its actual size, there are several possible reasons for this occurrence:

1. Abruptly removing the pen drive while it is in use.
2. Interruptions during the formatting process or inappropriate usage of third-party software.
3. Installation of bootable operating systems like Chrome or Linux, which may alter the partition system and result in free space reduction.
4. Infection by computer viruses or malware.

However, there is no need to panic, as there are effective solutions available to address this problem and restore the full storage capacity of your pen drive.

## Solution for Pen Drive Showing Less Space

### Utilizing Diskpart to Maximize Pen Drive Capacity

The simplest method involves using Diskpart, a built-in Windows tool. Follow these steps:

1. Connect the pen drive to your computer and ensure its detection.


2. Open the Start menu, search for "Command Prompt," right-click on its shortcut, and select "Run as administrator."


3. Type `diskpart` and press Enter.
```cmd
diskpart
```
4. Enter `list disk` and press Enter to display the connected disks.
```cmd
list disk 
```

5. Identify your pen drive by its corresponding number and enter `select disk #` (replace # with the appropriate number).
```cmd
select disk # 
```

6. Input `clean` and press Enter to remove all existing partitions from the pen drive.
```cmd
clean 
```

7. Once you receive the message "Diskpart succeeded in cleaning the disk," enter `create partition primary` to generate a new primary partition.
```cmd
create partition primary 
```
If you want to create more than one partition on the pen drive, specify the partition size by this syntax: `create partition primary size=#`(replace # with the appropriate number). For example, to create a 7000MB partition, run the command “create partition primary size=7000”.
```cmd
create partition primary size=#
```

8. You can now format the pen drive using Disk Management or Diskpart.

## Summary

This guide has provided a solution to address the issue of a pen drive displaying less storage space than its actual capacity. By utilizing the Diskpart tool, you can maximize the capacity of your pen drive. Remember to back up your data before proceeding with any operations to prevent data loss.

 
