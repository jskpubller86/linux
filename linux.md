# GNU(GNU is Not Unix) 프로젝트 

## GNU 프로젝트
- 1984년 리차드 스톨만(Richard Stallman)에 의해 시작
- 목표 : "모두가 공유할 수 있는 소프트웨어"를 만드는 것

## FSF(Free Software Foundation : 자유 소프트웨어 재단)
리차드 스톨먼이 1985년  GNU 프로젝트를 지원하기 위한 재단이다.

다음 아래 4가지 소프트웨어 자유에 대한 개념을 포함하고 있다. 

- 소프트웨어의 사용에 대한 자유
- 소프트웨어의 수정에 대한 자유
- 소프트웨어의 재배포에 대한 자유
- 수정된 소프트웨어의 이익을 전체가 얻을 수 있도록 배포할 수 있는 자유

ref ) 무료로 얻은 소프트웨어를  유상으로 판매할 수 있는 자유도 허용된다. 단 소스코드를 모두 개방해야 한다.



# 커널(kernel)

- 컴퓨터 운영체제의 핵심이 되는 컴퓨터 프로그램의 하나로, 시스템의 모든 것을 완전히 통제
- 운영체제의 다른 부분 및 응용 프로그램 수행에 필요한 여러 가지 서비스를 제공
- 리눅스 커널 아카이브 → <http://www.kernel.org>
- 커널 버전 
  - 안정 버전(stable version) : 이미 검증된 개발 안료 코드로 구성
  - 개발 버전(development version) :  
  - 4.6.4   =  주(major)버전 .부(minor) 버전.패치(patch)버전



# 리눅스 배포판

리눅스 커널에 다양한 응용프로그램을 추가해 쉽게 설치할 수 있도록 만든 것 

### 데비안(debian) 리눅스

- 1993년 이안 머독이 데비안 프로젝트를 창시
- 1996년 1.1버전을 시작으로 현재 9.9 버전까지 출시
- 패키지 설치 및 업그레이드가 단순하며, apt 프로그램을 이용해서 소프트웨어 설치나 업데이트 등이 자동으로 이루어짐

### 우분투(Ubuntu) 리눅스

- 데비안 리눅스를 기초로 유니티 데스크톱 환경을 사용하는 리눅스 배포판
- 최초 버전은 2004년 10월에 우분투 4.10 버전부터 시작
- 우분투 데스크톱과 우분투 서버 두 가지를 기본적으로 배포
  - 우분투 데스크톱 : x 윈도 환경을 지원하며 리브레오피스, 파이어폭스 웹 브라우저, 김프 이미지 편집기 등 다양한 GUI 툴을 제공
  - 우분투 서버 : x 윈도 환경을 지원하지 않으며, GUI 대신에 TUI(Text User Interface)를 제공
- Ubuntu flavours : 쿠분투(kubuntu), 우분투 그놈 (Ubuntu GNOME), 우분투 기린(Ubuntu Kylin), 루분투(Lubuntu) 등



# 가상콘솔 

가상 콘솔이란 '가상의 모니터'를 말한다. 우분투는 총 7개의 가상 콘솔을 제공한다.  즉, 한 개의 컴퓨터에 일곱개의 모니터가 연결된 효과를 낸다.

7번은 GUI 환경을 제공하고 1 ~ 6번은 테스트 모드 환경을 제공한다. 

각각의 콘솔로 이동하는 단축키는 ctrl + alt + F1 ~ F7 이다.



# 숨김파일

리눅스의 숨김 파일이라는 속성이 별도로 존재하지 않는다. 

숨기고 싶은 파일이나 디렉터리 이름 앞에 .(dot)를 붙인다. 

~~~
.hidden_folder
~~~



# 마운트 (mount)

마운트란 물리적인 장치를 논리적으로 사용하기 위한 기능이다.

GUI 환경에서는  자동으로 마운트를 하지만  CUI 환경에서는 관리자가 직접 마운트를 해줘야 한다. 

## 리눅스 기본 마운트 포인트 

