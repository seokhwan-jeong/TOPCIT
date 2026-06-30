# 📘 TOPCIT MasterBook 2026

# Day 01 (Part 5)

## 종합 문제 · OX 문제 · 기술면접 · 최종 암기노트

> **난이도:** ⭐⭐⭐⭐☆
>
> **TOPCIT 출제 빈도:** ⭐⭐⭐⭐⭐
>
> **실무 중요도:** ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# Part 5 학습 목표

Day 1에서 학습한 내용을 최종 정리하고 실전 문제를 통해 확인한다.

학습 범위

-   컴퓨터 시스템
-   CPU
-   Register
-   Cache
-   Pipeline
-   Multi-Core
-   NUMA
-   Kubernetes CPU
-   VMware CPU
-   AWS CPU

------------------------------------------------------------------------

# 1. Day 1 핵심 요약

## 반드시 암기

  항목                핵심 내용
  ------------------- --------------------------
  CPU                 ALU + CU + Register
  Register            CPU 내부 초고속 저장공간
  Cache               CPU와 RAM 속도 차이 해결
  Pipeline            처리량 증가
  Branch Prediction   분기 예측
  Multi-Core          물리 Core 증가
  Hyper-Threading     논리 Core 증가
  NUMA                Local Memory 우선
  Kubernetes          Requests / Limits
  VMware              CPU Ready
  AWS                 CPU Credit

------------------------------------------------------------------------

# 2. TOPCIT 종합 문제

## 문제 1

CPU 내부 저장장치 중 가장 빠른 것은?

1.  RAM
2.  Cache
3.  Register
4.  SSD

**정답:** 3

### 해설

Register는 CPU 내부에 위치하는 가장 빠른 저장공간이다.

속도 순서는 다음과 같다.

``` text
Register
 ↓
L1 Cache
 ↓
L2 Cache
 ↓
L3 Cache
 ↓
RAM
 ↓
SSD
```

------------------------------------------------------------------------

## 문제 2

Pipeline을 사용하는 가장 큰 목적은?

1.  메모리 증가

2.  처리량 증가

3.  저장공간 확보

4.  전력 절감

**정답:** 2

### 해설

Pipeline은 명령어를 동시에 여러 단계에서 처리하여 CPU의
처리량(Throughput)을 높이는 기술이다.

------------------------------------------------------------------------

## 문제 3

다음 중 CPU 병목 분석 순서로 가장 적절한 것은?

1.  CPU → 서버 교체

2.  CPU → Memory → Swap → Disk I/O → Network

3.  CPU → RAID

4.  CPU → DNS

**정답:** 2

### 해설

CPU 사용률은 결과일 뿐이다.

실제 원인을 찾기 위해서는 Memory, Swap, Disk I/O, Network, DB Lock 등을
함께 확인해야 한다.

------------------------------------------------------------------------

## 문제 4

VMware CPU Ready Time이 높다는 의미는?

1.  CPU 성능이 매우 좋다.

2.  VM이 CPU 할당을 기다리는 시간이 길다.

3.  Memory가 부족하다.

4.  SSD가 고장났다.

**정답:** 2

### 해설

CPU Ready Time은 Hypervisor에서 CPU를 할당받지 못하고 대기한 시간을
의미한다.

------------------------------------------------------------------------

## 문제 5

Kubernetes에서 CPU Limit이 너무 낮으면 발생 가능한 현상은?

1.  Cache Hit 증가

2.  CPU Throttling

3.  RAID 장애

4.  DNS Timeout

**정답:** 2

### 해설

CPU Limit을 초과하려고 하면 Linux CFS가 CPU 사용을 제한한다.

이를 CPU Throttling이라고 한다.

------------------------------------------------------------------------

