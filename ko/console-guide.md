## Storage > Backup > 콘솔 사용 가이드

백업 서비스를 사용하기 위한 절차는 다음과 같습니다.

## 상품 활성화
백업 서비스는 Storage 카테고리에 있습니다. 서비스 선택 목록에서 Backup을 선택하여 활성화 할 수 있습니다.


## 서버 등록
`[+서버 등록]` 버튼을 클릭하면 서버를 등록할 수 있는 화면으로 전환됩니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_03.png"/>
<br>
[그림 3] 서버 등록 선택
</center>
<br>
<br>

아직 서버에 에이전트를 설치하지 않았기 때문에 선택할 수 있는 서버가 없습니다. 에이전트를 먼저 설치하고 화면에 출력된 `Agent 등록시 입력할 도메인`을 이용하여 등록해야 합니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_04.png"/>
<br>
[그림 4] 서버 등록 화면
</center>
<br>
<br>


### 에이전트 설치
[TOAST의 다운로드 페이지](http://docs.cloud.toast.com/ko/Download)에서 서버에 설치된 OS 종류에 따라 에이전트를 내려받아 설치합니다. 지원하는 OS는 CentOS, Debian, Ubuntu, Windows입니다. 자세한 버전은 개요를 참조하세요.

* CentOS

	```
	# rpm -ivh AvamarClient-linux-sles11-x86_64-7.5.100-183.rpm
	```

* Debian, Ubuntu

	```
	# apt-get update
	# apt-get install -y libxml2
	# dpkg -i AvamarClient-debian4.0-x86_64-7.5.100-183.deb
	```

* Windows

	Windows 서버에서는 내려받은 설치 파일을 실행하면 설치가 진행됩니다. Windows 에이전트는 설치 관리자에서 백업 시스템에 등록하기 위한 정보를 요구합니다. 백업 시스템 URL과 사용자의 도메인 정보를 입력하고 설치를 진행합니다. (이 단계를 건너뛰어도 설치는 진행됩니다. 설치를 완료하고 에이전트 활성화 대화창을 열어 등록 정보를 입력할 수 있습니다.)


<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_05.png"/>
<br>
[그림 5] Windows Agent 등록 정보 입력 대화창
</center>
<br>
<br>


### 에이전트 등록
Linux 서버에서는 다음과 같은 명령을 입력하여 에이전트를 백업 시스템에 등록합니다.

```
# /usr/local/avamar/etc/avagent.d register tcbackup1.toastmaker.net /TCBackup_alpha/cio1hXb6ainRhbMu
avagent.d Info: Client Agent not running.                  [PASSED]
avagent Info <5008>: Logging to /usr/local/avamar/var/avagent.log
avagent.d Info: Client activated successfully.             [  OK  ]
avagent.d Info: Client Agent service started in systemd    [  OK  ]
avagent Info <5008>: Logging to /usr/local/avamar/var/avagent.log
avagent Info <5417>: daemonized as process id 7838
avagent.d Info: Client Agent started.                      [  OK  ]

```

Windows 서버에서는 다음과 같이 활성화 대화창을 열어 등록합니다. 설치 단계에서 입력했다면 이 과정은 생략해도 됩니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_06.png"/>
<br>
[그림 6] Windows 에이전트 활성화 대화창
</center>
<br>
<br>


### 서버 등록
서버 선택 항목 오른쪽의 `[새로고침]` 버튼을 클릭하면 서버 선택 드롭다운 메뉴에서 에이전트가 등록된 서버의 hostname을 확인할 수 있습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_07.png"/>
<br>
[그림 7] 서버와 OS 선택
</center>
<br>
<br>

서버와 OS 종류를 선택하고 `[서버 등록]` 버튼을 클릭해 등록을 완료합니다. 등록한 서버는 서버 목록에서 확인할 수 있습니다. (서버 등록 단계에서 백업 경로를 같이 등록할 수 있지만, 백업 경로 등록은 다음 단계에서 설명합니다.)

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_08.png"/>
<br>
[그림 8] 등록한 서버 목록
</center>
<br>
<br>

## 백업 경로 추가
서버 목록에서 서버를 선택하면 화면 하단에 선택한 서버의 백업 경로 목록이 나타납니다. 아직 백업 경로를 추가하지 않아 목록이 비어 있는 것을 확인할 수 있습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_09.png"/>
<br>
[그림 9] 등록한 백업 경로 목록
</center>
<br>
<br>

`[+ 백업 경로 추가]` 버튼을 클릭해 백업 경로 추가를 위한 대화창을 띄우고 백업할 경로와 백업 정책을 입력합니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_10.png"/>
<br>
[그림 10] 백업 경로 추가
</center>
<br>
<br>

대화창 하단의 `[백업 경로 추가]` 버튼을 클릭하면 완료 알림창이 나타납니다. 추가한 경로는 경로 목록에서 확인할 수 있습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_11.png"/>
<br>
[그림 11] 백업 경로 추가 완료
</center>
<br>
<br>

## 백업 결과 조회
백업 경로 목록에서 백업 경로를 클릭하면 백업 결과를 조회할 수 있습니다. 백업이 한 번도 수행되지 않았다면 빈 목록을, 백업이 한 번이라도 수행됐다면 결과 목록을 볼 수 있습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_12.png"/>
<br>
[그림 12] 한 번도 백업되지 않았을 때의 결과 조회
</center>
<br>
<br>

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_13.png"/>
<br>
[그림 13] 한 번 이상 백업되었을 때의 결과 조회
</center>
<br>
<br>

백업 결과는 백업이 잘 되었다면 `성공`으로, 실패했다면 `실패`로 표시됩니다. 그리고 백업은 잘 되었지만, 백업 도중 파일이 변경되었다면 `성공(주의)`로 표시됩니다.

## 백업 정책 변경

백업 경로 목록에서 각 항목 오른쪽에 있는 `[변경]` 버튼을 클릭하면 백업 정책 변경 대화창이 나타납니다. 변경할 수 있는 항목은 `백업 주기`, `백업 시각`, `보관 주기`입니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_14.png"/>
<br>
[그림 14] 백업 정책 변경 대화창
</center>
<br>
<br>

정책을 변경하고 `[백업 정책 변경]` 버튼을 클릭하면 변경된 정책이 반영됩니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_15.png"/>
<br>
[그림 15] 백업 정책 변경 결과
</center>
<br>
<br>

## 복구 요청
등록한 백업 경로를 1회 이상 백업했다면, 해당 데이터로 복구를 요청할 수 있습니다.

서버를 선택하면 화면 하단의 백업 경로 목록에서 백업/복구를 선택할 수 있는 탭을 찾을 수 있습니다. 복구 탭을 선택하면 `[+ 복구 신청]` 버튼과 선택한 서버에 대한 과거 복구 요청 목록이 나타납니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_16.png"/>
<br>
[그림 16] 복구 신청 목록
</center>
<br>
<br>

`[+ 복구 신청]` 버튼을 클릭하면 복구 신청 대화창이 표시됩니다. 등록한 경로 중 복구를 원하는 경로를 선택할 수 있고, 경로를 선택하면 백업 일자를 선택할 수 있습니다. 한 번도 백업되지 않았거나, 모두 실패하여 복구할 수 있는 백업 데이터가 없다면 복구할 데이터가 없다는 메시지가 표시됩니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_17.png"/>
<br>
[그림 17] 복구 신청 대화창
</center>
<br>
<br>

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_18.png"/>
<br>
[그림 18] 복구할 백업 일자 선택
</center>
<br>
<br>

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_19.png"/>
<br>
[그림 19] 복구할 데이터가 없는 경우의 메시지
</center>
<br>
<br>

복구할 경로와 일자를 선택하고, 요청 사항, 이름, 휴대전화, Email 주소를 입력한 다음 `개인정보 수집 및 이용`에 동의해야 복구 신청을 할 수 있습니다. 동의하지 않으면 `신청` 버튼이 활성화되지 않습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_20.png"/>
<br>
[그림 20] 개인정보 수집 및 이용에 동의하지 않음
</center>
<br>
<br>

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_21.png"/>
<br>
[그림 21] 개인정보 수집 및 이용에 동의
</center>
<br>
<br>

`[신청]` 버튼을 클릭하면 운영자에게 신청 정보가 전달되고 복구 신청 상태를 목록에서 확인할 수 있습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_22.png"/>
<br>
[그림 22] 복구 신청 결과
</center>
<br>
<br>

복구 신청을 하면 진행상태가 `접수`로 표시됩니다. 운영자가 처리를 시작하면 `진행중`으로 변경되며, 처리가 완료되면 `완료`로 표시됩니다.


## 백업 경로 삭제

백업 경로 목록에서 각 항목의 왼쪽 체크박스를 선택하면 `[백업 경로 삭제]` 버튼이 활성화 됩니다. 활성화된 버튼을 클릭하면 경로 삭제 대화창이 나타납니다. 대화창에서 `[확인]` 버튼을 클릭하면 선택한 경로가 제거됩니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_23.png"/>
<br>
[그림 23] 백업 경로를 선택하여 삭제 버튼 활성화
</center>
<br>
<br>

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_24.png"/>
<br>
[그림 24] 백업 경로 삭제 대화창
</center>
<br>
<br>

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_25.png"/>
<br>
[그림 25] 백업 경로 삭제 결과
</center>
<br>

## 서버 삭제

서버 목록에서 각 항목의 왼쪽 체크박스를 선택하면 `[서버 삭제]` 버튼이 활성화 됩니다. 버튼을 클릭하면 서버 삭제 대화창이 나타납니다. `[확인]` 버튼을 클릭하면 선택한 서버가 제거됩니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_26.png"/>
<br>
[그림 26] 서버를 선택하여 삭제 버튼 활성화
</center>
<br>
<br>

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_27.png"/>
<br>
[그림 27] 서버 삭제 대화창
</center>
<br>
<br>

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_28.png"/>
<br>
[그림 28] 서버 삭제 완료
</center>
<br>
<br>

서버를 삭제하기 전에 먼저 등록한 백업 경로를 삭제해야 합니다. 만약 등록된 백업 경로가 있다면 안내 메시지가 나타나고 삭제가 중단됩니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_29.png"/>
<br>
[그림 29] 백업 경로 삭제 안내
</center>
<br>
<br>

서버를 삭제한 후에는 반드시 에이전트를 정지시키고 등록을 해지해야 합니다. 그렇지 않으면 해당 서버를 다시 등록할 수 없습니다. 반드시 다음 명령을 이용하여 에이전트를 정지하고 등록 해지하십시오.

```
# /usr/local/avamar/etc/avagent.d stop
avagent.d Info: Stopping Avamar Client Agent (avagent)...
avagent.d Info: Client Agent stopped.                      [  OK  ]

# /usr/local/avamar/etc/avagent.d unregister

```

Windows의 경우 트레이의 에이전트 아이콘을 우클릭하여 팝업 메뉴를 띄우고 종료를 클릭합니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/getting_started/backup_30.png"/>
<br>
[그림 30] Windows 에이전트 종료
</center>
<br>
<br>