<table>
    <thead>
        <tr>
            <th>
                마운트 포인트
            </th>
            <th>
                권장 크기
            </th>
             <th>
                비고
            </th>
        </tr>
    </thead>
	<tbody>
		<tr>
        	<td>/</td>
            <td>3GB</td>
            <td>루트 파티션</td>
        </tr>
        <tr>
        	<td>/boot</td>
            <td>1GB</td>
            <td>부팅 커널이 저장됨</td>
        </tr>
        <tr>
        	<td>/usr</td>
            <td>설치할 응용프로그램에 따라 크기 다름(주로 20GB 내외)</td>
            <td>응용 프로그램이 주로 저장됨</td>
        </tr>
        <tr>
        	<td>/tmp</td>
            <td>4GB</td>
            <td>임시 파일이 저장됨</td>
        </tr>
        <tr>
        	<td>/var</td>
            <td>10GB</td>
            <td>로그, 캐시 파일 등이 저장됨</td>
        </tr>
        <tr>
        	<td>/home</td>
            <td>사용자가 많을수록 많이 할당(나머지 용량)</td>
            <td>사용자별 공간</td>
        </tr>
        <tr>
        	<td>swap 파티션</td>
            <td>RAM의 2배 정도</td>
            <td>RAM 부족 시에 사용되는 공간</td>
        </tr>
	</tbody>
</table>

ref )   루트 파티션만 생성해서 마운트 해도  나머지 파티션은 자동으로 종속되어 생성된다.



# 파일 정보

<table>
    <tr>
    	<td>-</td>
        <td>rwxr--r--</td>
        <td>1</td>
        <td>root</td>
        <td>root</td>
        <td>0</td>
        <td>7월 15 16:11</td>
        <td>sample.txt</td>
    </tr>
</table>    
<table>
    <tr>
    	<th>-</th>
        <td>파일유형</td>
    </tr>
    <tr>
    	<th>rwxr--r--</th>
        <td>권한</td>
    </tr>
    <tr>
    	<th>1</th>
        <td>링크 수</td>
    </tr>
    <tr>
    	<th>root</th>
        <td>파일 소유자 이름</td>
    </tr>
    <tr>
    	<th>root</th>
        <td>파일 소유그룹 이름</td>
    </tr>
    <tr>
    	<th>0</th>
        <td>파일크기(Byte)</td>
    </tr>
    <tr>
    	<th>7월 15 16:11</th>
        <td>마지막 변경 날짜/시간</td>
    </tr>
    <tr>
    	<th>sample.txt</th>
        <td>파일이름</td>
    </tr>
</table>



## 파일의 유형

파일이 어떤 종류의 파일인지를 나타낸다. 

<table>
    <tr>
    	<th>d</th>
        <td>디렉터리</td>
    </tr>
    <tr>
    	<th>-</th>
        <td>파일</td>
    </tr>
    <tr>
    	<th>b</th>
        <td>블록 디바이스</td>
    </tr>
    <tr>
    	<th>c</th>
        <td>문자 디바이스</td>
    </tr>
    <tr>
    	<th>l</th>
        <td>링크</td>
    </tr>
</table>

## 파일 허가권

파일 허가권은 3개씩 끊어서 인식한다.

<table>
    <tr>
    	<td>rwx</td>
        <td>rwx</td>
        <td>rwx</td>
    </tr>
    <tr>
    	<td>사용자 권한</td>
        <td>그룹 권한</td>
        <td>게스트 권한</td>
    </tr>
</table>

- r : read
- w : write
- x : execute 



# 사용자와 그룹

- 리눅스는 다중 사용자 시스템(Multi-User system)

- root :  기본적으로 제공되는 계정으로 모든 작업에 대한 권한을 가진 수퍼유저(Superuser)

- 모든 사용자는 하나 이상의 그룹에 소속

- 계정 정보는 /etc/passwd 파일에 정의 

  ~~~
  user_nmae : password : user_id : group_id : description : home_dir : shell
  ~~~

  user_id 와 group_id가 0번이면 루트의 권한을 갖는다.

  일반 계정의 user_id는 1000부터 생성된다.

- /etc/passwd 파일에 패스워드가 "x"로 표시된 경우, 사용자의 비밀번호가 /etc/shadow 파일에 암호화되어 저장
- 그룹정보는 /etc/group 파일에 있다.
  - 사용자의 보조그룹은 볼 수 있다.

- 사용자 생성시 그룹을 지정하지 않으면 사용자 아이디로 새 그룹 아이디를 생성하여 적용한다.

### umask 






















