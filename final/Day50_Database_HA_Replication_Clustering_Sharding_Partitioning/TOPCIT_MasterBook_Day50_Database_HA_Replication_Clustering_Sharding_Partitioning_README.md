# 📘 TOPCIT MasterBook 2026 (V2)

# Day 50 - Database High Availability · Replication · Clustering · Sharding · Partitioning · Failover

> 목표: **TOPCIT 500점 대비**
>
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   데이터베이스 고가용성(HA)의 개념을 이해한다.
-   Replication, Clustering, Sharding, Partitioning을 비교할 수 있다.
-   Failover와 Failback 절차를 설명할 수 있다.
-   Read Replica의 활용 목적을 이해한다.
-   업무 특성에 맞는 DB 아키텍처를 선택할 수 있다.

------------------------------------------------------------------------

# 1. Database High Availability

HA는 장애 발생 시에도 서비스를 지속하기 위한 구조이다.

``` text
Client
   │
Load Balancer
   │
Primary DB
   │
Replication
   │
Standby DB
```

목표 - 서비스 연속성 - 데이터 보호 - 빠른 복구

------------------------------------------------------------------------

# 2. Replication

  방식            특징                  활용
  --------------- --------------------- -------------
  Master-Slave    쓰기 1대, 읽기 다수   일반 서비스
  Master-Master   양방향 쓰기           특수 환경
  Read Replica    읽기 전용 복제        조회 분산

복제 방식

-   동기(Synchronous): 데이터 손실 최소
-   비동기(Asynchronous): 성능과 거리 우수

------------------------------------------------------------------------

# 3. Clustering

여러 DB 서버를 하나의 시스템처럼 운영한다.

장점 - 장애 허용 - 부하 분산 - 가용성 향상

대표 사례 - Oracle RAC - MySQL InnoDB Cluster

------------------------------------------------------------------------

# 4. Sharding

데이터를 여러 DB에 수평 분산한다.

예시

``` text
Shard1 : 고객 A~H
Shard2 : 고객 I~P
Shard3 : 고객 Q~Z
```

장점 - 대규모 확장 - 부하 분산

단점 - 설계 복잡 - JOIN 어려움

------------------------------------------------------------------------

# 5. Partitioning

하나의 테이블을 논리적으로 분할한다.

종류 - Range - List - Hash - Composite

Sharding은 DB 분산, Partitioning은 테이블 분할이라는 점이 핵심 차이이다.

------------------------------------------------------------------------

# 6. Failover / Failback

Failover - Primary 장애 시 Standby 전환

Failback - 장애 복구 후 원래 구조로 복귀

자동 Failover는 서비스 중단 시간을 줄인다.

------------------------------------------------------------------------

# 7. Backup vs Replication

  항목        Backup   Replication
  ----------- -------- -------------
  목적        복구     서비스 지속
  실시간      X        O
  삭제 전파   X        O
  재해 복구   O        일부

Replication은 Backup을 대체할 수 없다.

------------------------------------------------------------------------

# 8. 실무 사례

-   Oracle Data Guard
-   PostgreSQL Streaming Replication
-   MySQL Read Replica
-   Azure SQL Geo-Replication
-   Amazon RDS Multi-AZ

------------------------------------------------------------------------

# PM 체크리스트

-   RTO/RPO 확인
-   복제 지연 모니터링
-   Failover 테스트
-   백업 검증
-   Split Brain 방지
-   운영 Runbook

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   HA = 고가용성
-   Replication = 복제
-   Cluster = 이중화
-   Sharding = DB 분산
-   Partition = 테이블 분할
-   Failover = 자동 전환
-   Backup ≠ Replication

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중 \| ★★★★★)

조회 부하를 줄이기 위한 가장 적절한 구성은?

① Read Replica ② RAID0 ③ Trigger ④ View

**정답: ①**

**해설:** Read Replica는 읽기 요청을 분산하여 Primary DB의 부하를
줄인다.

------------------------------------------------------------------------

## 문제2 (상 \| ★★★★★)

Primary DB 장애 시 Standby DB로 자동 전환하는 기능은?

① Rollback ② Failover ③ Partitioning ④ Sharding

**정답: ②**

**해설:** Failover는 장애 발생 시 대기 서버를 서비스 서버로 승격한다.

------------------------------------------------------------------------

## 문제3 (상 \| ★★★★★)

하나의 테이블을 범위별로 나누는 기술은?

① Sharding ② Partitioning ③ Replication ④ Snapshot

**정답: ②**

------------------------------------------------------------------------

## 문제4 (시나리오 \| ★★★★★)

전 세계 사용자 증가로 단일 DB 확장이 한계에 도달했다. 가장 적절한
방법은?

① Trigger 추가 ② Sharding 적용 ③ Index 삭제 ④ COMMIT 제거

**정답: ②**

**해설:** Sharding은 데이터를 여러 DB에 분산해 수평 확장을 지원한다.

------------------------------------------------------------------------

## 문제5 (시나리오 \| ★★★★★)

실시간 복제를 사용 중이지만 랜섬웨어로 데이터가 암호화되었다. 복구를
위해 가장 필요한 것은?

① Replication만 유지 ② Backup 데이터 활용 ③ Read Replica 증설 ④
Partition 추가

**정답: ②**

**해설:** 복제는 변경 사항을 그대로 전파하므로 랜섬웨어도 복제될 수
있다. 독립적인 Backup이 필수이다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   HA = High Availability
-   Read Replica = 조회 분산
-   Failover = 장애 전환
-   Sharding = DB 분산
-   Partition = Table 분할
-   Sync = RPO 최소
-   Backup ≠ Replication

------------------------------------------------------------------------

# Day 51 예고

-   Big Data
-   Hadoop
-   HDFS
-   MapReduce
-   Spark
-   Kafka
-   Data Lake
-   Data Warehouse
