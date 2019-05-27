# 계정표시 

**터미널에서는 계정에 관한 정보를 아래와 같이 표시하여 준다. **

~~~
<사용자>@호스트 : 경로 표시 $ 또는 #

root@server-b : ~ #

ubuntu @호스트 :  ~$
~~~



# 도움말

명령어 도움말을 볼 수 있는 방법은 man, --help 옵션이 있다. 

### man

man 명령어는 섹션(Section)을 1 ~ 9까지 9개 페이지로 나눈다.  

>  1) 명령어
>
> 2 ~ 3) 프로그래밍
>
> 4) 디바이스
>
> 5) 파일 형식
>
> 6) 게임 
>
> 7) 기타주제
>
> 8)  시스템 관리
>
> 9) 커널

~~~
# man [섹션 번호] 명령어   → 섹션번호를 지정하지 않을 경우 위에서부터 순차적으로 검색한다.
~~~



# 자동완성 기능

파일명의 일부분 입력 후 [TAB] 키르 누르면 자동으로 파일 이름을 완성해 준다. 



# 히스토리

방향키 위 아래 ( ↑ ↓ ) 키로 입력했던 명령어들을 순차적으로 찾을 수 있다. 



# 시스템 명령어

## 종료

시스템 종료 명령어에는 poweroff, shutdown -P now, halt -p, init 0  옵션이 있다.  -P 또는 -p 옵션은 시스템 종료를 의미한다.  

### shutdown

~~~
# shutdown -P +10     → 10분 후에 종료 (P: pweroff)
# shutdown -r 22:00   → 오후 10시에 재부팅 (r: reboot)
# shutdown -c         → 예약된 shutdown을 취소(c: cancel)
# shutdown -k +15     → 현재 접속한 사용자에게 15분 후에 종료된다는 메시지를 보내지만 실제로 종료는 안 됨
~~~

## 시스템 재부팅

~~~
# reboot
# shutdown -r now
# init 6
~~~

## 로그아웃

사용자의 시스템 접속을 끝낸다.

~~~
# logout 
# exit
~~~

## 가상 콘솔 변경

리눅스에는 가상 콘솔이라 부르는 가상의 모니터 환경을 제공해주는데 chvt 명령어를 통해서 가상 콘솔을 전환할 수 있다. 

~~~
chvt 가상콘솔번호     → 해당 가상콘솔 번호로 전환된다.
~~~



# 기본명령어

### ls

List의 약자로 Windows의 dir 명령과 같은 역할을 한다.  해당 디렉터리에 있는 파일 및 디렉터리의 목록을 나열한다.

~~~
# ls                      → 현재 디렉터리의 파일 목록
# ls  /etc/systemd        → /etc/systemd 디렉터리의 목록
# ls -a                   → 현재 디렉터리의 목록(숨김 파일 포함)
# ls -l                   → 현재 디렉터리의 목록을 자세히 보여줌 (생성일자, 권한 정보 등)
# ls *.conf               → 확장자가 conf인 목록을 보여줌
# ls -l /etc/systemd/b**  → /etc/systemd 디렉터리에 있는 목록 중 앞 글자가 'b'인 것의 목록을 자세히 보여줌 
~~~

### cd

Change Directory의 약자로 디렉터리를 이동하는 명령이다.

~~~
# cd 
# cd ~                  → 현재 사용자의 홈 디렉터리로 이동 
# cd -사용자             → ubuntu 사용자의 홈 디렉터리로 이동
# cd .. , # cd ../      → 바로 상위의 디렉터리로 이동. '...'은 현 디렉터리의 부모 디렉터리를 의미(예를 들어, 현재 디렉터리가 /etc/systemd라면, 바로 상위인 /etc 디렉터리로 이동)
# cd /etc/systemd       → /etc/systemd 디렉터리로 이동(절대 경로)
# cd ../etc/systemd     → 상대 경로로 이동, 현재 디렉터리의 상위('...')로 이동한 후, 다시 /etc/systemd로 이동
# cd . 
# cd ./                 → 현재 디렉터리  
~~~

### pwd

Print Working Directory의 약자로 현재 디렉터리의 전체 경로를 화면에 보여준다.

~~~
# pwd                   → 현재 작업 중인 디렉터리의 경로 출력
~~~

### rm

ReMove의 약자로 파일이나 디렉터리를 삭제한다. 삭제할 때는 파일이나 디렉터리를 삭제할 권한이 있어야 한다.

root  사용자는 모든 권한이 있으므로 이 명령에 제약이 없다. 

리눅스는 휴지통 개념이 없으므로 삭제시 주의해야 한다.

