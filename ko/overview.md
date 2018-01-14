## Storage > Backup > 개요

## 백업
백업은 데이터 손실에 대비하여 복제본을 만들어 보관해주고, 손실이 발생하면 보관된 복제본을 이용하여 복구해주는 서비스입니다.

해킹, 랜섬웨어와 같은 악성코드 등의 보안 위협이 날로 커지고 있습니다. 랜섬웨어에 의한 데이터 손실로 기업이 파산에 이르는 사건이 있었을 정도입니다. 이와 같은 보안 위협에 대비하여 데이터를 안전하게 보관하려는 요구 역시 증가하고 있습니다. 백업은 보안 위협, 사용자의 조작 실수, 저장장치의 고장, 자연재해 등으로 인한 데이터 손실에 대비해 여러 벌의 복제본을 만들어 서로 다른 장소에 보관하는 방법입니다. 이러한 대비책은 ICT 기술이 발전하기 이전부터 사용됐습니다. 오늘날 완벽하게 보존된 조선왕조실록을 볼 수 있는 것은 조선의 철저한 백업 정책에 따른 결과입니다.

TOAST의 백업 서비스는 DELL EMC의 Avamar 솔루션을 사용합니다. Avamar는 데이터의 중복을 제거하여 백업 데이터를 최소화할 수 있는 가변 길이 중복제거(Variable-Length Deduplication) 기술을 이용하며 최초 전체 백업 이후에는 증분만을 백업합니다. 따라서 백업 시간이 단축되고 네트워크 사용량도 줄어듭니다. 또한, 백업 데이터를 암호화하여 클라우드에 전송하므로 네트워크상의 보안 위협에도 안전합니다. 백업된 증분들은 한 번의 작업으로 즉각 복구할 수 있도록 전체 백업 본으로 유지됩니다.

TOAST의 백업 서비스는 간편하게 백업 정책을 등록하고, 백업 이력을 조회하고, 복구 요청을 할 수 있는 웹 콘솔 환경을 제공합니다. 백업 결과는 매일 취합되어 사용자의 메일로 보고됩니다.

## 서비스 특징
* DELL EMC의 Avamar 솔루션을 사용하여 높은 신뢰성과 가용성, 안정성을 제공합니다.
* 다양한 운영체제를 지원합니다.
* 가상화 환경에 최적화되었습니다.
* 서비스를 중단하지 않고 백업할 수 있습니다.
* 백업 주기와 백업 시각, 보관 주기를 설정할 수 있는 사용자 정의 백업 정책을 제공합니다.

### 백업 주기
1일 간격과 7일 간격을 선택할 수 있습니다.

### 백업 시각
1시간 단위로 백업 시작 시각을 선택할 수 있습니다.

### 백업 보관주기
7일, 14일, 21일, 30일의 보관 주기를 선택할 수 있습니다.


## 백업 서비스 지원 OS

* **Linux**

