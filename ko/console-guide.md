## Storage > Backup > 콘솔 사용 가이드

백업 서비스를 사용하기 위한 절차는 다음과 같습니다.

## 상품 활성화
백업 서비스는 `Storage` 카테고리에 있습니다. 서비스 선택 목록에서 `Backup`을 선택하여 활성화할 수 있습니다.


## 서버 등록
`[+서버 등록]` 버튼을 클릭하면 서버를 등록할 수 있는 화면으로 전환됩니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_01.png"/>
<br>
[그림 1] 서버 등록
</center>
<br>
<br>

아직 서버에 에이전트를 설치하지 않았기 때문에 선택할 수 있는 서버가 없습니다. 에이전트를 먼저 설치하고 화면에 출력된 `Agent 등록 시 입력할 도메인`을 입력하여 활성화해야 합니다.


### 에이전트 설치
[TOAST의 다운로드 페이지](http://docs.cloud.toast.com/ko/Download)에서 서버에 설치된 OS 종류에 따라 에이전트를 내려받아 설치합니다. 에이전트를 설치할 때 콘솔에서 확인한 도메인을 입력합니다.

* Linux

```
# curl http://tools.tcbackup.toastmaker.net/scripts/install.sh | bash -s /TCBackup_alpha/faL6GUt2nboWNI0a
```

* Windows

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_02.png"/>
<br>
[그림 2] Windows Agent 등록
</center>
<br>
<br>


### 서버 등록
서버 선택 항목 오른쪽의 `[새로 고침]` 버튼을 클릭하면 서버 선택 드롭다운 메뉴에서 에이전트가 등록된 서버의 호스트 이름을 확인할 수 있습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_03.png"/>
<br>
[그림 3] 서버 선택
</center>
<br>
<br>

서버와 OS 종류를 선택한 다음 하단의 `[+ 백업 경로 추가]` 버튼을 클릭해 백업할 경로를 추가합니다. 하나의 서버에 여러 개의 백업 경로를 추가할 수 있습니다. 백업 경로 추가는 서버 등록이 완료된 다음에도 가능합니다.

백업 경로를 추가할 때는 정확한 백업 경로를 입력해야 합니다. 경로를 잘못 입력하면 백업이 되지 않거나 원하지 않는 경로가 백업될 수 있습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_04.png"/>
<br>
[그림 4] 백업 경로 추가
</center>
<br>
<br>

백업 경로를 추가했으면 하단의 `[서버 등록]` 버튼을 클릭해 서버 등록을 완료합니다. 등록한 서버는 서버 목록에서 확인할 수 있습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_05.png"/>
<br>
[그림 5] 서버 목록
</center>
<br>
<br>

## 백업 경로 목록
서버 목록에서 서버 이름 왼쪽의 체크박스를 선택하면 화면 하단에 선택한 서버의 백업 경로 목록이 나타납니다. `[+ 백업 경로 추가]` 버튼을 클릭해 새로운 경로를 추가할 수 있습니다.
<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_06.png"/>
<br>
[그림 6] 백업 경로 목록
</center>
<br>
<br>


## 백업 결과 조회
백업 경로 목록에서 백업 경로를 클릭하면 백업 결과를 조회할 수 있습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_07.png"/>
<br>
[그림 7] 백업 결과 조회
</center>
<br>
<br>

백업 결과는 백업이 잘 되었다면 `성공`으로, 실패했다면 `실패`로 표시됩니다. 그리고 백업이 되었지만, 백업 도중 파일이 변경되었다면 `성공(주의)`로 표시됩니다.

## 백업 정책 변경

백업 경로 목록에서 각 항목 오른쪽에 있는 `[변경]` 버튼을 클릭하면 백업 정책 변경 대화창이 나타납니다. 변경할 수 있는 항목은 `백업 주기`, `백업 시각`, `보관 주기`입니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_08.png"/>
<br>
[그림 8] 백업 정책 변경
</center>
<br>
<br>

정책을 변경하고 `[백업 정책 변경]` 버튼을 클릭하면 변경한 내용이 반영됩니다.


## 복구 신청
등록한 백업 경로가 1회 이상 백업되었다면, 해당 데이터로 복구를 신청할 수 있습니다.

복구할 서버를 선택하면 화면 하단의 백업 경로 목록에서 `백업`/`복구` 탭을 선택할 수 있습니다. 복구 탭을 선택하면 `[+ 복구 신청]` 버튼과 선택한 서버에 대한 과거 복구 요청 목록이 나타납니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_09.png"/>
<br>
[그림 9] 복구 신청 목록
</center>
<br>
<br>

`[+ 복구 신청]` 버튼을 클릭하면 복구 신청 대화창이 표시됩니다. 등록한 백업 경로 중 복구를 원하는 경로를 선택할 수 있고, 경로를 선택하면 백업 일자를 선택할 수 있습니다. 한 번도 백업되지 않았거나, 모두 실패하여 복구할 수 있는 백업 데이터가 없다면 복구할 데이터가 없다는 메시지가 표시됩니다.

복구할 경로와 일자를 선택하고, 요청 사항, 이름, 휴대전화, Email 주소를 입력한 다음 `개인정보 수집 및 이용`에 동의해야 복구 신청을 할 수 있습니다. 동의하지 않으면 `신청` 버튼이 활성화되지 않습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_10.png"/>
<br>
[그림 10] 복구 신청
</center>
<br>
<br>

`[신청]` 버튼을 클릭하면 운영자에게 신청 정보가 전달되고 복구 신청 상태를 목록에서 확인할 수 있습니다. 복구 신청을 하면 진행상태가 `접수`로 표시됩니다. 운영자가 처리를 시작하면 `진행 중`으로 변경되며, 처리가 완료되면 `완료`로 표시됩니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_11.png"/>
<br>
[그림 11] 복구 신청 목록
</center>
<br>
<br>


## 백업 경로 삭제

백업 경로 목록에서 각 항목의 왼쪽 체크박스를 선택하면 `[백업 경로 삭제]` 버튼이 활성화됩니다. 활성화된 버튼을 클릭해 선택한 경로를 삭제할 수 있습니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_12.png"/>
<br>
[그림 12] 백업 경로 삭제
</center>
<br>
<br>


## 서버 삭제

서버 목록에서 각 항목의 왼쪽 체크박스를 선택하면 `[서버 삭제]` 버튼이 활성화 됩니다. 활성화된 버튼을 클릭해 서버를 삭제할 수 있습니다. 서버를 삭제하기 전에 반드시 등록한 백업 경로를 삭제해야 합니다. 등록된 백업 경로가 있다면 안내 메시지가 나타나고 삭제가 중단됩니다.

<br>
<center>
<img src="http://static.toastoven.net/prod_backup/console_guide/console_guide_13.png"/>
<br>
[그림 13] 서버 삭제
</center>
<br>
<br>

콘솔에서 서버를 삭제한 후에는 반드시 에이전트를 정지시키고 등록을 해지해야 합니다. 그렇지 않으면 해당 서버를 다시 등록할 수 없습니다. 반드시 다음 명령을 이용하여 에이전트를 정지하고 등록 해지하십시오.

* Linux

```
# curl http://tools.tcbackup.toastmaker.net/scripts/uninstall.sh | bash

```

* Windows

```
c:> uninstall.sh
```