~~~
# rm abc.txt         → 해당 파일을 삭제(내부적으로 'rm -f'로 연결됨)
# rm -i abc.txt      → 삭제 시 정말 삭제할 지 확인하는 메시지가 나옴
# rm -f abc.txt      → 삭제 시 확인하지 않고 바로 삭제함(f는 Force의 약자)
# rm -r abc          → abc 디렉터리와 그 아래에 있는 하위 디렉터리를 강제로 전부 삭제함. 
					   편리하지만 상당히 주의해서 사용해야 함(r은 Recursive의 약자)
~~~

### cp

copy의 약자로 파일이나 디렉터리를 복사한다. 새로 복사한 파일은 복사한 사용자의 소유가 된다. 
copy 명령을 실행할 때는 파일의 읽기 권한이 필요하다.

~~~
# cp aaa.txt bbb.txt      → abc.txt를 cba.txt라는 이름으로 바꿔서 복사
# cp -r aaa bbb           → 디렉터리 복사. abc 디렉터리를 cba 디렉터리로 복사
~~~

### touch

크기가 0인 새 파일을 생성하거나, 이미 파일이 존재한다면 파일의 최종 수정 시간을 변경한다.

~~~
# touch abc.txt           → 파일이 없을 경우엔 abc.txt라는 빈 파일을 생성하고, abc.txt가 있을 경우엔 파일의 최종 수정 시간을 현재 시각으로 변경  
~~~

### mv

move의 약자로 파일이나 디렉터리의 이름을 변경하거나, 다른 디렉터리로 옮길 때 사용한다.

~~~~
# mv abc.txt  /etc/systemd/       → abc.txt를  /etc/systemd/ 디렉터리로 이동
# mv aaa bbb ccc ddd              → aaa, bbb, ccc 파일을 '/ddd' 디렉터리로 이동
# mv abc.txt www.txt			  → abc.txt의 이름을 www.txt로 변경해서 이동
~~~~

### mkdir

make DIRectory의 약자로 새로운 디렉터리를 생성한다. 생성된 디렉터리는 명령을 실행한 사용자의 소유가 된다.

~~~
# mkdir abc            → 현재 디렉터리 아래에 '/abc'라는 디렉터리 생성
# mkdir-p /def/fgh     → /def/fgh 디렉터리를 생성하는데, 만약 '/fgh'의 부모 디렉터리인 '/def' 디렉터리가 없다면 자동 생성(p는 Parents의 약자)
~~~

### rmdir

ReMove DIRectory의 약자로 디렉터리를 삭제한다. 해당 디렉터리의 삭제 권한이 있어야 하며, 디렉터리는 비어 있어야 한다. 파일이 들어 있는 디렉터리를 삭제하려면 'rm -r'을 실행해야 한다.

~~~
# rmdir abc           → '/abc' 디렉터리를 삭제
~~~

### cat

concatenate의 약자로 파일의 내용을 화면에 보여준다. 여러 개 파일을 나열하면 파일을 연결해서 보여준다.

~~~
# cat a.txt b.txt        → a.txt와 b.txt를 연결해서 파일의 내용을 화면에 보여줌
~~~

### head

텍스트 형식으로 작성된 파일의 앞 10행만 화면에 출력한다. 

~~~  
# head /etc/systemd/bootchart.conf      → 해당 파일의 앞 10행을 화면에 출력
# head -3 /etc/systemd/bootchart.conf   → 앞 3행만 화면에 출력
~~~

### tail

텍스트 형식으로 작성된 파일의  마지막 10행만 화면에 출력한다.

~~~
# tail /etc/systemd/bootchart.conf      → 해당 파일의 마지막 10행을 화면에 출력
# tail -5 /etc/systemd/bootchart.conf   → 마지막 5행만 화면에 출력
~~~

### more

텍스트 형식으로 작성된 파일을 페이지 단위로 화면에 출력한다.  \<space bar\>를 누르면 다음 페이지로 이동하며, \<B\>를 누르면 앞 페이지로 이동한다. \<Q\>를 누르면 종료한다.

~~~
# more /etc/systemd/sytem.conf
# more +10 /etc/systemd/sytem.conf     →  10행부터 출력
~~~

### less

more  명령어와 용도가 비슷하지만 기능이 더 확장되어 있다.  more 명령에서 사용하는 키도 사용할 수 있으며, 추가로 화살표 키나 \<page up\>, \<page down\>도 사용할 수 있다.

~~~~
# less /etc/systemd/system.conf
# less +10 /etc/systemd/system.conf   →  10행부터 출력  
~~~~

### file

해당 파일이 어떤 종류의 파일인지를 표시해준다.

~~~~
# file /etc/systemd/system.conf      → system.conf는 텍스트 파일이므로 아스키 파일(ASCII)로 표시됨
# file /bin/gzip                     → gzip은 실행 파일이므로 'ELF 64-bit LSB executable' 파일로 표시됨
~~~~

### clear

현재 사용 중인 터미널 화면을 깨끗하게 지워준다.

~~~
# clear
~~~























