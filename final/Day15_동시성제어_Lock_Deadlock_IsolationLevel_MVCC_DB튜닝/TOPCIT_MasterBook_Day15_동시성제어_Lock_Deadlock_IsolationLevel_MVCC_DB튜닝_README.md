# 📘 TOPCIT MasterBook 2026

# Day 15 - 동시성 제어 · Lock · Deadlock · Isolation Level · MVCC · DB 성능 튜닝

> **난이도** ⭐⭐⭐⭐⭐\
> **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐\
> **실무 중요도** ⭐⭐⭐⭐⭐\
> **예상 학습시간** 120분

------------------------------------------------------------------------

# 학습 목표

-   동시성 제어의 필요성을 이해한다.
-   Lock과 Deadlock의 차이를 설명할 수 있다.
-   Isolation Level의 특징을 비교할 수 있다.
-   MVCC의 동작 원리를 이해한다.
-   DB 성능 튜닝 기본 절차를 설명할 수 있다.

------------------------------------------------------------------------

# 1. 동시성 제어(Concurrency Control)

여러 사용자가 동시에 데이터를 접근해도 데이터의 일관성을 유지하는
기술이다.

동시성 제어가 없으면 다음과 같은 문제가 발생한다.

-   Lost Update
-   Dirty Read
-   Non-Repeatable Read
-   Phantom Read

``` text
User A ─┐
         ├── Database
User B ─┘
```

------------------------------------------------------------------------

# 2. Lock

Lock은 여러 트랜잭션이 동일 데이터를 동시에 수정하지 못하도록 보호하는
메커니즘이다.

  Lock                설명
  ------------------- ----------------
  Shared Lock(S)      읽기 가능
  Exclusive Lock(X)   읽기/쓰기 독점

### Lock 동작 예

``` text
TX1
 UPDATE emp
      │
 Exclusive Lock
      │
TX2 대기
```

------------------------------------------------------------------------

# 3. Deadlock

두 개 이상의 트랜잭션이 서로의 Lock 해제를 기다리는 상태이다.

``` text
TX1 → Lock A → Lock B 대기
TX2 → Lock B → Lock A 대기
```

### 발생 조건

1.  Mutual Exclusion
2.  Hold and Wait
3.  No Preemption
4.  Circular Wait

### 해결 방법

-   Lock 순서 통일
-   Timeout
-   Deadlock Detection
-   Rollback

------------------------------------------------------------------------

# 4. Isolation Level

  Level               Dirty   Non-Repeatable    Phantom
  ------------------ ------- ---------------- -----------
  Read Uncommitted    발생         발생          발생
  Read Committed      방지         발생          발생
  Repeatable Read     방지         방지        발생 가능
  Serializable        방지         방지          방지

### 실무 팁

-   Oracle : Read Committed 기본
-   PostgreSQL : Read Committed 기본(MVCC)
-   MySQL(InnoDB) : Repeatable Read 기본

------------------------------------------------------------------------

# 5. MVCC

MVCC(Multi-Version Concurrency Control)는 여러 버전의 데이터를 유지하여
읽기와 쓰기의 충돌을 줄이는 기술이다.

장점

-   읽기 성능 향상
-   Lock 경합 감소
-   높은 동시성

대표 DB

-   PostgreSQL
-   Oracle
-   MySQL(InnoDB)

------------------------------------------------------------------------

# 6. Lock과 MVCC 비교

  항목        Lock 기반      MVCC
  ----------- -------------- -----------
  읽기 대기   발생 가능      거의 없음
  동시성      보통           높음
  성능        Lock 영향 큼   우수

------------------------------------------------------------------------

# 7. DB 성능 튜닝 절차

``` text
Slow Query
   ↓
Execution Plan
   ↓
Index 확인
   ↓
Lock 분석
   ↓
Wait Event
   ↓
CPU / Memory
   ↓
Disk I/O
```

### 자주 사용하는 명령

PostgreSQL

``` sql
EXPLAIN ANALYZE
```

Oracle

``` sql
EXPLAIN PLAN
```

MySQL

``` sql
EXPLAIN
```

------------------------------------------------------------------------

# 실무 사례

### Oracle

-   AWR Report
-   ASH Report
-   Wait Event 분석

### PostgreSQL

-   pg_stat_activity
-   pg_locks
-   EXPLAIN ANALYZE

### Kubernetes

StatefulSet 환경에서 DB Pod가 재시작되면 미완료 Transaction과 연결
상태를 함께 점검해야 한다.

------------------------------------------------------------------------

# PM Note

DB 장애 발생 시 점검 순서

``` text
Application
 ↓
Connection Pool
 ↓
Slow Query
 ↓
Execution Plan
 ↓
Lock
 ↓
Deadlock
 ↓
CPU
 ↓
Memory
 ↓
Disk
```

DB CPU가 높다고 즉시 서버를 증설하지 말고 Lock, 실행계획, Index를 먼저
확인한다.

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   Lock 종류
-   Deadlock 4조건
-   Isolation Level
-   MVCC
-   Dirty Read
-   Phantom Read

------------------------------------------------------------------------

# 예상 문제

## 문제 1

Exclusive Lock의 특징은?

1.  여러 사용자가 동시에 수정 가능
2.  읽기/쓰기 모두 독점
3.  읽기 전용
4.  Lock이 필요 없다.

**정답:** 2

### 해설

Exclusive Lock은 데이터 변경 시 사용되며 다른 트랜잭션은 대기한다.

------------------------------------------------------------------------

## 문제 2

Deadlock 발생 조건이 아닌 것은?

1.  Circular Wait
2.  Hold and Wait
3.  Shared Cache
4.  Mutual Exclusion

**정답:** 3

### 해설

Shared Cache는 Deadlock 조건이 아니다. 나머지 네 가지는 필수 조건이다.

------------------------------------------------------------------------

## 문제 3

Oracle 기본 Isolation Level은?

1.  Read Uncommitted
2.  Read Committed
3.  Repeatable Read
4.  Serializable

**정답:** 2

### 해설

Oracle은 기본적으로 Read Committed를 사용하여 Dirty Read를 방지한다.

------------------------------------------------------------------------

## 문제 4

MVCC의 장점은?

1.  읽기 성능 저하
2.  Lock 증가
3.  읽기와 쓰기 충돌 감소
4.  Disk 제거

**정답:** 3

### 해설

MVCC는 여러 버전을 유지하여 읽기 작업이 쓰기 Lock을 기다리지 않도록
한다.

------------------------------------------------------------------------

## 문제 5

DB 성능 분석 시 가장 먼저 확인할 것은?

1.  CPU 교체
2.  Slow Query와 Execution Plan
3.  RAID 변경
4.  서버 재부팅

**정답:** 2

### 해설

성능 문제의 상당수는 비효율적인 SQL과 잘못된 실행계획에서 시작된다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   Lock = 데이터 보호
-   Deadlock = 서로 Lock 대기
-   Isolation Level = 동시성 수준
-   MVCC = 다중 버전 관리
-   Slow Query → Execution Plan → Index → Lock 순으로 분석

------------------------------------------------------------------------

# Day 16 예고

-   NoSQL
-   Key-Value
-   Document DB
-   Column Family
-   Graph DB
-   CAP 이론
-   BASE
