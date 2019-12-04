
# Bash Master 배쉬마스터
리눅스 배쉬 쉘에서 자주 사용되는 함수와 스크립트를 정리하고 있습니다.  
우분투에서 테스트를 했으며, 다른 계열 (레드햇 등) 에서는 안될 수도 있습니다.
```
$ <- 쉘 프롬프트를 뜻하며, 쉘에서 바로 실행할 수 있는 명령입니다.
# <- 쉘 프롬프트를 뜻하며, 루트 root 권한으로 실행한다는 의미입니다.
될 수 있으면 명확하게 적어두려고 합니다만, 둘을 혼용해서 사용하기도 합니다.
```

----

### Ch.01 시스템 관련 기본 명령어 [1장 예제 파일](https://github.com/bash-master/bash-master.github.io/tree/master/ch.01)
리눅스 시스템과 관련된 기본적인 명령어, 변수 안내입니다.

1. chmod : 파일 권한 변경.
1. chown : 파일 소유자 변경.
1. date : 날짜 관련 명령어. [상세보기](https://github.com/bash-master/bash-master.github.io/blob/master/ch.01/ch.01.data.sh)
```
$ date +%Y"-"%m"-"%d" "%H":"%M":"%S # 오늘날짜 
2019-11-22 13:29:42
$ date --date="1 days" +%Y"-"%m"-"%d" "%H":"%M":"%S # 1일뒤 (내일) 날짜
2019-11-23 13:29:42
$ date --date="-1 days" +%Y"-"%m"-"%d" "%H":"%M":"%S # 1일전 (어제) 날짜
2019-11-21 13:29:42
```
1. df : 파티션별 점유하고 있는 디스크 공간 확인.
```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
udev            488M     0  488M   0% /dev
tmpfs           100M   11M   89M  11% /run
/dev/xvda1      7.7G  5.9G  1.9G  76% /
/dev/xvdf        99G   76G   18G  82% /data
```
1. dmesg : 부팅되면서 체크하는 내용 확인하기. 부팅이후 중요 메시지도 이 명령어로 확인할 수 있다.
1. du : 디렉토리별 점유하고 있는 디스크 공간 확인.
```
$ du -sh # 현재 디렉토리 사용공간 확인.
216K    .
```
1. find : 파일 찾기.
1. free : 메모리 사용량 확인.
```
$ free -m # 옵션 m = MB 메가단위
              total        used        free      shared  buff/cache   available
Mem:            990         320          92          15         577         472
Swap:          2047         204        1843
```
1. hostname : 호스트명 확인.
1. id : 로그인 한 아이디 확인.
1. ifconfig : 네트워크 설정 보기.
1. lastlog : 마지막 시스템 로그 확인하기.
1. lsof : 열려 있는 파일 리스트 보기.
1. ls : 파일 리스트 보기.
1. mount / umount : 디스크 마운트 / 언마운트.
1. ps : 프로세스 상태 보기.
```
$ ps -axlf
F   UID   PID  PPID PRI  NI    VSZ   RSS WCHAN  STAT TTY        TIME COMMAND
1     0     2     0  20   0      0     0 kthrea S    ?          0:05 [kthreadd]
1     0     3     2   0 -20      0     0 rescue I<   ?          0:00  \_ [rcu_gp]
4     0   818     1  20   0   5688   444 poll_s Ss   ?          0:00 /usr/bin/vncserver-x11-serviced -fg
4     0   834   818  20   0  39716  5024 poll_s Sl   ?         18:48  \_ /usr/bin/vncserver-x11-core -service
4     0   819     1  20   0 130452  1736 epoll_ Ss   ?          6:04 php-fpm: master process (/etc/php/7.0/fpm/php-fpm.conf)
5    33   860   819  20   0 141256 12648 skb_wa S    ?          2:07  \_ php-fpm: pool www
5    33  2790   819  20   0 141236 10596 skb_wa S    ?          1:49  \_ php-fpm: pool www
5    33 26647   819  20   0 130968 10428 skb_wa S    ?          0:50  \_ php-fpm: pool www
4     0   828     1  20   0  37404  1924 poll_s Ssl  ?          0:00 /usr/sbin/lightdm
4     0   861   828  20   0 145828  4420 epoll_ Ssl+ tty7      54:18  \_ /usr/lib/xorg/Xorg :0 -seat seat0 -auth
4     0  1036   828  20   0  29604  1076 wait   Sl   ?          0:00  \_ lightdm --session-child 14 17
$ ps -elf
```
1. route : 라우트 경로 보기.
1. stty : 터미널 설정하기.
1. sudo : 실행권한 바꿔서 실행하기.
1. top : 프로세스 상태 보기. 빠져 나올땐 Ctrl+C
1. tty : 접속 터미널 확인하기.
1. uname : 리눅스 시스템 이름 확인하기.
```
$ uname
Linux
$ uname -a
Linux raspberrypi #1245 SMP Fri Jul 12 17:25:51 BST 2019 armv7l GNU/Linux
```
1. uptime : 시스템이 부팅된 날짜 확인하기.
1. useradd / userdel : 사용자 추가 / 사용자 삭제
1. w : 로그인한 유저 확인하기.
```
$ w
 11:16:55 up 51 days, 19:52,  2 users,  load average: 0.21, 0.23, 0.26
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
pi       tty7     :0               08Oct19 52days 54:18  18.84s /usr/bin/lxsession -s LXDE-pi -e LXDE
pi       pts/0    192.168.11.12    11:16    0.00s  0.67s  0.23s sshd: pi [priv] 
```
1. who : 로그인한 유저 확인하기 2.
```
$ who
pi       tty7         2019-10-08 15:26 (:0)
pi       pts/0        2019-11-29 11:16 (192.168.11.12)
```

----

### Ch.02 문자열, 텍스트 파일 관련 함수 [2장 예제 파일](https://github.com/bash-master/bash-master.github.io/tree/master/ch.02)

1. &gt; / &gt;&gt; : 입/출력 리다이렉션. 꺽쇠 한개 또는 두개.
```
$ echo "123" > test.txt # 출력 결과를 test.txt 파일로 보내기.
$ mysql -uroot -p testdb < test.sql # test.sql 파일 내용을 mysql 실행파일의 입력값으로 보내기.
```
1. awk : 문자열 자르기.
1. cat : 파일 내용 출력.
1. cut : 문자열 자르기.
1. grep : 원하는 문자열 찾기. 문자열 검색.
1. head : 파일의 맨 위에 있는 문자열 출력하기.
1. sed : 원하는 문자열을 찾아서 대체하기. 문자열 바꾸기.
1. tail : 파일의 맨 아래에 있는 문자열 출력하기.


### Ch.03 반복 및 분기 함수 [3장 예제 파일](https://github.com/bash-master/bash-master.github.io/tree/master/ch.03)
반복해서 작업해야 할때, 작업 대상마다 다르게 처리해야 할때 유용합니다.

1. 조건 : if then...else...
1. 반복 : for
1. 반복 : while
1. 분기 : case

----

### Ch.04 시스템 상태 확인 CLI 프로그램 [4장 예제 파일](https://github.com/bash-master/bash-master.github.io/tree/master/ch.04)

1. chkconfig : 
1. iostat : 
1. mpstat :
1. netstat : 
1. vmstat : 
1. strace : 
1. sysv-rc-conf : 
1. tcpdump : 

----

### Ch.05 많이 쓰는 쉘 커멘드라인 CLI 프로그램 [5장 예제 파일](https://github.com/bash-master/bash-master.github.io/tree/master/ch.05)
유용해서 자주 사용하는 쉘 커멘드라인 프로그램 안내입니다.

1. 웹 호출 : curl
1. MSSQL 접속 : tsql
1. MySQL 접속 : mysql

----

QnA : 묻고 답하기 : [다음카페 배쉬마스터](http://cafe.daum.net/bashmaster/qm9n)  
여기에 사용된 모든 예제 파일에 대한 권리는 본 사이트 관리자에게 있습니다.  
예제 파일 : 개인 용도 사용 가능, 상업적 사용 불가능.

