# 작성자: 기영환 (학번: 20194572)
## top ('t'able 'o'f 'p'rocess)
<img src='https://github.com/GYHGwangju/2024-05-20-20194572_Assignment/blob/main/top_in_here.png?raw=true'>

top 명령어는 현재 OS의 상태를 나타내주는 CLI 어플리케이션으로, 메모리 사용량, CPU 사용량 등을 나타내주며 top를 실행하는 동안에는 주기적인 업데이트로 실시간에 근접한 내용을 보여준다.

`top - 13:30:54 up 1 min, 1 user, load average: 2.16, 0.62, 0.21`

top은 순서대로 "System time(현재 시간)", "System 구동 시간", "서버에 접속한 유저 수", "load average"를 보여준다. (load average는 각각 1분, 5분, 15분 당 부하 수치를 보여준다.)

`작 업 : 195 총계, 3 실행, 192 대기, 0 멈춤, 0 좀비`

task 탭에서는 total, running, sleeping, stopped, zombie 프로세스를 보여주는데, 왼쪽부터 각각 **모든 상태의 프로세스의 합계**, **정상적으로 실행하는 프로세스 수**, **리소스 대기 중인 프로세스 수**, **리소스를 종료하거나 해제하는 프로세스 수**, **부모 프로세스가 릴리스하길 기다리는 프로세스의 수** 를 나타낸다.

`Cpu: 44.4 us, 22.2 sy, 0.0 ni, 0.0 id, 0.0 wa, 0.0 hi, 33.3 si, 0.0 st`

Cpu 탭에서는 왼쪽부터 각각 **사용자 프로세스 실행에 소요된 시간의 백분율**, **커널 실행에 소요된 시간의 백분율**, **수동으로 구성된 nice 값으로 프로세스를 실행하는 데 소요된 시간의 백분율**, **유휴 시간의 백분율**, **대기 시간의 백분율**, **하드웨어 인터럽트를 관리하는 시간의 백분율**, **소프트웨어 인터럽트를 관리하는 데 걸리는 시간의 백분율**, **물리적 CPU에 대한 액세스를 대기하는 가상 CPU 시간의 백분율**을 나타낸다.

`MiB 메모리 : 3907.5 total, 1561.1 free, 953.2 used, 1393.2 buff/cache`

MiB 메모리는 왼쪽부터 **시스템이 가진 메모리의 사용률**, **설치된 총 메모리**, **사용 가능한 메모리**, **사용된 메모리**, **쓰기 위해 버퍼링되는 정보의 양**을 보여준다.

`MiB 스 왑: 2680.0 total, 2680.0 free, 0.0 used. 2683.8 avail 메모리`

Linux는 스토리지 디스크에서 스토리지 공간을 빌려 물리적 메모리 공간을 사용할 때 가상 메모리를 활용할 수 있는데, 물리적 RAM과 스토리지 드라이브 간에 데이터를 주고 받는 프로세스는 시간이 많이 걸리고 시스템 리소스를 사용하므로 가상 메모리 사용을 최소화 하거나, DB프로세스등 중요한 프로세스가 메모리 부족(OOM)으로 중지되지 않도록 권장하는 설정만큼 분배하는 것이 있다.

## ps ('p'rocess 's'tate) 
<img src='https://github.com/GYHGwangju/2024-05-20-20194572_Assignment/blob/main/ps_in_here.png?raw=true'>

ps 명령어는 현재 실행 중인 프로세스와 상태를 출력하는 명령어이다. 

man ps를 사용 시 ps 명령어와 관련된 매뉴얼을 볼 수 있는데, ps 명령어의 옵션은 각 시스템 계열 System V(-), BSD(- 사용 안 함), GNU(--)마다 다른 표기법 및 출력을 가지고 있다. 

## jobs
<img src='https://github.com/GYHGwangju/2024-05-20-20194572_Assignment/blob/main/jobs_in_here.png?raw=true'>

jobs 명령어는 백그라운드로 실행 중인 프로세스나 현재 중지된 프로세스의 목록을 출력해 주는 명령어이다.

- 첫 번째 열의 대괄호 안의 숫자는 잡 ID로 이 번호는 현재 셸에서 유효하다. 또한 그 다음에 있는 +는 bg나 fg 명령 실행시 기본 인자로 사용된다는 뜻이다. -는 +로 표시된 프로세스가 종료시 기본값으로 사용될 프로세스를 의미한다.
- Running: 두 번째 열은 프로세스의 상태를 나타내고, 현재는 Running으로 실행중인 상태를 의미한다.
- sleep 1000 &: 프로세스를 실행한 명령어.

## kill
<img src='https://github.com/GYHGwangju/2024-05-20-20194572_Assignment/blob/main/kill_in_here.png?raw=true'>

kill 명령어는 프로세스를 **죽일(kill) 때** 사용한다.


---
#### 출처

[top 명령어 출처](https://velog.io/@ljk0509/EC2-top-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0)

[ps 명령어 출처](https://blog.naver.com/tmk0429/222318530824)

[jobs 명령어 출처](https://www.lainyzine.com/ko/article/linux-jobs-command-usage/)

[kill 명령어 출처](https://121202.tistory.com/45)

----
##### 여담
<img src='https://i.imgur.com/cbHjY6c.jpg'>