| Operating System | Vendor | Hardware Architecture | Supported Vendor Version | Supported Configurations |
| ---------------- | ------ | --------------------- | ------------------------ | ------------------------ |
| Linux | CentOS_Linux | x64 | 5.x | ext2, ext3, ext4, xfs |
| Linux | CentOS_Linux | x86 | 5.x | ext2, ext3, ext4, xfs |
| **<span style="color:#207de5">Linux</span>** | **<span style="color:#207de5">CentOS_Linux</span>** | **<span style="color:#207de5">x64</span>** | **<span style="color:#207de5">6.x, 7.x</span>** | **<span style="color:#207de5">ext2, ext3, ext4, xfs</span>** |
| Linux | CentOS_Linux | x86 | 6.x | ext2, ext3, ext4, xfs |
| **<span style="color:#207de5">Linux</span>** | **<span style="color:#207de5">Debian</span>** | **<span style="color:#207de5">x64</span>** | **<span style="color:#207de5">6.x, 7.x, 8.x</span>** | **<span style="color:#207de5">ext2, ext3, ext4</span>** |
| Linux | Debian | x86 | 6.x, 7.x, 8.x | ext2, ext3, ext4 |
| Linux | Novell Open Enterprise Server | x64 | OES 2 | Nssvol |
| Linux | Novell Open Enterprise Server | x64 | OES 11 | Nssvol |
| Linux | Oracle_Linux | x86 | 5 | ext2, ext3, ext4 |
| Linux | Oracle_Linux | x64 | 5 | ext2, ext3, ext4 |
| Linux | Oracle_Linux | x86 | 6 | ext2, ext3, ext4 |
| Linux | Oracle_Linux | x64 | 6, 7 | ext2, ext3, ext4 |
| Linux | Red Hat Enterprise Linux | x86 | AS, ES, WS, 5, 6 | ext2, ext3, ext4, xfs |
| Linux | Red Hat Enterprise Linux | x64 | AS, ES, WS, 5, 6, 7.0, 7.1, 7.2, 7.3 | ext2, ext3, ext4, xfs |
| Linux | Red Hat Enterprise Linux | IBM\_System\_Z | AS, ES, WS, 5, 6, 7.0, 7.1, 7.2, 7.3 | ext2, ext3, ext4, xfs |
| Linux | SuSE Linux Enterprise Server | x64 | 10, 11, 12 | ext2, ext3, ext4, reiserfs, xfs, brtfs |
| Linux | SuSE Linux Enterprise Server | x86 | 10, 11 | ext2, ext3, ext4, reiserfs, xfs |
| Linux | SuSE Linux Enterprise Server | IBM\_System\_Z | 10, 11, 12 | ext2, ext3, ext4, reiserfs, btrfs |
| Linux | SuSE Linux Enterprise Server | x64 | 12 SP1 | ext2, ext3, ext4, reiserfs, xfs, brtfs |
| Linux | Ubuntu | x64 | 10.04 LTS, 12.10, 13.04, 13.10 | ext2, ext3, ext4 |
| Linux | Ubuntu | x86 | 10.04 LTS, 12.10, 13.04, 13.10 | ext2, ext3, ext4 |
| **<span style="color:#207de5">Linux</span>** | **<span style="color:#207de5">Ubuntu</span>** | **<span style="color:#207de5">x64</span>** | **<span style="color:#207de5">12.04 LTS, 14.04 LTS</span>** | **<span style="color:#207de5">ext2, ext3, ext4</span>** |
| Linux | Ubuntu | x86 | 12.04 LTS, 14.04 LTS | ext2, ext3, ext4 |
| **<span style="color:#207de5">Linux</span>** | **<span style="color:#207de5">Ubuntu</span>** | **<span style="color:#207de5">x64</span>** | **<span style="color:#207de5">16.04 LTS</span>** | **<span style="color:#207de5">ext2, ext3, ext4</span>** |
| Linux | Ubuntu | x86 | 16.04 LTS | ext2, ext3, ext4 |

* **Windows**

| Operating System | Vendor | Hardware Architecture | Supported Vendor Version | Supported Configurations |
| ---------------- | ------ | --------------------- | ------------------------ | ------------------------ |
| Windows | Microsoft Windows 7 | x64 | Windows 7 Professional, Ultimate, Enterprise |  |
| Windows | Microsoft Windows 7 | x86 | Windows 7 Professional, Ultimate, Enterprise |  |
| Windows | Microsoft Windows Server 2008 | x64 | RTM, SP2, Web, Standard, Enterprise, Datacenter |  |
| Windows | Microsoft Windows Server 2008 | x86 | RTM, SP2, Web, Standard, Enterprise, Datacenter |  |
| **<span style="color:#207de5">Windows</span>** | **<span style="color:#207de5">Microsoft Windows Server 2008_R2</span>** | **<span style="color:#207de5">x64</span>** | **<span style="color:#207de5">Standard, Enterprise, Datacenter</span>** | **<span style="color:#207de5">n-node active/passive, active/active cluster</span>** |
| Windows | Microsoft Windows Server 2012 | x64 | (all editions) |  |
| **<span style="color:#207de5">Windows</span>** | **<span style="color:#207de5">Microsoft Windows Server 2012_R2</span>** | **x64** | **<span style="color:#207de5">(all editions)</span>** |  |
| **<span style="color:#207de5">Windows</span>** | **<span style="color:#207de5">Microsoft Windows Server 2016</span>** | **x64** | **<span style="color:#207de5">(all editions)</span>** |  |
| Windows | Microsoft Windows Storage Server 2008 | x64 | (all editions) |  |
| Windows | Microsoft Windows Storage Server 2008_R2 | x64 | (all editions) |  |
| Windows | Microsoft Windows Storage Server 2012 | x64 | (all editions) |  |
| Windows | Microsoft Windows Storage Server 2012_R2 | x64 | (all editions) |  |
| Windows | Microsoft Windows Vista | x64 | Windows Vista Basic, Premium, Enterprise |  |
| Windows | Microsoft Windows Vista | x86 | Windows Vista Basic, Premium, Enterprise |  |
| Windows | Microsoft Windows_10 | x64 | Windows 10 Home, Pro, and Enterprise |  |
| Windows | Microsoft Windows_10 | x86 | Windows 10 Home, Pro, and Enterprise |  |
| Windows | Microsoft Windows_8 | x64 | Windows 8 Basic, Pro, Enterprise |  |
| Windows | Microsoft Windows_8 | x86 | Windows 8 Basic, Pro, Enterprise |  |
| Windows | Microsoft Windows_8.1 | x64 | (all editions) |  |
| Windows | Microsoft Windows_8.1 | x86 | (all editions) |  |
