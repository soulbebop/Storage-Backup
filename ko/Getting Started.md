## Infrastructure > Backup > Getting Started
```
※ 이 상품은 alpha 개발 단계입니다. 사용에 관심이 있으신 분은 **support@cloud.toast.com** 으로 문의해 주시기 바랍니다.
```

Backup 상품을 사용하기 위한 절차는 다음과 같습니다.

## 백업 대상 준비
### Avamar Agent 설치 
[TOAST Cloud의 다운로드 페이지](http://docs.cloud.toast.com/ko/Download)에서 서버 OS에 해당하는 Agent를 내려받아 설치합니다.

지원하는 OS는 CentOS, Debian, Ubuntu, Windows입니다.

* CentOS

	```
	# rpm -ivh AvamarClient-linux-sles11-x86_64-7.5.100-183.rpm
	```

* Debian, Ubuntu

	```
	# dpkg -i AvamarClient-debian4.0-x86_64-7.5.100-183.deb
	```

* Windows

	Windows에서는 내려받은 설치 파일을 실행하면 설치가 진행됩니다.


## 상품 활성화
Backup 상품은 TOAST Cloud의 Infrastructure 메뉴에서 선택할 수 있습니다. Project List 화면에서 권한이 있는 프로젝트의 목록을 확인하고 Backup 상품을 추가할 프로젝트를 선택한 다음 왼쪽 메뉴에서 `Infrastructure > Backup`을 선택합니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_02.png"/>
<br>
[그림 2] Backup 상품 선택
</center>
<br>

상품 페이지에서 `상품 이용` 버튼을 클릭하면 상품을 활성화됩니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_03.png"/>
<br>
[그림 3] 상품 이용 선택
</center>
<br>

## 서버 등록 
`서버 등록` 버튼을 클릭하면 서버를 등록할 수 있는 화면으로 전환됩니다. 

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_04.png"/>
<br>
[그림 4] 서버 등록 선택
</center>
<br>

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_05.png"/>
<br>
[그림 5] 서버 등록 화면
</center>
<br>

아직 서버의 에이전트를 백업 시스템에 등록하지 않은 상태이므로 선택할 수 있는 서버가 없습니다. `Agent 등록시 입력할 도메인`을 이용하여 에이전트를 등록해야합니다. 

다음과 같은 명령을 입력하여 에이전트를 백업 시스템에 등록합니다.

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

서버 등록 화면을 다시 띄우면 서버 선택 드롭다운 메뉴에 등록한 서버의 hostname을 확인할 수 있습니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_06.png"/>
<br>
[그림 6] 서버 선택
</center>
<br>

서버와 OS 종류를 선택하고 `서버 등록` 버튼을 클릭해 등록을 완료합니다. 등록을 완료하면 서버 목록에서 등록한 서버를 확인할 수 있습니다. (서버 등록 단계에서 백업 경로를 같이 등록할 수 있지만, 백업 경로 등록은 다음 단계에서 설명합니다.)

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_07.png"/>
<br>
[그림 7] 등록한 서버 목록
</center>
<br>


## 백업 경로 추가 
서버 목록에서 서버를 선택하면 화면 하단에 해당 서버의 백업 경로 목록이 나타납니다. 아직 백업 경로를 추가하지 않아 목록이 비어 있는 것을 확인할 수 있습니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_08.png"/>
<br>
[그림 8] 등록한 백업 경로 목록
</center>
<br>

`백업 경로 추가` 버튼을 클릭해 백업 경로 추가를 위한 대화창을 띄우고 백업할 경로와 백업 정책을 입력합니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_09.png"/>
<br>
[그림 9] 백업 경로 추가
</center>
<br>

`백업 경로 추가` 버튼을 클릭하면 완료 알림창이 나타납니다. 그리고 백그라운드의 백업 경로 목록에서 추가한 경로를 확인할 수 있습니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_10.png"/>
<br>
[그림 10] 백업 경로 완료
</center>
<br>

## 백업 결과 조회
백업 경로 목록에서 백업 경로를 클릭하면 백업 결과를 조회할 수 있습니다. 백업이 한 번도 수행되지 않았다면 빈 목록을, 백업이 한 번이라도 수행됐다면 결과 목록을 볼 수 있습니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_11.png"/>
<br>
[그림 11] 백업이 한 번도 수행되지 않았을 때의 백업 결과 조회
</center>
<br>

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_12.png"/>
<br>
[그림 12] 백업 결과 조회
</center>
<br>

백업 결과는 정상적으로 백업이 잘 되었다면 `성공`으로 실패했다면 `실패`로 표시됩니다. 그리고 백업은 잘 되었지만, 백업 도중 파일이 변경되었다면 `성공(주의)`로 표시됩니다.

## 백업 정책 변경

백업 경로 목록에서 각 항목 오른쪽에 있는 `변경` 버튼을 클릭하면 [그림 13]과 같이 백업 정책 변경 대화창이 나타납니다. 변경할 수 있는 항목은 `백업 주기`, `백업 시각`, `보관 주기`입니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_13.png"/>
<br>
[그림 13] 백업 정책 변경 대화창
</center>
<br>

정책을 변경하고 `백업 정책 변경` 버튼을 클릭하면 변경된 정책이 반영됩니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_14.png"/>
<br>
[그림 14] 백업 정책 변경 결과
</center>
<br>

## 백업 경로 삭제

백업 경로 목록에서 각 항목의 왼쪽 체크박스를 선택하고 `백업 경로 삭제` 버튼을 클릭하면 경로 삭제 대화창이 나타납니다. `확인` 버튼을 클릭하면 선택한 경로가 제거됩니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_15.png"/>
<br>
[그림 15] 백업 경로 삭제 대화창
</center>
<br>

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_16.png"/>
<br>
[그림 16] 백업 경로 삭제 결과
</center>
<br>

## 복구 요청 
등록한 백업 경로를 1회 이상 백업했다면, 해당 데이터로 복구를 요청할 수 있습니다. 

서버를 선택하면 화면 하단의 백업 경로 목록에서 백업/복구를 선택할 수 있는 탭을 찾을 수 있습니다. 복구 탭을 선택하면 `복구 신청` 버튼과 선택한 서버에 대한 복구 요청 목록이 나타납니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_17.png"/>
<br>
[그림 17] 복구 신청 목록
</center>
<br>

`복구 신청` 버튼을 클릭하면 복구 신청 대화창이 표시됩니다. 등록한 경로 중 복구를 원하는 경로를 선택할 수 있고, 경로를 선택하면 백업 일자를 선택할 수 있습니다. 한 번도 백업되지 않았거나, 모두 실패하여 복구할 수 있는 백업 데이터가 없다면 복구할 데이터가 없다는 메시지가 표시됩니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_18.png"/>
<br>
[그림 18] 복구 신청 대화창
</center>
<br>

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_19.png"/>
<br>
[그림 19] 복구할 백업 일자 선택
</center>
<br>

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_20.png"/>
<br>
[그림 20] 복구할 데이터가 없는 경우의 메시지
</center>
<br>

복구할 경로와 일자를 선택하고, 이름과 휴대전화, Email 주소를 입력한 다음 `개인정보 수집 및 이용`에 동의해야 복구 신청을 할 수 있습니다. 동의하지 않으면 `신청` 버튼이 활성화되지 않습니다. 

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_21.png"/>
<br>
[그림 21] 개인정보 수집 및 이용에 동의하지 않음
</center>
<br>

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_22.png"/>
<br>
[그림 22] 개인정보 수집 및 이용에 동의
</center>
<br>

`신청` 버튼을 클릭하면 운영자에게 신청 정보가 전달되고 복구 신청 상태를 목록에서 확인할 수 있습니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_23.png"/>
<br>
[그림 23] 복구 신청 결과
</center>
<br>


복구 신청을 하면 진행상태가 `접수`로 표시됩니다. 운영자가 처리를 시작하면 `진행중`으로 변경되며, 처리가 완료되면 `완료`로 표시됩니다.


## 서버 삭제

서버 목록에서 각 항목의 왼쪽 체크박스를 선택하고 `서버 삭제` 버튼을 클릭하면 서버 삭제 대화창이 나타납니다. `확인` 버튼을 클릭하면 선택한 서버가 제거됩니다. 

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_24.png"/>
<br>
[그림 24] 서버 삭제 대화창
</center>
<br>

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_25.png"/>
<br>
[그림 25] 서버 삭제 완료 
</center>
<br>

서버를 삭제하기 전에 먼저 등록한 백업 경로를 삭제해야 합니다. 만약 등록된 백업 경로가 있다면 안내 메시지가 나타나고 삭제가 중단됩니다.

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_26.png"/>
<br>
[그림 26] 서버 삭제 불가 안내 메시지
</center>
<br>

서버를 삭제한 후에는 반드시 에이전트를 정지시키고 등록을 해지해야 합니다. 해지하지 않으면 해당 서버를 다시 등록할 수 없습니다. 반드시 다음 명령을 이용하여 에이전트를 정지하고 등록 해지하십시오.

```
# /usr/local/avamar/etc/avagent.d stop
avagent.d Info: Stopping Avamar Client Agent (avagent)...
avagent.d Info: Client Agent stopped.                      [  OK  ]

# /usr/local/avamar/etc/avagent.d unregister

```

## 상품 이용 종료 
상품 이용을 종료할 때도 등록된 서버가 없어야 합니다. 모든 서버를 삭제하여 등록된 서버가 없는 상태에서 상단의 `이용 종료` 버튼을 클릭하면 Backup 상품 이용이 종료됩니다. 

<br>
<center>
<img src="/Users/arzhna/project/iaas/backup/guide_images/backup_27.png"/>
<br>
[그림 27] 상품 이용 종료
</center>
<br>

