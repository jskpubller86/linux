# 가상머신이란

가상머신이란 가상의 컴퓨터로 존재하는 것이며 가상머신에 os를 설치 할 수 있다. 이 OS를 게스트 OS라 하고 원래 컴퓨터의 운영체제를 호스트 OS라 한다.

![Alt text](images/virtual_structure.png)



# 가상머신(docker) 설치

1)  vmware 다운로드 - [https://my.vmware.com/web/vmware/details?downloadGroup=WKST-1259-WIN&productId=524&rPId=20840#product_downloads]    12.1.1 버전을 설치한다. pro로 설치한다. pro를 설치하면 스냅숏 기능과 가상 네트워크 사용자 설정 기능을 사용할 수 있다. 
2)  vmware 키 다운로드 - <https://dd00oo.tistory.com/entry/VMWare-12-key>  해당 키 목록 중에 하나를 선택해서 등록한다.
3) 
4) 


# 64bit 및 가상화 기술 지원 여부 확인
http://www.grc.com/secureable.html   또는  http://cafe.naver.com/thisisLinux/  자료실에서 다운로드 할 수 있다. 



# 호스트 디렉터리 쉐어링 하기 

VMware Tool 에서는 가상머신 호스트 컴퓨터의 쉐어링 기능을 제공한다. 

1) VM > settings > options > shared folders 메뉴를 선택한다. 

2)  shared folders  옵션 중 Folder sharing에서 always enabled 를 선택한다. 

3) 다음 옵션인 Folders 옵션에서 add 버튼을 눌러 Add Shared Folder Wiard를 실행시킨 다음 Host path에는 공유할 호스트 폴더를 지정하고 

Name에는 게스트에서 고유된 호스트 폴더와 연결할 폴더의 이름을 지정한다.




