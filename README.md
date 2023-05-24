
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


```bash
# tail -f /var/log/syslog
. . . .
[1]+  Stopped                 tail -f /var/log/syslog

# tail -f /var/log/syslog &
[2] 464975
. . . .
