# 📘 TOPCIT MasterBook 2026

# Day 02 - 운영체제 · Process · Thread · Scheduling · Synchronization · Deadlock

> 난이도 : ⭐⭐⭐☆☆\
> TOPCIT 출제빈도 : ⭐⭐⭐⭐⭐\
> 실무 중요도 : ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   운영체제의 역할을 설명할 수 있다.
-   Process와 Thread의 차이를 이해한다.
-   Context Switching 원리를 설명할 수 있다.
-   CPU Scheduling 알고리즘을 비교할 수 있다.
-   Deadlock과 Synchronization을 실무 관점에서 설명할 수 있다.

------------------------------------------------------------------------

# 1. 운영체제(OS)

운영체제는 **하드웨어와 응용프로그램 사이에서 자원을 효율적으로 관리하는
소프트웨어**이다.

주요 기능

-   프로세스 관리
-   메모리 관리
-   파일시스템 관리
-   입출력 관리
-   보안 관리

``` text
Application
     │
Operating System
     │
CPU / Memory / Disk / Network
```

------------------------------------------------------------------------

# 2. Process와 Thread

## Process

실행 중인 프로그램을 의미한다.

특징

-   독립된 메모리 공간
-   PCB(Process Control Block) 보유
-   프로세스 간 통신(IPC) 필요

## Thread

프로세스 내부의 실행 단위이다.

특징

-   Code/Data/Heap 공유
-   Stack은 개별 보유
-   생성 비용이 Process보다 낮음

  항목                Process   Thread
  ------------------- --------- --------
  메모리              독립      공유
  생성비용            큼        작음
  Context Switching   느림      빠름

------------------------------------------------------------------------

# 3. Context Switching

CPU가 다른 Process 또는 Thread로 전환되는 과정이다.

``` text
Running
   │
Save Context
   │
Scheduler
   │
Load Context
   │
Running
```

### PM Note

Context Switching이 과도하면 CPU 사용률은 높지만 실제 업무 처리량은
감소할 수 있다.

------------------------------------------------------------------------

# 4. CPU Scheduling

## FCFS

먼저 도착한 작업부터 수행

장점 - 구현 단순

단점 - Convoy Effect 발생

## SJF

실행 시간이 짧은 작업 우선

장점 - 평균 대기시간 최소

단점 - 실행시간 예측 어려움

## Round Robin

Time Quantum 기반 순환 수행

장점 - 응답성 우수

단점 - Quantum이 너무 작으면 Context Switching 증가

## Priority

우선순위 기반

단점 - Starvation 가능

------------------------------------------------------------------------

# 5. Synchronization

동시에 공유 자원 접근 시 데이터 일관성을 유지하기 위한 기법이다.

## Mutex

동시에 한 개 Thread만 접근

## Semaphore

여러 Thread 접근 제어 가능

  항목      Mutex   Semaphore
  --------- ------- -----------
  접근 수   1       N
  소유권    있음    없음

------------------------------------------------------------------------

# 6. Deadlock

Deadlock은 서로 자원을 기다리며 영원히 진행되지 않는 상태이다.

필요 조건

1.  Mutual Exclusion
2.  Hold and Wait
3.  No Preemption
4.  Circular Wait

해결 방법

-   예방
-   회피
-   탐지
-   복구

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   Process vs Thread
-   PCB
-   Context Switching
-   FCFS / SJF / RR
-   Mutex / Semaphore
-   Deadlock 4조건

------------------------------------------------------------------------

# 예상 문제

## 문제 1

Process와 Thread의 가장 큰 차이는?

1.  Thread는 메모리를 공유한다.
2.  Process는 Stack을 공유한다.
3.  Thread는 PCB가 없다.
4.  Process는 CPU를 사용하지 않는다.

**정답:** 1

### 상세 해설

Thread는 같은 Process 내부에서 Code, Data, Heap을 공유한다. Stack만
독립적으로 가진다. Process는 독립적인 주소 공간을 가진다.

------------------------------------------------------------------------

## 문제 2

Round Robin Scheduling의 장점은?

1.  응답시간 향상
2.  메모리 증가
3.  Cache 증가
4.  RAID 성능 향상

**정답:** 1

### 상세 해설

Round Robin은 Time Quantum을 이용해 CPU를 순환 할당하므로 대화형
시스템의 응답성이 뛰어나다.

------------------------------------------------------------------------

## 문제 3

Deadlock 발생을 위한 조건이 아닌 것은?

1.  Mutual Exclusion
2.  Hold and Wait
3.  Circular Wait
4.  CPU Overclock

**정답:** 4

### 상세 해설

CPU Overclock은 Deadlock과 무관하다. Deadlock은 4가지 필요조건이 동시에
만족될 때 발생한다.

------------------------------------------------------------------------

# 기술면접

### Q. Process와 Thread의 차이를 설명해 보세요.

**모범답변**

Process는 독립적인 메모리 공간을 가진 실행 단위이고, Thread는 Process
내부에서 실행되는 작업 단위입니다. Thread는 Code, Data, Heap을
공유하므로 생성과 전환 비용이 낮아 성능상 유리합니다.

------------------------------------------------------------------------

# 암기노트

-   Process = 독립 메모리
-   Thread = 메모리 공유
-   RR = Time Quantum
-   Mutex = 1개
-   Semaphore = N개
-   Deadlock = 4가지 필요조건

------------------------------------------------------------------------

# Day 03 예고

-   Virtual Memory
-   Paging
-   Segmentation
-   Page Fault
-   TLB
-   Swap
