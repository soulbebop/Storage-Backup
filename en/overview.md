## Storage > Backup > Overview

Backup refers to creating and safely saving copies, in preparation against potential data loss, out of security threats, user's operational mistakes, failure in saving devices, or natural disasters. Saved copies may be used to restore data.  

TOAST Backup adopts both Full Backup and Incremental Backup. The initial backup regards the entire data of routes that user registered. In later times, only changes since the last backup are contained, by using variable-length deduplication, which can minimize backup data by removing duplicates.  Therefore, time, as well as network usage volume, can be saved. Data, meanwhile, is encrypted and safely transmitted to the backup storage.

TOAST Backup provides a web console environment, in which backup policy is conveniently registered, history is retrieved, and requests for backup are made.

## Service Features
* Supports various operating systems;
* Optimized to virtual environment;
* Backup is available without service suspension; and,
* Provides user-defined backup policy where the cycle, hour, and retention cycle can be set.

### Backup Cycle
Choose either daily or weekly.

### Backup Time
Select a backup start time by the hour. It is recommended to select time, when file change is the least and server is idle.  Actual start time may differ up to 1 hour, depending on the situation.  

### Retention Cycle
Choose one of 7 days, 14 days, 21 days, or 30 days.

### Retrieve Results
User can retrieve backup results in the web console within half an hour to the latest, after backup is completed. User shall be reported by email on failure of backup. If a backup is not done for up to three hours, it shall be recorded as a failure.

## Operating Systems Supported by TOAST
TOAST supports the following operating systems:

| OS | Hardware Architecture | Supportive Version | Supportive Configuration |
| --- | --- | --- | --- |
| CentOS | x64 | 6.10, 7.5 | ext2, ext3, ext4, xfs |
| Ubuntu | x64 | 16.04 LTS<br/>8.04 LTS | ext2, ext3, ext4 |
| Debian | x64 | 9, 10 | ext2, ext3, ext4 |
| Windows Server | x64 | 2012 R2 STD<br/>2016 STD<br/>2019 STD | NTFS |

## Application Procedure for Restoration
Restoration is processed by user's application, to be followed by operator's confirmation. For flawless processing, the operator may contact users.  

1. Select a server to restore.
2. Click **Apply for Restoration** in the **Restoration** tab.
3. Fill in the content and click **Apply**.

Restoration, when applied, is completed within three business hours, or in the following day, if application is made after business hours.

Restoration is available only during business hours (10am to 6pm weekdays), with the operator's confirmation.

## Charges  
When a server is registered, basic monthly price shall be charged, with more charges to be added, depending on the number of registered servers and storage volume. Basic monthly prices is applied for two servers and 100GB of storage volume.  

## Reference  
### Backup Software
DELL EMC AVAMAR

### Installation Location of Backup Program
* Linux : /usr/local/avamar
* Windows : C:\Program Files\avs

### Demonstration (Process) Information
* Linux : /usr/local/avamar/bin/avagent.bin
* Windows : Avamar Backup Client
