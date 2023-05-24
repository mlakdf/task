
<h1 align="center"> 🛠 Top 🛠 </h1>


# Top 명령어는 시스템 상태를 파악 할수있는 명령어   (CPU,Memory,Process)

* top (옵션 없이 사용하면 3초마다 화면을 갱신하며 정보를 보여줍니다)


* top 명령어의 옵션
* -b(batch 모드) : 순간의 정보를 알려줌
* -n(반복횟수) : 기본 3초 주기를 -n 옵션으로 바꿀수 있음

> top -b -n 1 예시 
<img width="300" height="230" align="left" alt="스크린샷 2018-07-18 20 25 32" src="https://github.com/mlakdf/task/assets/133843608/96956da6-336a-42a6-846b-4d679b0c9811">


> Task: 프로세스 개수 


> KiB Mem, Swap: 각 메모리의 사용량


> PR: 실행 우선순위


> VIRT, RES, SHR: 메모리 사용량 => 누수 check 가능


> S: 프로세스 상태(작업중, I/O 대기, 유휴 상태 등)


> load avrage: 시스템이 얼마나 일하는지 나타냄


top 실행 후 명령어

    shift + p : CPU 사용률 내림차순
    shit + m : 메모리 사용률 내림차순
    shift + t : 프로세스가 돌아가고 있는 시간 순
    k : kill. k 입력 후 PID 번호 작성. signal은 9
    f : sort field 선택 화면 -> q 누르면 RES순으로 정렬
    a : 메모리 사용량에 따라 정렬
    b : Batch 모드로 작동
    1 : CPU Core별로 사용량 보여줌
    
    
* top 나오실꺼면 q나 컨트롤+c누르시면 됩니다.(q는 잘 안먹는거같아요)

---

---
<h1 align="center"> 🛠 PS 🛠 </h1>

# PS는 (process status)의 줄인말로 현재 프로세스 목록과 상태를 파악 할수있는 명령어


* PS 명령어 
* ps (옵션 없이 쓰면 현재 사용자(shell)이 사용 중인 프로세스만 보여줌)


* ps 옵션 
* -e: 다른 사용자들이 구동시킨 모든 프로세스를 보여줌
* -f: 보다 상세하게 정보를 보여줌(Full)
* -l: -f보다 더 상세하게 보여줌(Long)


> ps -efl 명령어를 쓴 예시

![스크린샷, 2023-05-24 12-31-12](https://github.com/mlakdf/task/assets/133843608/f1e64bdd-9104-4bd6-8c48-13ee5eb8f14e)


> S:프로세스의 현재 상태


> UID:프로세스 실행시킨 사용자 ID


> PID:프로세스에 부여된 ID


> PPID:프로세스의 부모 프로세스


> C: CPU


> PRI: 프로세스 우선순위


> NI: CPU 사용 우선순위


> ADDR:프로레스 메모리 주소


> SZ: 가상메모리 사용량


> STIME: 프로세스 시작 시간


> TTY: 프로세스가 실행된 터미널의 종류와 번호


> TIME: 사용된 CPU시간


> CMD: 실행된 프로세스의 이름 혹은 실행된 명령














 ps와 top의 차이점

    ps는 ps한 시점에 proc에서 검색한 cpu 사용량
    top은 proc에서 일정 주기로 합산해 cpu 사용율 출력
    
* 그냥쓰고 싶은것
    * top -b 옵션이랑 ps랑 큰 차이가 없는거 같음
    * 사실상 상위 명령어가 top 인듯 함


---


---


<h1 align="center"> 🛠 Jobs 🛠 </h1>



# Jobs 명령어는 백그라운드로 실행중인 프로세스나 현재 중지된 프로세스를 보여줌
> jobs 명령어는 각 작업에 번호가 붙는데 나중에 kill 명령어 뒤에 '%번호'등으로 사용할 수 있다.


> ![스크린샷, 2023-05-24 15-26-52](https://github.com/mlakdf/task/assets/133843608/8415d8e4-49a8-4f4f-b94b-82e57e463590)



* jobs [옵션] [번호] 위에 사진은 jobs 명령어를 사용한거다.


**상태 설명**


> Running 작업이 계속 진행중임


> Done 작업이 완료되어 0을 반환


> Done(code) 작업이 완료되어 0이 아닌 코드를 반환


> Stopped 작업이 일시 중단


>>Stopped(SIGTSTP) SIGTSTP 시그널이 작업을 일시 중단


>>Stopped(SIGSTOP) SIGSTOP 시그널이 작업을 일시 중단


>>Stopped(SIGTTIN) SIGTTIN 시그널이 작업을 일시 중단


>>Stopped(SIGTTOU) SIGTTOU 시그널이 작업을 일시 중단  

---

* jobs 옵션 종류


* -l 프로세스 그룹 ID를 state 필드 앞에 출력

* -n  프로세스 그룹 중에 대표 프로세스 ID를 출력

* -p  각 프로세스 ID에 대해 한 행씩 출력

* command 지정한 명령어를 실행

---
---


<h1 align="center"> 🛠 Kill 🛠 </h1>


# Kill 프로세스를 지정해 제어하는 명령어
> 주로 프로세스를 종료하는 용도로 많이 사용
>> 2번째로 알아본 **PS명령어를 통해 pid를 얻고** kill 명령어의 인자로 넘기면 가능 


* ps -ef | grep node 를 쓴 사진


![123](https://github.com/mlakdf/task/assets/133843608/11951892-decb-43c4-97d4-c87ad9e2edf7)


* 첫번째 숫자가 pid 


* **kill 명령어를 알기전 시그널을 알아야함** 
    * 시그널은 **인터럽트**의 한 종류로 이벤트를 프로세스에 알려줌
    * 시그널 이벤트로는 HW 예외(나누기 0), SW 상태, 사용자 입력, 시스템 콜(kill)
    * kill -l 로 시그널을 확인해야함 (os마다 시그널이 다를수도 있음)
    * 시그널은 여러종류가 있고 각각 번호가 붙어 있습니다.


|시그널번호|시그널|설명|
|:---:|:---:|:---|
|1|SIGHUP(HUP)|종료(연결끊기,실행종료)|
|2|SIGINT(INT)|종료(CRTL+C,인터럽트)|
|3|SIGQUIT(QUIT)|종료+코어 덤프(CRTL+\)|
|9|SIGKILL(KILL)|종료(강제종료,프로그램에서 핸들러를 만들수 없는 시그널|
|15|SIGTERM(TERM)|종료 (정상종료)|
|18|SIGCONT(CONT)|정지 된 프로세스 재실행(STOP이나 TSTP에 의해 정지된 프로세스를 다시 실행|
|19|SIGSTOP(STOP)|정지(프로그램에서 핸들러를 만들수 없는 시그널|
|20|SIGTSTP(TSTP)|정지(CRTL+Z)|



* kill 명령어 설명
    * *kill -s [signal id] [pid]*
    * kill 은 기본적으로 -s  즉 시그널을 지정하지 않으면 15값을 디폴트로 사용한다(즉 정상종료를 시행함)
    * 예시로 kill 'pid' 위에서 알아낸 값을 적으면 정상종료 시킴
    * 시그널을 지정하는 명령어 예시로
    * kill -s 'SIGTERM' 'pid'
    * kill -s '15' 'pid'
    * 이렇게 3개의 명령어는 동일하게 볼 수있음 
    * tmi로 SIG를 뺴고 TERM만 적어도 정상 작동함
    





