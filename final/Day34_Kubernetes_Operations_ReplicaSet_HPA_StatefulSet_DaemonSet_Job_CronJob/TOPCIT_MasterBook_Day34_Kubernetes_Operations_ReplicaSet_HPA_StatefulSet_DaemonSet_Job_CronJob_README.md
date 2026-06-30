# 📘 TOPCIT MasterBook 2026 (V2)

# Day 34 - Kubernetes 운영 심화 · ReplicaSet · HPA · DaemonSet · StatefulSet · Job · CronJob

> 목표: **TOPCIT 500점 대비**\
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Kubernetes의 주요 Workload를 구분한다.
-   ReplicaSet, Deployment, StatefulSet의 차이를 이해한다.
-   HPA와 Resource Request/Limit의 관계를 설명한다.
-   Job과 CronJob의 활용 사례를 이해한다.
-   장애 분석 절차를 익힌다.

------------------------------------------------------------------------

# 1. Workload 종류

  리소스        용도
  ------------- ----------------------
  Pod           최소 실행 단위
  ReplicaSet    동일 Pod 개수 유지
  Deployment    무상태 앱 배포
  StatefulSet   상태 저장 앱
  DaemonSet     모든 Node에 Pod 실행
  Job           1회성 작업
  CronJob       예약 작업

------------------------------------------------------------------------

# 2. ReplicaSet vs Deployment

ReplicaSet은 Pod 수를 유지한다.

Deployment는 ReplicaSet을 관리하며 다음 기능을 제공한다.

-   Rolling Update
-   Rollback
-   Revision 관리

``` text
Deployment
    │
ReplicaSet
    │
 Pods
```

------------------------------------------------------------------------

# 3. StatefulSet

상태가 있는 애플리케이션에 사용한다.

특징

-   고정 Pod 이름
-   고정 스토리지(PVC)
-   순차 생성/삭제

대표 사례

-   PostgreSQL
-   MySQL
-   Kafka
-   Elasticsearch

------------------------------------------------------------------------

# 4. DaemonSet

모든 Worker Node에 하나의 Pod를 실행한다.

활용

-   Fluent Bit
-   Node Exporter
-   CNI Plugin
-   보안 에이전트

------------------------------------------------------------------------

# 5. Job / CronJob

## Job

-   배치 작업
-   백업
-   데이터 마이그레이션

## CronJob

Cron 형식으로 예약 실행

예)

``` text
0 2 * * *
```

매일 새벽 2시 실행

------------------------------------------------------------------------

# 6. HPA(Horizontal Pod Autoscaler)

CPU, Memory 등의 메트릭을 기반으로 Pod 개수를 자동 조절한다.

``` text
CPU ↑
  │
HPA
  │
Pod 2 → Pod 6
```

------------------------------------------------------------------------

# 7. Resource 관리

  항목      의미
  --------- ----------------
  Request   최소 보장 자원
  Limit     최대 사용 자원

Request가 Scheduler의 배치 기준이 된다.

------------------------------------------------------------------------

# 8. Probe

## Liveness Probe

-   프로세스 생존 확인
-   실패 시 재시작

## Readiness Probe

-   서비스 가능 여부 확인
-   실패 시 트래픽 제외

------------------------------------------------------------------------

# 9. 장애 분석

점검 순서

1.  kubectl get pod
2.  kubectl describe pod
3.  kubectl logs
4.  Event 확인
5.  Node 상태 확인

대표 오류

-   CrashLoopBackOff
-   ImagePullBackOff
-   Pending
-   OOMKilled

------------------------------------------------------------------------

# 실무 사례

-   HPA + Cluster Autoscaler 운영
-   DaemonSet으로 로그 수집
-   StatefulSet으로 DB 운영
-   CronJob으로 야간 백업
-   Readiness Probe로 무중단 배포

------------------------------------------------------------------------

# PM 체크리스트

-   Request/Limit 설정
-   HPA 임계값
-   PVC 용량
-   Node 자원
-   Rolling Update 전략
-   백업 정책

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제 1 (중)

상태 저장 애플리케이션에 가장 적합한 리소스는?

① Deployment ② ReplicaSet ③ StatefulSet ④ DaemonSet

**정답:** ③

**해설:** StatefulSet은 고정 네트워크 ID와 스토리지를 제공하여 DB와 같은
Stateful 애플리케이션에 적합하다.

------------------------------------------------------------------------

## 문제 2 (상)

모든 Worker Node에 하나씩 실행해야 하는 로그 수집기는?

① Deployment ② Job ③ DaemonSet ④ HPA

**정답:** ③

**해설:** DaemonSet은 Node마다 하나의 Pod를 실행하므로 모니터링·로그
수집에 적합하다.

------------------------------------------------------------------------

## 문제 3 (상)

Pod 개수를 CPU 사용량에 따라 자동 조절하는 기능은?

① ReplicaSet ② HPA ③ PVC ④ Ingress

**정답:** ②

**해설:** HPA는 Metrics Server 등의 메트릭을 기반으로 수평 확장을
수행한다.

------------------------------------------------------------------------

## 문제 4 (상)

서비스 준비가 되지 않은 Pod를 Load Balancer 대상에서 제외하는 Probe는?

① Startup Probe ② Liveness Probe ③ Readiness Probe ④ Health Probe

**정답:** ③

**해설:** Readiness Probe가 실패하면 Pod는 살아 있어도 Service
Endpoint에서 제외된다.

------------------------------------------------------------------------

## 문제 5 (상)

Pod가 CrashLoopBackOff 상태라면 가장 먼저 확인해야 할 명령은?

① kubectl logs ② ping ③ traceroute ④ nslookup

**정답:** ①

**해설:** 애플리케이션 오류인지 확인하기 위해 로그를 먼저 확인한다.

------------------------------------------------------------------------

# 시험 직전 암기

-   Deployment = 무상태
-   StatefulSet = 상태 저장
-   DaemonSet = Node당 1개
-   Job = 1회
-   CronJob = 예약
-   HPA = Pod 자동 확장
-   Request = 최소
-   Limit = 최대

------------------------------------------------------------------------

# Day 35 예고

-   Kubernetes Storage
-   PV / PVC
-   StorageClass
-   CSI
-   ConfigMap
-   Secret
-   Helm
