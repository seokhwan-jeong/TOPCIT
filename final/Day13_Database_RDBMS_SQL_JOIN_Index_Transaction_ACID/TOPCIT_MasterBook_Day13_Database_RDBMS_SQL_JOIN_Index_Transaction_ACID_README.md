# 📘 TOPCIT MasterBook 2026

# Day 13 - Database · RDBMS · SQL · JOIN · Index · Transaction · ACID

> **난이도** ⭐⭐⭐⭐☆
>
> **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐
>
> **실무 중요도** ⭐⭐⭐⭐⭐
>
> **예상 학습시간** 110분

------------------------------------------------------------------------

# 학습 목표

-   데이터베이스와 RDBMS의 개념을 이해한다.
-   SQL의 기본 문법과 DDL/DML/DCL/TCL을 구분한다.
-   JOIN의 종류와 사용 목적을 설명할 수 있다.
-   Index의 원리와 장단점을 이해한다.
-   Transaction과 ACID 특성을 설명할 수 있다.

------------------------------------------------------------------------

# 1. Database란?

Database(DB)는 데이터를 체계적으로 저장하고 검색하기 위한 시스템이다.

대표 RDBMS

  제품                   특징
  ---------------------- ---------------------
  Oracle                 대규모 엔터프라이즈
  PostgreSQL             오픈소스, 표준 SQL
  MySQL                  웹 서비스
  Microsoft SQL Server   Windows 환경

``` text
Application
      │
 JDBC/ODBC
      │
   RDBMS
      │
 Storage
```

------------------------------------------------------------------------

# 2. RDBMS

RDBMS(Relational Database Management System)는 데이터를 테이블 형태로
관리한다.

핵심 요소

-   Table
-   Row(Record)
-   Column(Field)
-   Primary Key
-   Foreign Key

------------------------------------------------------------------------

# 3. SQL 분류

  분류   명령
  ------ --------------------------------
  DDL    CREATE, ALTER, DROP
  DML    SELECT, INSERT, UPDATE, DELETE
  DCL    GRANT, REVOKE
  TCL    COMMIT, ROLLBACK

------------------------------------------------------------------------

# 4. SELECT 기본

``` sql
SELECT name, salary
FROM employee
WHERE dept='IT'
ORDER BY salary DESC;
```

실행 순서

``` text
FROM
 ↓
WHERE
 ↓
GROUP BY
 ↓
HAVING
 ↓
SELECT
 ↓
ORDER BY
```

------------------------------------------------------------------------

# 5. JOIN

JOIN은 여러 테이블을 연결하여 조회한다.

  JOIN    설명
  ------- -------------
  INNER   공통 데이터
  LEFT    왼쪽 전체
  RIGHT   오른쪽 전체
  FULL    양쪽 전체

예시

``` sql
SELECT e.name,d.dept_name
FROM employee e
INNER JOIN dept d
ON e.dept_id=d.id;
```

------------------------------------------------------------------------

# 6. Index

Index는 검색 속도를 높이기 위한 자료구조이다.

``` text
Query
  │
Index Search
  │
Data Block
```

장점

-   SELECT 성능 향상

단점

-   INSERT/UPDATE/DELETE 성능 저하
-   저장공간 증가

### 실무 TIP

-   WHERE 절
-   JOIN 컬럼
-   ORDER BY 컬럼

에 자주 사용되는 컬럼에 Index를 생성한다.

------------------------------------------------------------------------

# 7. Transaction

Transaction은 하나의 논리적인 작업 단위이다.

예)

``` text
계좌 A -100만원
        ↓
계좌 B +100만원
```

둘 중 하나라도 실패하면 전체 작업이 취소되어야 한다.

------------------------------------------------------------------------

# 8. ACID

  특성          설명
  ------------- --------------------------
  Atomicity     모두 성공 또는 모두 실패
  Consistency   데이터 일관성
  Isolation     독립성
  Durability    영속성

------------------------------------------------------------------------

# 9. Lock

동시성 제어를 위해 Lock을 사용한다.

-   Shared Lock
-   Exclusive Lock

실무에서는 Lock 경합으로 인해 성능 저하가 자주 발생한다.

------------------------------------------------------------------------

# 10. 실무 사례

## Kubernetes

StatefulSet에서 PostgreSQL 운영 시 Persistent Volume과 백업 전략이
중요하다.

## AWS

-   Amazon RDS
-   Amazon Aurora
-   Read Replica
-   Multi-AZ

## 데이터센터

-   Active-Standby DB
-   RAC Cluster
-   백업 및 복구 정책

------------------------------------------------------------------------

# PM Note

DB 성능 저하 시 확인 순서

``` text
Slow Query
 ↓
Execution Plan
 ↓
Index
 ↓
Lock
 ↓
Transaction
 ↓
Disk I/O
 ↓
CPU/Memory
```

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   DDL/DML
-   PK/FK
-   JOIN
-   Index
-   Transaction
-   ACID
-   COMMIT / ROLLBACK

------------------------------------------------------------------------

# 예상 문제

## 문제 1

DDL에 해당하는 명령은?

1.  SELECT
2.  INSERT
3.  CREATE
4.  COMMIT

**정답:** 3

### 상세 해설

DDL은 데이터베이스 객체를 생성·변경·삭제하는 명령이다. CREATE, ALTER,
DROP이 대표적이다.

------------------------------------------------------------------------

## 문제 2

검색 성능 향상을 위해 사용하는 것은?

1.  Transaction
2.  Index
3.  Rollback
4.  View

**정답:** 2

### 상세 해설

Index는 검색 속도를 향상시키지만 쓰기 작업이 많을수록 오버헤드가
증가한다.

------------------------------------------------------------------------

## 문제 3

계좌이체 기능에서 반드시 필요한 ACID 특성은?

1.  Atomicity
2.  Cache
3.  Routing
4.  Fragmentation

**정답:** 1

### 상세 해설

출금과 입금은 모두 성공하거나 모두 실패해야 하므로 Atomicity가 핵심이다.

------------------------------------------------------------------------

## 문제 4

LEFT JOIN의 특징은?

1.  교집합만 조회
2.  왼쪽 테이블은 모두 조회
3.  오른쪽 테이블만 조회
4.  JOIN 불가

**정답:** 2

### 상세 해설

LEFT JOIN은 왼쪽 테이블의 모든 데이터를 유지하고 오른쪽은 일치하는
데이터만 연결한다.

------------------------------------------------------------------------

## 문제 5

COMMIT의 의미는?

1.  작업 취소
2.  트랜잭션 확정
3.  테이블 삭제
4.  인덱스 생성

**정답:** 2

### 상세 해설

COMMIT은 트랜잭션 결과를 영구 저장하며, ROLLBACK은 이전 상태로 되돌린다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   DB = 데이터 저장소
-   RDBMS = 관계형 DB
-   DDL = 구조
-   DML = 데이터
-   JOIN = 테이블 연결
-   Index = 검색 성능 향상
-   Transaction = 작업 단위
-   ACID = 원자성, 일관성, 독립성, 영속성

------------------------------------------------------------------------

# Day 14 예고

-   정규화
-   반정규화
-   View
-   Stored Procedure
-   Trigger
-   Optimizer
-   Execution Plan
