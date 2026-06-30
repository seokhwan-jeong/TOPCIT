# 📘 TOPCIT MasterBook 2026 (V2)

# Day 30 - 클라우드 컴퓨팅 · IaaS · PaaS · SaaS · Virtualization · Container · Kubernetes · Cloud Native

> **난이도** ⭐⭐⭐⭐⭐ **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐ **실무 중요도**
> ⭐⭐⭐⭐⭐ **예상 학습시간** 150분

------------------------------------------------------------------------

# 학습 목표

-   클라우드 컴퓨팅의 핵심 개념을 이해한다.
-   IaaS, PaaS, SaaS를 비교할 수 있다.
-   가상화와 컨테이너의 차이를 설명할 수 있다.
-   Kubernetes와 Cloud Native의 관계를 이해한다.
-   실무에서 적절한 클라우드 서비스를 선택할 수 있다.

------------------------------------------------------------------------

# 1. 클라우드 컴퓨팅

클라우드 컴퓨팅은 인터넷을 통해 컴퓨팅 자원을 필요한 만큼 사용하는
방식이다.

``` text
사용자
   │
Internet
   │
Cloud Provider
   ├── Compute
   ├── Storage
   ├── Network
   └── AI / DB / Security
```

## 장점

-   초기 투자 비용 절감
-   빠른 확장(Elasticity)
-   사용량 기반 과금(Pay-as-you-go)
-   고가용성

------------------------------------------------------------------------

# 2. 서비스 모델

  구분   사용자가 관리   CSP가 관리   대표 서비스
  ------ --------------- ------------ ----------------------
  IaaS   OS 이상         HW           EC2, Azure VM
  PaaS   애플리케이션    OS 이하      App Service, GAE
  SaaS   거의 없음       전체         Microsoft 365, Gmail

### 암기법

-   IaaS = 서버 제공
-   PaaS = 개발 플랫폼 제공
-   SaaS = 완성된 서비스 제공

------------------------------------------------------------------------

# 3. 배포 모델

  모델            특징
  --------------- --------------------
  Public Cloud    외부 CSP 사용
  Private Cloud   기업 내부 전용
  Hybrid Cloud    Public + Private
  Multi Cloud     여러 CSP 동시 활용

------------------------------------------------------------------------

# 4. Virtualization vs Container

  항목          Virtual Machine   Container
  ------------- ----------------- -----------
  가상화 대상   HW                OS
  Guest OS      필요              불필요
  속도          상대적으로 느림   빠름
  대표 기술     VMware, Hyper-V   Docker

``` text
VM
Hardware
 └─ Hypervisor
     ├─ Guest OS
     └─ Guest OS

Container
Host OS
 └─ Container Runtime
     ├─ App
     └─ App
```

------------------------------------------------------------------------

# 5. Kubernetes

Kubernetes는 컨테이너 오케스트레이션 플랫폼이다.

주요 구성

-   Pod
-   Deployment
-   Service
-   Ingress
-   ConfigMap
-   Secret

장점

-   Auto Scaling
-   Self Healing
-   Rolling Update

------------------------------------------------------------------------

# 6. Cloud Native

Cloud Native의 핵심 요소

-   Microservices
-   Containers
-   DevOps
-   CI/CD
-   Kubernetes
-   Observability

------------------------------------------------------------------------

# 7. 실무 사례

### AWS

-   EC2(IaaS)
-   RDS
-   EKS
-   S3

### Azure

-   Azure VM
-   AKS
-   App Service

### Kubernetes 프로젝트

GitHub → GitHub Actions → Docker → ACR/ECR → Kubernetes → Argo CD

------------------------------------------------------------------------

# PM Note

클라우드 도입 체크리스트

-   요구사항
-   보안
-   비용
-   성능
-   DR
-   운영 자동화

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   IaaS/PaaS/SaaS
-   VM vs Container
-   Kubernetes
-   Cloud Native
-   Hybrid Cloud

------------------------------------------------------------------------

# 예상 문제

## 문제 1

OS까지 사용자가 관리하는 서비스는?

1.  SaaS
2.  PaaS
3.  IaaS
4.  FaaS

**정답:** 3

### 상세 해설

IaaS는 사용자가 운영체제, 미들웨어, 애플리케이션을 직접 관리한다.

------------------------------------------------------------------------

## 문제 2

컨테이너의 가장 큰 장점은?

1.  Guest OS 필수
2.  빠른 실행과 높은 자원 효율
3.  무조건 보안 강화
4.  물리 서버만 사용

**정답:** 2

### 상세 해설

컨테이너는 Host OS를 공유하여 VM보다 가볍고 빠르게 실행된다.

------------------------------------------------------------------------

## 문제 3

Kubernetes의 주요 기능이 아닌 것은?

1.  Auto Scaling
2.  Self Healing
3.  Rolling Update
4.  RAID 구성

**정답:** 4

### 상세 해설

RAID는 스토리지 기술이며 Kubernetes 기능이 아니다.

------------------------------------------------------------------------

## 문제 4

Cloud Native의 핵심 기술이 아닌 것은?

1.  Kubernetes
2.  Containers
3.  DevOps
4.  CRT Monitor

**정답:** 4

### 상세 해설

Cloud Native는 컨테이너와 쿠버네티스 기반의 현대적 애플리케이션 개발
방식을 의미한다.

------------------------------------------------------------------------

## 문제 5

Hybrid Cloud의 설명으로 맞는 것은?

1.  Public Cloud만 사용
2.  Private Cloud만 사용
3.  Public과 Private를 함께 사용
4.  하나의 VM만 사용

**정답:** 3

### 상세 해설

Hybrid Cloud는 내부 시스템과 퍼블릭 클라우드를 함께 활용해 유연성과
보안을 동시에 확보한다.

------------------------------------------------------------------------

# 핵심 암기노트

-   IaaS = 인프라
-   PaaS = 플랫폼
-   SaaS = 서비스
-   VM = Hypervisor
-   Container = Docker
-   Kubernetes = 오케스트레이션
-   Cloud Native = MSA + Container + DevOps

------------------------------------------------------------------------

# Day 31 예고

-   가상화 심화
-   Hypervisor Type 1/2
-   VMware
-   KVM
-   Hyper-V
-   OpenStack
-   Proxmox
