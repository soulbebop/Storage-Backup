## Storage > Backup > Console Guide

## Backup Agent
To register a backup server, agent must be installed in the server. User's domain information is required to install an agent: check domain information on the **Register Server** page.

* User's domain
```
/TCBackup/{domain-id}
```

> [Note]  
> Domain is the unit of the backup system used to manage many servers in groups.
> It is automatically created if backup service is enabled.
> To register a backup server in user's domain, enter domain information with the parameter commanding agent installation.
>

<br/>

### Security Group Configuration

To communicate with the backup server, add the following to the server security group.

| Direction | Port | Region | CIDR |
| --- | --- | --- | --- |
| Ingress/Egress | ALL TCP | KOREA (Pangyo) | 133.186.132.0/24 |
| | | KOREA (Pyeongchon) | 133.186.207.4/32, 133.186.207.5/32 |
| | | JAPAN (Tokyo) | 133.223.17.0/24 |
| Egress | 443 | KOREA (Pangyo) | 103.243.202.188/32 |
| | | KOREA (Pyeongchon) | 103.243.202.188/32 |
| | | JAPAN (Tokyo) | 119.235.231.50/32 |

<br/>

### Install Backup CLI

* **Linux**

| Region | URL |
| --- | --- |
| KOREA (Pangyo) | http://static.toastoven.net/toastcloud/sdk_download/backup/scripts/linux/bootstrap.sh |
| KOREA (Pyeongchon) | http://static.toastoven.net/toastcloud/sdk_download/backup/kr2/scripts/linux/bootstrap.sh |
| JAPAN (Tokyo) | http://static.toastoven.net/toastcloud/sdk_download/backup/jp/scripts/linux/bootstrap.sh |

```
curl {URL} | bash
```

<br/>

### Install Backup Agent

Install agent as below:

* **Linux**

```
tcbackup install {user-domain}
```

<br/>

* **Windows**

For Windows agent, download from [Downloads of TOAST](http://docs.toast.com/en/Download) and install. MC Server and MC Domain are required for installation: MC Domain refers to user's domain information and MC Server requires the following:  

| Region | MC Server |
| --- | --- |
| KOREA (Pangyo) | tcbackup1.toastmaker.net |
| KOREA (Pyeongchon) | kr2-backup-mc1.cloud.toast.com |
| JAPAN (Tokyo) | tcbackup.nhn-japan.com |

<br/>

### Re-register Backup Agent
If the host name of backup server has changed, agent needs to be re-registered. Here's the command:

* **Linux**

```
tcbackup re-register
```

<br/>

* **Windows**

Download and execute the PowerShell script as below.

[re-register.ps1](http://static.toastoven.net/toastcloud/sdk_download/backup/scripts/windows/re-register.ps1)

<br/>

### Close Backup Agent
To suspend backup for a while, you can close an agent.

* **Linux**

```
tcbackup stop
```

<br/>

* **Windows**

Right-click the backup agent icon in the system tray and press **Close**.

<br/>

### Restart Backup Agent
To restart the closed backup agent, use the following command:

* **Linux**

```
tcbackup restart
```

<br/>

* **Windows**

Execute **EMC Avamar > Client** on the start menu.

<br/>

## Register Server
Install agent in the backup server and select a server in which agent is registered from **Select Servers** in **Register Servers**.

<br/>

### Add Backup Routes
Many backup routes can be added to a server: adding routes is available after server registration is completed.

* **Backup Routes**

Specify a route for backup. Make sure the route is entered correctly; otherwise, backup may fail or end up in a wrong route. When soft link is set as the backup route, only soft link file is backed up.

```
e.g)
Windows :   c:\backup
Linux   :   /home/backup
```

<br/>

* **Backup Cycle**

Cycle of backup execution: choose either daily or weekly.

<br/>

* **Backup Time**

Start time of backup: select by the hour. It is recommended to select time when file change is the least and server is idle. Actual backup start time may differ up to 1 hour, depending on the situation.

<br/>

* **Retention Cycle**

Retention period for backed up copies: choose one of 7 days, 14 days, 21 days, or 30 days.

<br/>

### List of Backup Routes
Check the server name on the left of the server list, and backup routes of the selected server will be listed at the bottom of the page.   

<br/>

### Retrieve Results
Click a backup route on the list to retrieve the result of backup, which is collected within half an hour to the latest, after backup completion time.  

| Backup Result             | Description                                                  |
| ------------------------- | ------------------------------------------------------------ |
| Successful                | Backup succeeded                                             |
| Successful (with caution) | Backup is completed, but original file has changed during backup |
| Failed                    | Backup failed                                                |

> [Note]
> If a backup is not done within three hours, due to network status, volume of backup data, and lots of backup schedule configured to start all at once, it shall be recorded as a failure.
>

<br/>

### Change of Backup Policy

Click **Change** on the right of each item from the list of backup routes to change backup policy: items available to change are `Backup Cycle`, `Backup Time`, `Retention Cycle`.

<br/>

## Apply for Restoration
If a registered backup route has been backed up more than once, restoration of data can be applied.

* **Backup Route **

User can select one of the added backup routes.   

<br/>

* **Backup Date**

Select a date when a copy to restore was backed up. When there is no backup data since all has failed, message will show there is no data to restore.

<br/>

* **Requests**

Feel free to request for details required for restoration. Restoration can be made to the backup server, or to a new server.  

```
e.g)
Host name of the server to recover  : backup.guide
Path to recover : /home/debian
```

<br/>

* **Contact **

Enter contact information to serve as a dialogue channel between administrator and requester for flawless restoration. Collected personal information shall not be saved, to be immediately discarded when restoration is completed.

Restoration status is displayed as below:

| Status     | Description                                    |
| ---------- | ---------------------------------------------- |
| Received   | Application for restoration has been received. |
| Processing | Operator started restoration.                  |
| Completed  | Restoration has been completed.                |

<br/>

## Delete Servers

Must delete a registered backup route before deleting a server: if there is a registered backup route, message shows and deletion stops.  

> [Caution]
> If a server is deleted, its retained backup data shall also be deleted. If you need backup data, ask for restoration in advance and restore it to the server you need.  

After a server is deleted from the web console, stop agent from the server and cancel its registration: otherwise, the server cannot be registered again.  

* **Linux**

```
tcbackup uninstall
```

<br/>

* **Windows**

Close the agent: to use it again, open Enable Client and enter new domain information.
