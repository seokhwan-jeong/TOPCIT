# 📘 TOPCIT MasterBook 2026 (V2)

# Day 39 - Kubernetes 운영 및 장애 대응 · ETCD Backup · Cluster Upgrade · Drain · Cordon · Restore

> 목표: **TOPCIT 500점 대비**\
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Kubernetes 운영 절차를 이해한다.
-   ETCD 백업/복구의 중요성을 설명할 수 있다.
-   Node 유지보수(Drain/Cordon)를 수행할 수 있다.
-   대표 장애를 분석하는 방법을 익힌다.
-   운영 체크리스트를 이해한다.

------------------------------------------------------------------------

# 1. 운영 아키텍처

``` text
Users
  │
API Server
  │
Control Plane
  │
Worker Nodes
  │
Pods
```

운영자는 Control Plane과 Worker Node를 모두 지속적으로 모니터링해야
한다.

------------------------------------------------------------------------

# 2. ETCD Backup & Restore

ETCD는 클러스터의 모든 상태 정보를 저장한다.

백업 대상 - Pod - Service - Secret - ConfigMap - RBAC

복구 절차

1.  Snapshot 생성
2.  Snapshot 검증
3.  Restore 수행
4.  API Server 재연결
5.  서비스 검증

------------------------------------------------------------------------

# 3. Cluster Upgrade

권장 순서

1.  Control Plane 업그레이드
2.  Worker Node 업그레이드
3.  Add-on(CoreDNS 등) 업그레이드
4.  애플리케이션 검증

------------------------------------------------------------------------

# 4. Cordon / Drain / Uncordon

  명령       설명
  ---------- -------------------------------
  cordon     신규 Pod 스케줄링 금지
  drain      Pod 안전하게 다른 Node로 이동
  uncordon   스케줄링 재개

------------------------------------------------------------------------

# 5. 대표 장애

  상태               주요 원인          확인
  ------------------ ------------------ ----------
  Pending            자원 부족/PVC      describe
  CrashLoopBackOff   앱 오류            logs
  ImagePullBackOff   이미지 접근 실패   describe
  OOMKilled          메모리 부족        events

------------------------------------------------------------------------

# 6. 장애 분석 절차

1.  kubectl get pods
2.  kubectl describe pod
3.  kubectl logs
4.  kubectl get events
5.  Node 상태 확인
6.  Storage/Network 확인

------------------------------------------------------------------------

# 7. 운영 사례

-   AKS/EKS 버전 업그레이드
-   ETCD 정기 Snapshot
-   Node 교체 시 Drain 수행
-   Rolling Update 후 Health Check

------------------------------------------------------------------------

# PM 체크리스트

-   ETCD 백업 주기
-   버전 호환성
-   Node Ready
-   Backup 복구 테스트
-   모니터링 알림
-   장애 대응 Runbook

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   ETCD = 상태 저장
-   Snapshot = 백업
-   Restore = 복구
-   Cordon = 스케줄링 금지
-   Drain = Pod 이동
-   Uncordon = 운영 재개

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중 \| ★★★★★)

ETCD Snapshot의 주요 목적은?

① 로그 수집 ② 클러스터 상태 백업 ③ 이미지 저장 ④ 네트워크 설정

**정답:** ②

**해설:** ETCD Snapshot은 Kubernetes의 핵심 메타데이터를 백업한다.

------------------------------------------------------------------------

## 문제2 (상 \| ★★★★★)

Node 유지보수 전 가장 적절한 명령 순서는?

① delete node ② drain ③ cordon → drain ④ reboot

**정답:** ③

**해설:** 먼저 신규 스케줄링을 막고(cordon), 기존 Pod를 안전하게
이동(drain)한다.

------------------------------------------------------------------------

## 문제3 (상)

Pod가 Pending 상태다. 가장 먼저 확인할 것은?

① README ② kubectl describe pod ③ git log ④ docker login

**정답:** ②

**해설:** 이벤트와 스케줄링 실패 원인을 가장 빠르게 확인할 수 있다.

------------------------------------------------------------------------

## 문제4 (상)

Cluster Upgrade 시 가장 먼저 업그레이드하는 것은?

① Worker Node ② 애플리케이션 ③ Control Plane ④ Ingress

**정답:** ③

**해설:** Control Plane을 먼저 업그레이드한 후 Worker Node를 순차적으로
진행한다.

------------------------------------------------------------------------

## 문제5 (시나리오 \| ★★★★★)

Node 교체 작업 중 서비스 중단을 최소화하려면?

① Node 전원 종료 ② cordon + drain 후 작업 ③ Pod 삭제 ④ ETCD 삭제

**정답:** ②

**해설:** Drain은 Pod를 다른 Node로 안전하게 Evict하여 무중단 운영을
지원한다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   ETCD = Kubernetes DB
-   Snapshot = Backup
-   Restore = Recovery
-   Cordon = 신규 배치 금지
-   Drain = 안전한 Pod 이동
-   Uncordon = 재개

------------------------------------------------------------------------

# Day 40 예고

-   Cloud Native Architecture
-   MSA
-   API Gateway
-   Service Discovery
-   Circuit Breaker
-   Resilience
-   12-Factor App
