# 📘 TOPCIT MasterBook 2026 (V2)

# Day 33 - Kubernetes Architecture · Control Plane · Node · Pod · Deployment · Service · Ingress

> 목표: **TOPCIT 500점 대비**
>
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Kubernetes 아키텍처를 이해한다.
-   Control Plane과 Worker Node의 역할을 설명할 수 있다.
-   Pod, Deployment, Service, Ingress의 차이를 이해한다.
-   ConfigMap, Secret, PV/PVC의 용도를 설명할 수 있다.
-   장애 상황에서 점검 순서를 이해한다.

------------------------------------------------------------------------

# 1. Kubernetes 아키텍처

``` text
                Control Plane
+--------------------------------------+
| API Server | Scheduler | Controller |
|              etcd                |
+--------------------------------------+
             │
      -------------------
      │                 │
 Worker Node       Worker Node
 kubelet           kubelet
 kube-proxy        kube-proxy
 Container Runtime Container Runtime
      │                 │
     Pods              Pods
```

Control Plane은 클러스터를 관리하고 Worker Node는 실제 애플리케이션을
실행한다.

------------------------------------------------------------------------

# 2. Control Plane

  구성 요소            역할
  -------------------- --------------------------
  API Server           모든 요청의 진입점
  etcd                 클러스터 상태 저장
  Scheduler            Pod를 적절한 Node에 배치
  Controller Manager   Desired State 유지

------------------------------------------------------------------------

# 3. Worker Node

구성 요소

-   kubelet
-   kube-proxy
-   Container Runtime(containerd 등)

kubelet은 API Server와 통신하며 Pod 상태를 유지한다.

------------------------------------------------------------------------

# 4. Pod

-   Kubernetes의 최소 배포 단위
-   하나 이상의 컨테이너 포함
-   동일 IP와 Storage 공유

------------------------------------------------------------------------

# 5. Deployment

Deployment는 ReplicaSet을 이용하여 원하는 개수의 Pod를 유지한다.

장점

-   Rolling Update
-   Rollback
-   Self Healing

------------------------------------------------------------------------

# 6. Service

  타입           용도
  -------------- ----------------------
  ClusterIP      내부 통신
  NodePort       외부 테스트
  LoadBalancer   클라우드 외부 서비스
  ExternalName   외부 DNS 연결

------------------------------------------------------------------------

# 7. Ingress

HTTP/HTTPS L7 라우팅을 제공한다.

기능

-   Host 기반 라우팅
-   Path 기반 라우팅
-   TLS 종료

------------------------------------------------------------------------

# 8. ConfigMap / Secret

ConfigMap - 일반 설정

Secret - 비밀번호 - API Key - 인증서

------------------------------------------------------------------------

# 9. Persistent Volume

PV - 실제 스토리지

PVC - Pod가 요청하는 스토리지

StorageClass - 동적 Provisioning

------------------------------------------------------------------------

# 실무 사례

-   AKS / EKS / GKE 운영
-   GitHub Actions → ACR → Argo CD → Kubernetes
-   Readiness Probe 실패 시 Service에서 제외
-   Liveness Probe 실패 시 Pod 자동 재시작

------------------------------------------------------------------------

# PM 체크리스트

-   Node Ready 상태
-   Pod CrashLoopBackOff 확인
-   kubectl describe
-   kubectl logs
-   PVC Bound 상태
-   Ingress 연결
-   Service Endpoint

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   API Server = 중앙 관문
-   etcd = 상태 저장
-   Scheduler = Node 선택
-   Deployment = Replica 관리
-   Service = 접근
-   Ingress = L7
-   ConfigMap ≠ Secret
-   PV = Storage

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중)

클러스터 상태 정보를 저장하는 구성요소는?

① kubelet ② etcd ③ Scheduler ④ kube-proxy

**정답: ②**

**해설:** etcd는 분산 Key-Value 저장소로 Kubernetes의 모든 상태 정보를
저장한다.

------------------------------------------------------------------------

## 문제2 (중)

Pod를 실행할 Node를 선택하는 구성요소는?

① API Server ② Scheduler ③ Ingress ④ Service

**정답: ②**

**해설:** Scheduler는 자원 사용량과 정책을 고려해 적절한 Worker Node를
선택한다.

------------------------------------------------------------------------

## 문제3 (상)

외부 HTTP 요청을 URL Path 기준으로 분기하려면?

① ClusterIP ② ConfigMap ③ Ingress ④ PV

**정답: ③**

**해설:** Ingress는 L7에서 Host 및 Path 기반 라우팅을 제공한다.

------------------------------------------------------------------------

## 문제4 (상)

민감한 DB 비밀번호 저장에 적합한 것은?

① ConfigMap ② Secret ③ Deployment ④ ReplicaSet

**정답: ②**

**해설:** Secret은 Base64 인코딩 및 접근 제어를 통해 민감 정보를
관리한다.

------------------------------------------------------------------------

## 문제5 (상)

Pod가 계속 재시작되는 경우 가장 먼저 확인할 것은?

① README ② kubectl logs ③ DNS 서버 변경 ④ RAID 상태

**정답: ②**

**해설:** Pod 로그와 describe 결과를 통해 CrashLoopBackOff 원인을 먼저
확인한다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   API Server = 관문
-   etcd = DB
-   Scheduler = 배치
-   kubelet = Node Agent
-   Pod = 최소 실행 단위
-   Deployment = 선언적 관리
-   Service = 네트워크
-   Ingress = L7 Gateway
-   PV/PVC = 영구 저장소

------------------------------------------------------------------------

# Day 34 예고

-   Kubernetes 운영
-   ReplicaSet
-   HPA
-   DaemonSet
-   StatefulSet
-   Job
-   CronJob
-   장애 대응
