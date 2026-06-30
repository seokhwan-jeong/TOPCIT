# 📘 TOPCIT MasterBook 2026

# Day 01 (Part 4)

## CPU 성능 분석 · Kubernetes CPU · VMware CPU · AWS CPU

> **난이도:** ⭐⭐⭐⭐☆\
> **TOPCIT 출제 빈도:** ⭐⭐⭐⭐☆\
> **실무 중요도:** ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

이번 Part를 학습하면 다음 내용을 설명할 수 있습니다.

-   Linux/Windows에서 CPU 성능을 분석하는 기본 방법
-   CPU 사용률과 Load Average의 차이
-   Kubernetes CPU Requests / Limits / Throttling
-   VMware vCPU / pCPU / CPU Ready Time
-   AWS EC2 CPU Credit 개념
-   CPU 100% 장애 상황에서 인프라 PM이 확인해야 할 항목

------------------------------------------------------------------------

# 1. CPU 성능 분석의 기본 관점

CPU 성능 문제를 볼 때 가장 흔한 실수는 **CPU 사용률만 보는 것**이다.

CPU 사용률이 높다는 것은 증상일 뿐이며, 원인은 다양하다.

``` text
CPU 99%
  ├── 실제 연산량 증가
  ├── 애플리케이션 무한 루프
  ├── Thread Pool 과다 사용
  ├── Memory 부족으로 인한 Swap
  ├── Disk I/O Wait
  ├── DB Lock 대기
  └── Container CPU Limit에 의한 Throttling
```

즉, CPU 사용률이 높다고 해서 곧바로 CPU 증설을 판단하면 안 된다.

------------------------------------------------------------------------

# 2. Linux CPU 분석 명령어

## 2.1 top

`top`은 Linux에서 가장 많이 사용하는 실시간 성능 확인 명령어이다.

``` bash
top
```

주요 확인 항목

  항목           의미
  -------------- ------------------------
  %us            User 영역 CPU 사용률
  %sy            Kernel 영역 CPU 사용률
  %id            Idle
  %wa            I/O Wait
  load average   실행 대기 중인 작업량
  RES            실제 메모리 사용량
  VIRT           가상 메모리 사용량

------------------------------------------------------------------------

## 2.2 vmstat

``` bash
vmstat 1
```

주요 항목

  항목   의미
  ------ -----------------------
  r      실행 대기 프로세스 수
  b      I/O 대기 프로세스 수
  swpd   Swap 사용량
  si     Swap In
  so     Swap Out
  us     User CPU
  sy     System CPU
  wa     I/O Wait

### 실무 해석

`wa` 값이 높으면 CPU가 바쁜 것이 아니라 **디스크 I/O를 기다리는 상태**일
수 있다.

``` text
CPU 사용률 높음
   ↓
wa 높음
   ↓
Disk I/O 병목 가능성
   ↓
iostat 확인
```

------------------------------------------------------------------------

## 2.3 mpstat

``` bash
mpstat -P ALL 1
```

CPU Core별 사용률을 확인할 수 있다.

예를 들어 16 Core 서버에서 특정 Core만 100%라면 애플리케이션이 병렬
처리를 제대로 하지 못하고 있을 가능성이 있다.

------------------------------------------------------------------------

## 2.4 sar

``` bash
sar -u 1
```

CPU 사용률을 시간대별로 확인할 수 있다.

장애 분석에서는 "현재 상태"보다 **장애 발생 시점의 추세**가 더 중요하다.

------------------------------------------------------------------------

## 2.5 iostat

``` bash
iostat -x 1
```

CPU 문제처럼 보이지만 실제로는 Disk I/O 문제일 수 있다.

  항목    의미
  ------- --------------------
  await   I/O 응답 대기 시간
  util    디스크 사용률
  r/s     초당 읽기
  w/s     초당 쓰기

------------------------------------------------------------------------

# 3. Windows CPU 분석

Windows 서버에서는 다음 도구를 사용한다.

-   Task Manager
-   Resource Monitor
-   Performance Monitor(PerfMon)

확인 항목

  항목                     의미
  ------------------------ --------------------
  Processor Time           CPU 사용률
  Processor Queue Length   CPU 대기열
  Context Switches/sec     문맥교환 빈도
  Disk Queue Length        디스크 대기열
  Available Memory         사용 가능한 메모리

------------------------------------------------------------------------

# 4. Kubernetes CPU 관리

Kubernetes에서는 CPU를 일반적인 서버와 다르게 봐야 한다.

## 4.1 CPU Requests

Pod가 최소한 확보받기를 원하는 CPU 양이다.

``` yaml
resources:
  requests:
    cpu: "500m"
```

`500m`은 0.5 Core를 의미한다.

## 4.2 CPU Limits

Pod가 사용할 수 있는 최대 CPU 양이다.

``` yaml
resources:
  limits:
    cpu: "1"
```

`1`은 1 Core를 의미한다.

------------------------------------------------------------------------

