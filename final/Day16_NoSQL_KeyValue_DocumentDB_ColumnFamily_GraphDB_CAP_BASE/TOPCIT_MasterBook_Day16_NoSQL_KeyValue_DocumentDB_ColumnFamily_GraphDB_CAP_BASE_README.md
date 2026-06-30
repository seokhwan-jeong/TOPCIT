# 📘 TOPCIT MasterBook 2026

# Day 16 - NoSQL · Key-Value · Document DB · Column Family · Graph DB · CAP · BASE

> **난이도** ⭐⭐⭐⭐☆\
> **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐\
> **실무 중요도** ⭐⭐⭐⭐⭐\
> **예상 학습시간** 120분

------------------------------------------------------------------------

# 학습 목표

-   NoSQL이 등장한 배경을 이해한다.
-   NoSQL의 4가지 주요 모델을 구분할 수 있다.
-   CAP 이론과 BASE 모델을 설명할 수 있다.
-   RDBMS와 NoSQL의 차이를 비교할 수 있다.
-   실무에서 어떤 상황에 NoSQL을 선택하는지 이해한다.

------------------------------------------------------------------------

# 1. NoSQL이란?

NoSQL(Not Only SQL)은 관계형 데이터베이스의 한계를 보완하기 위해 등장한
비관계형 데이터베이스이다.

## 등장 배경

-   대용량 데이터(Big Data)
-   높은 동시성
-   수평 확장(Scale-Out)
-   유연한 스키마

``` text
Application
      │
 ┌────┴────┐
 │ RDBMS   │
 │ NoSQL   │
 └─────────┘
```

------------------------------------------------------------------------

# 2. RDBMS vs NoSQL

  항목        RDBMS                NoSQL
  ----------- -------------------- ----------------
  스키마      고정                 유연
  JOIN        지원                 제한적
  확장        Scale-Up             Scale-Out
  트랜잭션    강력                 제한적
  대표 제품   Oracle, PostgreSQL   Redis, MongoDB

------------------------------------------------------------------------

# 3. Key-Value Database

Key와 Value 형태로 데이터를 저장한다.

대표 제품

-   Redis
-   Amazon DynamoDB(일부 용도)

장점

-   매우 빠른 조회
-   캐시 서버로 적합

활용

-   로그인 세션
-   캐시
-   실시간 랭킹

------------------------------------------------------------------------

# 4. Document Database

JSON/BSON 문서 단위로 저장한다.

대표 제품

-   MongoDB
-   CouchDB

예시

``` json
{
  "user":"kim",
  "age":30,
  "skills":["Java","Kubernetes"]
}
```

장점

-   스키마 변경이 쉬움
-   API와 궁합이 좋음

------------------------------------------------------------------------

# 5. Column Family Database

컬럼 단위 저장 구조를 사용한다.

대표 제품

-   Apache Cassandra
-   HBase

활용

-   IoT
-   로그 분석
-   시계열 데이터

------------------------------------------------------------------------

# 6. Graph Database

노드(Node)와 관계(Relationship)를 저장한다.

대표 제품

-   Neo4j

활용

-   SNS 친구 추천
-   추천 시스템
-   사기 탐지

------------------------------------------------------------------------

# 7. CAP 이론

분산 시스템에서는 다음 세 가지를 모두 만족할 수 없다.

  요소   의미
  ------ ---------------------
  C      Consistency
  A      Availability
  P      Partition Tolerance

두 가지만 선택 가능하다.

예)

-   CP : HBase
-   AP : Cassandra

------------------------------------------------------------------------

# 8. BASE 모델

RDBMS의 ACID와 대비되는 개념이다.

-   Basically Available
-   Soft State
-   Eventual Consistency

즉, 최종적으로 데이터 일관성을 맞춘다.

------------------------------------------------------------------------

# 9. 실무 사례

## Redis

-   Session 저장
-   Cache
-   Pub/Sub
-   분산 Lock

## MongoDB

-   로그
-   CMS
-   사용자 프로필

## Kubernetes

-   Redis Cache
-   MongoDB StatefulSet

## AWS

-   DynamoDB
-   ElastiCache
-   DocumentDB

------------------------------------------------------------------------

# PM Note

NoSQL을 선택해야 하는 경우

``` text
데이터 구조 자주 변경
        │
대용량 트래픽
        │
수평 확장 필요
        │
NoSQL 검토
```

반대로 금융, 회계, ERP처럼 강한 트랜잭션이 필요하면 RDBMS가 적합하다.

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   NoSQL 종류
-   Redis
-   MongoDB
-   Cassandra
-   CAP
-   BASE
-   Scale-Up vs Scale-Out

------------------------------------------------------------------------

# 예상 문제

## 문제 1

NoSQL의 가장 큰 특징은?

1.  반드시 JOIN 사용
2.  유연한 스키마
3.  Oracle만 지원
4.  Scale-Up만 가능

**정답:** 2

### 상세 해설

NoSQL은 스키마를 유연하게 변경할 수 있어 데이터 구조가 자주 바뀌는
서비스에 적합하다.

------------------------------------------------------------------------

## 문제 2

캐시 서버로 가장 많이 사용하는 NoSQL은?

1.  Oracle
2.  Redis
3.  Neo4j
4.  MySQL

**정답:** 2

### 상세 해설

Redis는 메모리 기반 Key-Value DB로 매우 빠른 응답 속도를 제공한다.

------------------------------------------------------------------------

## 문제 3

문서(Document) 기반 DB는?

1.  MongoDB
2.  Redis
3.  Oracle
4.  PostgreSQL

**정답:** 1

### 상세 해설

MongoDB는 BSON 문서를 저장하는 대표적인 Document Database이다.

------------------------------------------------------------------------

## 문제 4

CAP 이론에서 세 가지 요소는?

1.  Cache, API, Proxy
2.  CPU, Application, Process
3.  Consistency, Availability, Partition Tolerance
4.  Cluster, Access, Port

**정답:** 3

### 상세 해설

분산 시스템에서는 C, A, P를 모두 동시에 만족시킬 수 없다는 것이 CAP
이론이다.

------------------------------------------------------------------------

## 문제 5

BASE 모델의 특징은?

1.  즉시 일관성만 허용
2.  최종 일관성(Eventual Consistency)
3.  JOIN 필수
4.  ACID 강화

**정답:** 2

### 상세 해설

BASE는 일부 시점의 불일치를 허용하더라도 최종적으로 일관성을 맞추는
모델이다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   NoSQL = 유연한 스키마
-   Redis = Key-Value
-   MongoDB = Document
-   Cassandra = Column Family
-   Neo4j = Graph
-   CAP = C, A, P
-   BASE = Eventual Consistency

------------------------------------------------------------------------

# Day 17 예고

-   자료구조
-   Array
-   Linked List
-   Stack
-   Queue
-   Tree
-   Hash Table
