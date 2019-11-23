
# Bash Master 배쉬마스터
리눅스 배쉬 쉘에서 자주 사용되는 함수와 스크립트를 정리하고 있습니다.  
우분투에서 테스트를 했으며, 다른 계열 (레드햇 등) 에서는 안될 수도 있습니다.
```
$ <- 쉘 프롬프트를 뜻하며, 쉘에서 바로 실행할 수 있는 명령입니다.
# <- 쉘 프롬프트를 뜻하며, 루트 root 권한으로 실행한다는 의미입니다.
될 수 있으면 명확하게 적어두려고 합니다만, 둘을 혼용해서 사용하기도 합니다.
```

----

### Ch.01 시스템 관련 [1장 예제 파일](https://github.com/bash-master/bash-master.github.io/tree/master/ch.01)
리눅스 시스템과 관련된 명령어, 변수 안내입니다.

1. awk : 
1. cat : 
1. chmod : 파일 권한 변경
1. chown : 파일 소유권 변경
1. cut : 
1. date : 날짜 관련 [상세보기](https://github.com/bash-master/bash-master.github.io/blob/master/ch.01/ch.01.data.sh)
```
$ date +%Y"-"%m"-"%d" "%H":"%M":"%S # 오늘날짜 
2019-11-22 13:29:42
$ date --date="1 days" +%Y"-"%m"-"%d" "%H":"%M":"%S # 1일뒤 (내일) 날짜
2019-11-23 13:29:42
$ date --date="-1 days" +%Y"-"%m"-"%d" "%H":"%M":"%S # 1일전 (어제) 날짜
2019-11-21 13:29:42
```
1. df : 
1. dmesg : 
1. du : 
1. free : 
1. hostname : 
1. id : 
1. ifconfig : 
1. lastlog : 
1. lsof : 
1. mount / umount : 
1. ps : 
1. route : 
1. sed : 
1. stty : 
1. sudo : 
1. top : 
1. tty : 
1. uname : 
1. uptime : 
1. useradd / userdel : 사용자 추가 / 사용자 삭제
1. w : 
1. who : 




### Ch.02 기본 함수 [2장 예제 파일](https://github.com/bash-master/bash-master.github.io/tree/master/ch.02)

1. &gt; / &gt;&gt; : 출력 리다이렉션. 꺽쇠 한개 또는 두개.

### Ch.03 반복 및 분기 함수 [3장 예제 파일](https://github.com/bash-master/bash-master.github.io/tree/master/ch.03)
반복해서 작업해야 할때, 작업 대상마다 다르게 처리해야 할때 유용합니다.

1. 조건 : if then...else...
1. 반복 : for
1. 반복 : while
1. 분기 : case

### Ch.04 시스템 상태 확인 CLI 프로그램 [4장 예제 파일](https://github.com/bash-master/bash-master.github.io/tree/master/ch.04)

1. chkconfig : 
1. iostat : 
1. mpstat :
1. netstat : 
1. vmstat : 
1. strace : 
1. sysv-rc-conf : 
1. tcpdump : 


### Ch.05 많이 쓰는 쉘 커멘드라인 CLI 프로그램 [5장 예제 파일](https://github.com/bash-master/bash-master.github.io/tree/master/ch.05)
유용해서 자주 사용하는 쉘 커멘드라인 프로그램 안내입니다.

1. 웹 호출 : curl
1. MSSQL 접속 : tsql
1. MySQL 접속 : mysql

----