## 4.3 CPU Throttling

CPU Limit이 설정된 컨테이너가 제한보다 더 많은 CPU를 사용하려고 할 때
발생한다.

``` text
Pod가 더 많은 CPU 필요
   ↓
CPU Limit 도달
   ↓
CFS Quota에 의해 제한
   ↓
응답 지연 발생
```

### 실무 사례

CPU 사용률은 낮아 보이는데 애플리케이션 응답이 느린 경우가 있다.

이때 원인이 CPU Throttling일 수 있다.

확인 항목

-   Pod CPU Usage
-   CPU Limit
-   Throttling Metrics
-   Application Latency
-   HPA 설정

------------------------------------------------------------------------

# 5. VMware CPU 관리

가상화 환경에서는 CPU를 다음과 같이 구분한다.

  용어         의미
  ------------ ------------------------------------
  pCPU         물리 CPU Core
  vCPU         VM에 할당한 가상 CPU
  CPU Ready    VM이 CPU를 쓰고 싶지만 대기한 시간
  Overcommit   물리 CPU보다 많은 vCPU를 할당

## CPU Ready Time

CPU Ready Time이 높으면 VM이 CPU를 할당받지 못해 대기 중이라는 뜻이다.

``` text
VM 응답 지연
   ↓
VM 내부 CPU 사용률은 낮음
   ↓
ESXi CPU Ready 높음
   ↓
물리 CPU 경합 가능성
```

------------------------------------------------------------------------

# 6. AWS EC2 CPU Credit

AWS T 계열 인스턴스는 CPU Credit 기반으로 동작한다.

  상태                 의미
  -------------------- ---------------
  Credit 충분          Burst 가능
  Credit 부족          CPU 성능 제한
  CPU Credit Balance   남은 Credit
  CPU Credit Usage     사용한 Credit

### 실무 사례

개발 서버에서 T3 인스턴스를 사용하다가 CPU Credit이 고갈되면 갑자기
성능이 저하될 수 있다.

------------------------------------------------------------------------

# 7. CPU 100% 장애 분석 절차

인프라 PM은 다음 순서로 장애를 분류한다.

``` text
1. 전체 CPU 사용률 확인
2. 프로세스별 CPU 사용률 확인
3. Core별 사용률 확인
4. Load Average 확인
5. Memory / Swap 확인
6. Disk I/O Wait 확인
7. Thread Pool 확인
8. DB Lock 확인
9. Kubernetes Limit / Throttling 확인
10. VMware CPU Ready 확인
```

------------------------------------------------------------------------

# 8. PM Note

CPU 증설은 마지막 선택지이다.

먼저 해야 할 질문은 다음과 같다.

-   어떤 프로세스가 CPU를 사용하는가?
-   특정 시간대에만 발생하는가?
-   Memory 부족으로 Swap이 발생했는가?
-   Disk I/O Wait가 높은가?
-   DB Lock으로 애플리케이션이 대기 중인가?
-   Kubernetes CPU Limit이 너무 낮은가?
-   VMware CPU Ready가 높은가?
-   AWS T 계열 인스턴스의 CPU Credit이 부족한가?

------------------------------------------------------------------------

# 9. TA Note

TA는 단순히 "CPU 몇 Core가 필요합니다"라고 말하면 안 된다.

업무 특성에 따라 CPU 설계 기준이 달라진다.

  업무 유형    CPU 설계 관점
  ------------ -----------------------------
  Web/WAS      동시 접속, Thread Pool
  DB           CPU + Memory + Disk I/O
  AI 추론      GPU 우선, CPU는 보조
  배치         Peak 시간대 처리량
  Kubernetes   Requests/Limits/HPA
  VMware       vCPU:pCPU Ratio, Ready Time

------------------------------------------------------------------------

# 10. TOPCIT 출제 포인트

⭐⭐⭐⭐⭐

반드시 이해해야 할 개념

-   CPU 사용률과 병목의 차이
-   Context Switching
-   Load Average
-   I/O Wait
-   CPU Throttling
-   vCPU와 pCPU
-   CPU Overcommit
-   CPU Credit

------------------------------------------------------------------------

# 11. 예상 문제 + 상세 해설

## 문제 1

Linux에서 CPU 사용률은 높지 않은데 응답속도가 느리다. `top`에서 `%wa`
값이 높게 나타났다. 가장 의심해야 할 원인은?

1.  CPU Core 부족
2.  Disk I/O 병목
3.  DNS 장애
4.  Cache Hit 증가

**정답:** 2. Disk I/O 병목

### 상세 해설

`%wa`는 CPU가 디스크 I/O 완료를 기다리는 시간을 의미한다.\
즉 CPU가 실제 연산을 수행하는 것이 아니라, 디스크 읽기/쓰기 작업이
끝나기를 기다리는 상태이다.

따라서 응답 지연의 원인은 CPU 부족보다 **Storage 또는 Disk I/O 병목**일
가능성이 높다.

