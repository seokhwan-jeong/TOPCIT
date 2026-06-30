# 📘 TOPCIT MasterBook 2026

# Day 01 (Part 3)

## Pipeline · Branch Prediction · Multi-Core · Hyper-Threading · NUMA

> **난이도:** ⭐⭐⭐⭐☆
>
> **TOPCIT 출제 빈도:** ⭐⭐⭐⭐⭐
>
> **실무 중요도:** ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Pipeline의 원리를 이해한다.
-   Branch Prediction이 필요한 이유를 설명할 수 있다.
-   Multi-Core와 Hyper-Threading의 차이를 설명할 수 있다.
-   NUMA 구조와 실무 적용 사례를 이해한다.

------------------------------------------------------------------------

# 1. Pipeline

Pipeline은 하나의 명령어가 끝날 때까지 기다리지 않고 여러 명령어를
단계별로 동시에 처리하는 기술이다.

## Pipeline 단계

``` text
Instruction 1 : Fetch → Decode → Execute → Memory → WriteBack
Instruction 2 :        Fetch → Decode → Execute → Memory → WriteBack
Instruction 3 :               Fetch → Decode → Execute → Memory → WriteBack
```

### 장점

-   CPU 처리량(Throughput) 증가
-   동일한 클럭에서도 성능 향상

### 단점

Pipeline Hazard가 발생할 수 있다.

-   Data Hazard
-   Control Hazard
-   Structural Hazard

------------------------------------------------------------------------

# 2. Branch Prediction

if, switch 같은 분기 명령은 Pipeline을 멈출 수 있다.

CPU는 다음 실행될 명령을 **예측(Branch Prediction)** 하여 Pipeline이
멈추는 것을 최소화한다.

``` text
IF
 ├── TRUE  (예측)
 └── FALSE

예측 성공 → 성능 향상
예측 실패 → Pipeline Flush
```

### TOPCIT Point

-   Branch Prediction 실패 시 성능 저하
-   Pipeline Flush 발생

------------------------------------------------------------------------

# 3. Multi-Core

하나의 CPU 내부에 여러 개의 Core를 탑재한 구조이다.

``` text
CPU
 ├── Core 1
 ├── Core 2
 ├── Core 3
 └── Core 4
```

### 장점

-   병렬 처리
-   멀티태스킹 향상
-   서버 성능 향상

------------------------------------------------------------------------

# 4. Hyper-Threading

하나의 물리 Core를 두 개의 논리 Core처럼 사용하는 기술이다.

  항목             Multi-Core   Hyper-Threading
  ---------------- ------------ ------------------
  물리 Core 증가   O            X
  논리 Core 증가   O            O
  성능 향상        큼           상황에 따라 다름

### 실무

가상화 환경에서는 vCPU 수만 볼 것이 아니라 **실제 Physical Core 수**도
확인해야 한다.

------------------------------------------------------------------------

# 5. NUMA

NUMA(Non-Uniform Memory Access)는 CPU마다 가까운 메모리가 있는 구조이다.

``` text
CPU0 ---- Local Memory0

CPU1 ---- Local Memory1

원격 메모리 접근 시 지연 증가
```

### 실무 사례

-   VMware ESXi NUMA 설정
-   Kubernetes CPU Manager
-   Oracle DB 서버

NUMA를 고려하지 않으면 성능이 크게 저하될 수 있다.

------------------------------------------------------------------------

# PM Note

CPU 증설 요청이 들어오면 반드시 확인한다.

``` text
CPU 사용률
   ↓
Core 사용률
   ↓
Ready Time
   ↓
NUMA
   ↓
Memory
   ↓
Disk I/O
```

특히 VMware에서는 **CPU Ready Time**이 높으면 CPU 부족으로 판단할 수
있다.

------------------------------------------------------------------------

# 암기 노트

-   Pipeline = 처리량 향상
-   Branch Prediction = 분기 예측
-   Multi-Core = 물리 Core 증가
-   Hyper-Threading = 논리 Core 증가
-   NUMA = Local Memory가 가장 빠르다.

------------------------------------------------------------------------

# 예상 문제

## 문제 1

Pipeline의 목적으로 가장 적절한 것은?

1.  저장공간 증가
2.  처리량 증가
3.  메모리 용량 증가
4.  디스크 성능 향상

**정답:** 2

------------------------------------------------------------------------

## 문제 2

Branch Prediction 실패 시 발생하는 현상은?

1.  Cache Hit
2.  Pipeline Flush
3.  Page Fault
4.  Interrupt

**정답:** 2

------------------------------------------------------------------------

## 문제 3

NUMA에서 가장 빠른 메모리 접근은?

1.  원격 메모리
2.  Local Memory
3.  SSD
4.  Swap

**정답:** 2

------------------------------------------------------------------------

# 기술면접 예상 질문

### Q1. Multi-Core와 Hyper-Threading의 차이를 설명해 보세요.

**모범 답변**

Multi-Core는 실제 물리 코어를 늘려 병렬 처리 성능을 높이는 기술입니다.
Hyper-Threading은 하나의 물리 코어를 두 개의 논리 코어처럼 활용하여 자원
활용률을 높이는 기술입니다.

------------------------------------------------------------------------

# 다음 Part 예고

-   CPU 성능 분석(top, vmstat, mpstat, sar)
-   Kubernetes CPU Requests/Limits
-   VMware CPU Ready
-   AWS EC2 CPU Credit
-   Day1 종합 문제 및 최종 요약
