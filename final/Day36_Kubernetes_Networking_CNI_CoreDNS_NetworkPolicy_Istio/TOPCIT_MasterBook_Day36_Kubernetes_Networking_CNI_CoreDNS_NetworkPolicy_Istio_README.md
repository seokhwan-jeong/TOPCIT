# 📘 TOPCIT MasterBook 2026 (V2)

# Day 36 - Kubernetes Networking · CNI · kube-proxy · CoreDNS · NetworkPolicy · Service Mesh · Istio

> 목표: **TOPCIT 500점 대비**\
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Kubernetes 네트워크 구조를 이해한다.
-   CNI와 kube-proxy의 역할을 설명할 수 있다.
-   CoreDNS, NetworkPolicy, Service Mesh를 구분할 수 있다.
-   Istio와 mTLS의 목적을 이해한다.
-   네트워크 장애 점검 절차를 익힌다.

------------------------------------------------------------------------

# 1. Kubernetes 네트워크 구조

``` text
Client
  │
Ingress
  │
Service
  │
Pod
```

원칙 - Pod ↔ Pod 직접 통신 가능 - Node 간 Pod 통신 가능 - NAT 없이 Pod
IP 사용

------------------------------------------------------------------------

# 2. CNI(Container Network Interface)

CNI는 Pod 네트워크를 구성하는 표준 인터페이스이다.

대표 구현체

  CNI         특징
  ----------- --------------------
  Calico      NetworkPolicy 지원
  Flannel     단순하고 빠름
  Cilium      eBPF 기반
  Weave Net   쉬운 구성

------------------------------------------------------------------------

# 3. kube-proxy

Service와 Pod 사이의 트래픽을 전달한다.

동작 모드

-   iptables
-   IPVS

IPVS는 대규모 환경에서 성능이 우수하다.

------------------------------------------------------------------------

# 4. CoreDNS

클러스터 내부 DNS 서비스.

예시

``` text
web.default.svc.cluster.local
```

기능 - 서비스 이름 해석 - Pod DNS 조회

------------------------------------------------------------------------

# 5. NetworkPolicy

Pod 간 통신을 제어한다.

적용 대상 - Ingress - Egress

기본적으로 NetworkPolicy가 없으면 대부분의 CNI에서 통신이 허용된다.

------------------------------------------------------------------------

# 6. Service Mesh

애플리케이션 수정 없이 통신을 제어하는 계층.

주요 기능 - mTLS - Traffic Control - Retry - Circuit Breaker -
Observability

대표 제품 - Istio - Linkerd

------------------------------------------------------------------------

# 7. Istio

구성 요소

-   Envoy Proxy
-   Control Plane

장점 - 보안 강화 - 트래픽 분산 - Canary Release - Telemetry

------------------------------------------------------------------------

# 8. 실무 사례

-   AKS + Azure CNI
-   EKS + VPC CNI
-   Calico NetworkPolicy
-   Istio 기반 Blue/Green 배포
-   Prometheus + Grafana 모니터링

------------------------------------------------------------------------

# PM 체크리스트

-   CoreDNS 상태
-   kube-proxy 상태
-   CNI Pod 정상 여부
-   NetworkPolicy 영향
-   Service Endpoint 확인
-   Ingress Controller 로그

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   CNI = 네트워크 구성
-   kube-proxy = Service 연결
-   CoreDNS = DNS
-   NetworkPolicy = 접근제어
-   Istio = Service Mesh
-   mTLS = 서비스 간 암호화

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중)

Pod 네트워크를 구성하는 표준은?

① CSI ② CNI ③ CRI ④ OCI

**정답:** ②

**해설:** CNI는 Kubernetes가 네트워크 플러그인과 연동하기 위한 표준이다.

------------------------------------------------------------------------

## 문제2 (중)

클러스터 내부 DNS를 담당하는 구성 요소는?

① kubelet ② CoreDNS ③ etcd ④ Helm

**정답:** ②

**해설:** CoreDNS는 Service 이름을 IP로 변환한다.

------------------------------------------------------------------------

## 문제3 (상)

Pod 간 통신을 제어하는 리소스는?

① Deployment ② ConfigMap ③ NetworkPolicy ④ PV

**정답:** ③

**해설:** NetworkPolicy는 Ingress/Egress 트래픽을 제어한다.

------------------------------------------------------------------------

## 문제4 (상)

Service Mesh의 대표 기능이 아닌 것은?

① mTLS ② Traffic Routing ③ Circuit Breaker ④ RAID

**정답:** ④

**해설:** RAID는 스토리지 기술이며 Service Mesh와 무관하다.

------------------------------------------------------------------------

## 문제5 (상)

대규모 클러스터에서 kube-proxy 성능 향상을 위해 많이 사용하는 모드는?

① FTP ② IPVS ③ SMTP ④ NFS

**정답:** ②

**해설:** IPVS는 iptables보다 확장성과 성능이 우수하다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   CNI = Pod Network
-   CoreDNS = DNS
-   kube-proxy = Service
-   NetworkPolicy = ACL
-   Istio = Service Mesh
-   mTLS = 암호화

------------------------------------------------------------------------

# Day 37 예고

-   Kubernetes Security
-   RBAC
-   ServiceAccount
-   Admission Controller
-   Pod Security
-   OPA Gatekeeper
-   Falco
