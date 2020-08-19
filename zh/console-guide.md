## Storage > Backup > 控制台使用指南

## 备份agent
添加备份服务器时，要在目标服务器上安装agent。安装agent时需要用户的域名信息。域名信息可以在**添加服务器**页面中确认。

* 用户的域名
```
/TCBackup/{domain-id}
```

> [参考]  
> 域是为了把多台服务器分组后管理而使用的备份系统的一个单元。
> 激活备份服务时会自动创建域。
> 用户的域名下登记备份服务器时，用agent安装命令的参数，输入域名信息。
>

<br/>

### 设置服务器安全组(security group)

如需与备份服务器通信，请在服务器安全组添加以下内容。

| 方向(direction) | 端口 | 地区 | CIDR |
| --- | --- | --- | --- |
| Ingress/Egress | ALL TCP | 韩国（板桥） | 133.186.132.0/24 |
| | | 韩国（坪村） | 133.186.207.4/32, 133.186.207.5/32 |
| | | 日本（东京） | 133.223.17.0/24 |
| Egress | 443 | 韩国（板桥） | 103.243.202.188/32 |
| | | 韩国（坪村） | 103.243.202.188/32 |
| | | 日本（东京） | 119.235.231.50/32 |

<br/>

### 设置备份CLI

* **Linux**

| 地区 | URL |
| --- | --- |
| 韩国（板桥） | http://static.toastoven.net/toastcloud/sdk_download/backup/scripts/linux/bootstrap.sh |
| 韩国（坪村） | http://static.toastoven.net/toastcloud/sdk_download/backup/kr2/scripts/linux/bootstrap.sh |
| 日本（东京） | http://static.toastoven.net/toastcloud/sdk_download/backup/jp/scripts/linux/bootstrap.sh |

```
curl {URL} | bash
```

<br/>

### 安装备份agent

则按如下方式安装agent。

* **Linux**

```
tcbackup install {user-domain}
```

<br/>

* **Windows**

从 [TOAST下载页面](http://docs.toast.com/zh/Download)下载windows agent并安装。安装时需要输入MC Server和MC Domain信息。MC Domain是用户的域信息。在 MC Server中需要输入以下信息。

| 地区 | MC Server |
| --- | --- |
| 韩国（板桥） | tcbackup1.toastmaker.net |
| 韩国（坪村） | kr2-backup-mc1.cloud.toast.com |
| 日本（东京） | tcbackup.nhn-japan.com |

<br/>

### 重新注册备份agent
如备份服务器的主机名变更,需重新注册备份agent,命令如下:

* **Linux**

```
tcbackup re-register
```

<br/>

* **Windows**

下载并运行下面的PowerShell脚本。

[re-register.ps1](http://static.toastoven.net/toastcloud/sdk_download/backup/scripts/windows/re-register.ps1)

<br/>

### 关闭备份agent
如果要短时间暂停备份，可以关闭agent。

* **Linux**

```
tcbackup stop
```

<br/>

* **Windows**

右键单击系统托盘中的备份agent图标，然后点击**关闭**。

<br/>

### 重新启动备份agent
要重新启已关闭的备份agent，使用以下命令。

* **Linux**

```
tcbackup restart
```

<br/>

* **Windows**

在开始菜单中运行**EMC Avamar > Client**。

<br/>

## 添加服务器
备份服务器安装agent后，则可以从**添加服务器**页面的**选择服务器** 项中选择该服务器

<br/>

### 添加备份路径
一台服务器可添加多个备份路径。完成服务器添加后也可以添加备份路径。

* **备份路径**

指定要备份的路径。此时务必准确输入绝对路径。如果输入错误的路径，有可能无法备份或备份的路径有错误。如果把soft link设置为备份路径，则仅备份soft link file。

```
例如)
Windows :   c:\backup
Linux   :   /home/backup
```

<br/>

* **备份周期**

执行备份的周期，可以选择1日间隔或7日间隔。

<br/>

* **备份时间**

开始备份的时间。以1小时为单位选择备份时间。备份时间建议选择文件更改少，服务器空闲的时间段。实际备份开始时间根据当时的情况可能会存在1小时左右的偏差。

<br/>

* **备份保留周期**

备份保留周期可选择7日，14日，21日，30日。

<br/>

### 备份路径目录
在服务器目录中选择服务器名称左侧的复选框，则屏幕下方的详细页面中显示所选服务器的备份路径目录。

<br/>

### 查看备份结果
在备份路径目录中点击备份路径可查看备份结果。备份结果将在备份完成后的30分钟内汇总。

| 备份结果  | 详情                        |
| ------ | --------------------------- |
| 成功     | 备份成功                       |
| 成功(注意) | 已完成备份，但原始文件在备份期间发生了变化 |
| 失败     | 备份失败                       |

> [参考]
> 根据网络状态和备份数据量,设定为同一个时间启用的多个备份计划任务,如3小时之内不能完成,则该计划任务记录为失败。
>

<br/>

### 更改备份政策
在备份路径目录中点击各项目右侧的**变更**按钮来更改备份策略。可更改的项目是“备份周期”，“备份时间”和“保留周期”。

<br/>

## 恢复申请
如果已注册的备份路径的备份次数超过1次以上，则可以使用该数据申请恢复。

* **备份路径**

可以选择用户添加过的备份路径之一

<br/>

* **备份日期**

可以选择备份日期。如果从未备份或备份失败导致没有备份的数据，则会提示没有可用于恢复的数据。

<br/>

* **请求事项**

可以恢复到备份服务器，也可以恢复到新的服务器。

```
例如)
要恢复的服务器的主机名 :   backup.guide
恢复的路径   :   /home/debian
```

<br/>

* **联系方式**

为了顺利进行恢复，输入联系方式用于运营负责人与请求人之间的沟通。我们不存储收集的个人信息，并在恢复完成后立即删除。

恢复进展情况如下表所示。

| 状态   | 详情           |
| ---- | ------------ |
| 接收   | 接收恢复请求   |
| 进行中 | 运营负责人开始恢复 |
| 完成   | 完成恢复        |


<br/>

## 删除服务器

删除服务器之前必须先删除已注册的备份路径。如果存在注册的备份路径，则会显示提示并中止删除。

> [注意]
> 删除服务器的同时删除保留的备份数据。如需备份数据请提前提交恢复请求，将其还原到所需的服务器上。
>

从Web控制台删除服务器后，必须中止服务器上的代理并取消注册。否则，无法重新注册服务器。取消命令如下。

* **Linux**

```
tcbackup uninstall
```

<br/>

* **Windows**

关闭代理。再次使用时需要打开客户端的激活条目输入新的域信息。