# 3. OX 문제

  -----------------------------------------------------------------------
  문제                    정답                    해설
  ----------------------- ----------------------- -----------------------
  Register는 RAM보다      X                       Register가 가장 빠르다.
  느리다.                                         

  L1 Cache가 L3보다       O                       L1이 가장 빠르다.
  빠르다.                                         

  NUMA는 Local Memory     O                       원격 메모리보다 빠르다.
  접근이 가장 빠르다.                             

  CPU Ready는 VMware에서  O                       VM CPU 대기시간이다.
  사용하는 지표이다.                              

  AWS T 계열은 CPU        O                       Burstable 인스턴스
  Credit을 사용한다.                              특징이다.
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 4. 단답형 문제

### 문제 1

CPU 내부에서 가장 빠른 저장공간은?

**정답:** Register

------------------------------------------------------------------------

### 문제 2

CPU와 RAM 사이 속도 차이를 줄이는 메모리는?

**정답:** Cache Memory

------------------------------------------------------------------------

### 문제 3

CPU가 명령어를 실행하는 첫 번째 단계는?

**정답:** Fetch

------------------------------------------------------------------------

### 문제 4

VMware에서 VM CPU 대기시간을 나타내는 지표는?

**정답:** CPU Ready Time

------------------------------------------------------------------------

### 문제 5

AWS Burstable 인스턴스에서 성능을 결정하는 핵심 자원은?

**정답:** CPU Credit

------------------------------------------------------------------------

# 5. 기술면접 예상 질문

## Q1

CPU와 Core의 차이를 설명하세요.

### 모범답변

CPU는 하나의 프로세서를 의미하며, Core는 CPU 내부의 독립적인 연산
장치이다. 하나의 CPU에는 여러 개의 Core가 포함될 수 있다.

------------------------------------------------------------------------

## Q2

CPU 사용률이 100%라면 어떻게 분석하시겠습니까?

### 모범답변

CPU만 보지 않고 다음 순서로 확인한다.

``` text
CPU
 ↓
Memory
 ↓
Swap
 ↓
Disk I/O
 ↓
Network
 ↓
DB Lock
 ↓
Thread Pool
 ↓
Container
```

원인을 찾은 후 증설 여부를 판단한다.

------------------------------------------------------------------------

## Q3

CPU Ready Time이 높은데 VM 내부 CPU 사용률은 낮습니다. 이유는?

### 모범답변

VM 내부에서는 CPU를 거의 사용하지 않는 것처럼 보일 수 있지만, 실제로는
Hypervisor에서 CPU를 할당받지 못하고 대기하는 시간이 길기 때문이다.

------------------------------------------------------------------------

# 6. PM 체크리스트

CPU 장애 시 확인

-   [ ] CPU Usage
-   [ ] Load Average
-   [ ] Context Switching
-   [ ] Memory
-   [ ] Swap
-   [ ] Disk I/O
-   [ ] Thread Pool
-   [ ] DB Lock
-   [ ] Kubernetes Throttling
-   [ ] VMware CPU Ready
-   [ ] AWS CPU Credit

------------------------------------------------------------------------

# 7. Day 1 한 페이지 요약

``` text
컴퓨터
 │
CPU
 │
ALU
CU
Register
 │
Fetch
Decode
Execute
 │
Cache
 │
Pipeline
 │
Multi-Core
 │
NUMA
 │
Kubernetes
 │
VMware
 │
AWS
```

### 반드시 기억할 것

-   CPU = ALU + CU + Register
-   Register \> Cache \> RAM \> SSD
-   CPU 사용률은 원인이 아니라 결과일 수 있다.
-   Kubernetes는 CPU Requests/Limits를 반드시 확인한다.
-   VMware는 CPU Ready를 확인한다.
-   AWS T 계열은 CPU Credit을 확인한다.

------------------------------------------------------------------------

# Day 2 예고

다음 Day에서는 운영체제를 학습한다.

-   Process
-   Thread
-   Context Switching
-   Scheduling
-   Deadlock
-   Synchronization
-   Semaphore
-   Mutex