-   ① CPU Core 부족: CPU 연산 사용률이 높은 경우 의심한다.
-   ③ DNS 장애: 이름 해석 실패와 관련된다.
-   ④ Cache Hit 증가: 일반적으로 성능 향상 요인이다.

------------------------------------------------------------------------

## 문제 2

Kubernetes에서 CPU Limit이 낮게 설정된 Pod가 순간적으로 많은 CPU를
필요로 할 때 발생할 수 있는 현상은?

1.  CPU Throttling
2.  Page Fault
3.  DNS Cache
4.  RAID Rebuild

**정답:** 1. CPU Throttling

### 상세 해설

Kubernetes에서 CPU Limit은 컨테이너가 사용할 수 있는 최대 CPU 양이다.\
컨테이너가 Limit 이상 CPU를 사용하려 하면 Linux CFS Quota에 의해 CPU
사용이 제한된다.\
이 현상을 CPU Throttling이라고 한다.

CPU Throttling이 발생하면 CPU 사용률이 낮아 보이더라도 애플리케이션 응답
시간이 길어질 수 있다.

-   ② Page Fault: 필요한 메모리 페이지가 RAM에 없을 때 발생한다.
-   ③ DNS Cache: 이름 해석 캐시이다.
-   ④ RAID Rebuild: 스토리지 복구 작업이다.

------------------------------------------------------------------------

## 문제 3

VMware 환경에서 VM 내부 CPU 사용률은 낮지만 서비스 응답이 느리고,
ESXi에서 CPU Ready Time이 높다. 가장 적절한 해석은?

1.  VM이 CPU를 충분히 할당받지 못하고 대기 중이다.
2.  VM 내부에서 DNS 장애가 발생했다.
3.  Disk 용량이 부족하다.
4.  Cache Hit가 높다.

**정답:** 1. VM이 CPU를 충분히 할당받지 못하고 대기 중이다.

### 상세 해설

CPU Ready Time은 VM이 CPU를 사용하고 싶지만 물리 CPU 자원이 부족하거나
경합이 있어 대기한 시간을 의미한다.\
VM 내부에서 CPU 사용률이 낮게 보여도, 실제로는 Hypervisor 수준에서 CPU
할당을 기다리고 있을 수 있다.

따라서 가상화 환경에서는 VM 내부 지표뿐 아니라 ESXi Host의 Ready Time도
함께 확인해야 한다.

------------------------------------------------------------------------

## 문제 4

AWS T 계열 인스턴스에서 일정 시간 후 갑자기 성능이 저하되었다. 가장 먼저
확인할 지표는?

1.  CPU Credit Balance
2.  ARP Table
3.  RAID Level
4.  DNS TTL

**정답:** 1. CPU Credit Balance

### 상세 해설

AWS T 계열 인스턴스는 CPU Credit을 사용해 일정 시간 동안 Burst 성능을
제공한다.\
Credit이 고갈되면 CPU 사용이 제한되어 성능이 저하될 수 있다.

따라서 T3, T4g 같은 Burstable 인스턴스에서는 CPU Credit Balance와 CPU
Credit Usage를 확인해야 한다.

------------------------------------------------------------------------

## 문제 5

CPU 사용률이 100%일 때 인프라 PM의 가장 적절한 첫 대응은?

1.  즉시 CPU 증설
2.  서버 재부팅
3.  원인 프로세스와 병목 지표 확인
4.  방화벽 정책 변경

**정답:** 3. 원인 프로세스와 병목 지표 확인

### 상세 해설

CPU 사용률 100%는 증상이다.\
원인은 애플리케이션 버그, 트래픽 증가, Thread Pool, DB Lock, Disk I/O,
Swap 등 다양하다.

따라서 즉시 증설하거나 재부팅하기보다 다음을 확인해야 한다.

``` text
프로세스별 CPU
Memory
Swap
Disk I/O
Network
DB Lock
Thread Pool
Container Limit
```

------------------------------------------------------------------------

# 12. 실무 체크리스트

CPU 장애 발생 시 확인 항목

-   [ ] CPU 전체 사용률
-   [ ] Core별 사용률
-   [ ] 프로세스별 CPU 사용률
-   [ ] Load Average
-   [ ] Context Switching
-   [ ] Memory 사용률
-   [ ] Swap 사용량
-   [ ] Disk I/O Wait
-   [ ] Network 사용률
-   [ ] DB Lock
-   [ ] WAS Thread Pool
-   [ ] Kubernetes CPU Limit
-   [ ] Kubernetes Throttling
-   [ ] VMware CPU Ready
-   [ ] AWS CPU Credit

------------------------------------------------------------------------

# 다음 Part 예고

Day 01 Part 5에서는 다음 내용을 다룬다.

-   Day 1 전체 종합 문제
-   OX 문제
-   단답형 문제
-   기술면접 예상 질문
-   최종 암기노트
-   Day 1 한 페이지 요약
