# 📘 TOPCIT MasterBook 2026

# Day 01 (Part 2)

## Register · Cache Memory · Cache Mapping

> **난이도:** ⭐⭐⭐☆☆\
> **TOPCIT 출제 빈도:** ⭐⭐⭐⭐⭐\
> **실무 중요도:** ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Register의 종류와 역할을 이해한다.
-   Cache Memory의 필요성을 설명할 수 있다.
-   L1/L2/L3 Cache의 차이를 이해한다.
-   Cache Mapping 방식을 비교할 수 있다.

------------------------------------------------------------------------

# 1. Register

Register는 CPU 내부에 존재하는 가장 빠른 저장공간이다.

  Register                    역할
  --------------------------- -------------------------
  PC (Program Counter)        다음 실행할 명령어 주소
  IR (Instruction Register)   현재 실행 중인 명령어
  SP (Stack Pointer)          스택 최상단 위치
  MAR                         메모리 주소 저장
  MDR                         메모리 데이터 저장

``` text
CPU
 ├── ALU
 ├── Control Unit
 └── Registers
      ├── PC
      ├── IR
      ├── SP
      ├── MAR
      └── MDR
```

### TOPCIT Point

-   Register는 RAM보다 훨씬 빠르다.
-   CPU 내부에 위치한다.

------------------------------------------------------------------------

# 2. Cache Memory

CPU와 RAM의 속도 차이를 줄이기 위해 사용하는 고속 메모리이다.

## Cache 계층

  계층   특징
  ------ ----------------------
  L1     가장 빠름, 가장 작음
  L2     속도와 용량의 균형
  L3     여러 Core가 공유

``` text
CPU
 │
L1 Cache
 │
L2 Cache
 │
L3 Cache
 │
RAM
 │
SSD
```

------------------------------------------------------------------------

# 3. Cache Hit & Miss

-   Cache Hit : 필요한 데이터가 Cache에 존재
-   Cache Miss : RAM까지 접근해야 함

공식

    Hit Rate ↑  → 성능 ↑
    Miss Rate ↑ → 성능 ↓

------------------------------------------------------------------------

# 4. Cache Mapping

## Direct Mapping

-   구현이 단순
-   충돌이 많다.

## Fully Associative

-   어느 위치에도 저장 가능
-   성능 우수
-   구현 비용 증가

## Set Associative

-   Direct와 Fully Associative의 절충안
-   실제 CPU에서 가장 많이 사용

  방식                속도        구현
  ------------------- ----------- --------
  Direct              빠름        쉬움
  Fully Associative   가장 좋음   어려움
  Set Associative     우수        보통

------------------------------------------------------------------------

# PM Note

CPU 사용률이 높지 않은데 응답속도가 느리다면 Cache Miss 증가나 Memory
병목도 의심해야 한다.

가상화 환경에서는 NUMA 설정과 CPU Pinning도 함께 확인한다.

------------------------------------------------------------------------

# 암기 노트

-   Register \> Cache \> RAM \> SSD (속도 순)
-   L1 \> L2 \> L3 (속도 순)
-   Set Associative가 가장 많이 사용

------------------------------------------------------------------------

# 예상 문제

### 문제 1

다음 중 가장 빠른 저장장치는?

1.  SSD
2.  RAM
3.  L3 Cache
4.  Register

**정답:** 4

### 문제 2

CPU와 RAM 사이의 속도 차이를 줄이기 위한 장치는?

1.  SSD
2.  Cache Memory
3.  GPU
4.  NIC

**정답:** 2

### 문제 3

실제 CPU에서 가장 많이 사용하는 Cache Mapping 방식은?

1.  Direct
2.  Fully Associative
3.  Set Associative
4.  Random

**정답:** 3

------------------------------------------------------------------------

# 다음 Part 예고

-   Pipeline
-   Branch Prediction
-   Multi-Core
-   Hyper-Threading
-   NUMA
-   CPU 성능 분석
