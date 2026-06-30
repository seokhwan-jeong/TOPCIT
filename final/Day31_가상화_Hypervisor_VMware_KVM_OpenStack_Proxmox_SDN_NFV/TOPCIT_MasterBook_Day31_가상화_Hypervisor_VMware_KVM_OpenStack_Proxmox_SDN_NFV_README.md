# 📘 TOPCIT MasterBook 2026 (V2)

# Day 31 - 가상화 심화 · Hypervisor · VMware · KVM · Hyper-V · OpenStack · Proxmox · SDN · NFV

> **목표:** TOPCIT 500점 대비
>
> **난이도** ⭐⭐⭐⭐⭐ \| **출제빈도** ⭐⭐⭐⭐⭐ \| **실무 중요도**
> ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   가상화 기술의 원리와 필요성을 이해한다.
-   Hypervisor Type1/Type2를 비교한다.
-   VMware, KVM, Hyper-V, Proxmox, OpenStack의 특징을 설명할 수 있다.
-   SDN/NFV와 클라우드의 관계를 이해한다.
-   TOPCIT 실전 문제를 통해 실무형 사고력을 기른다.

------------------------------------------------------------------------

# 1. 가상화(Virtualization)

하나의 물리 서버를 여러 개의 독립적인 가상 서버처럼 사용하는 기술이다.

``` text
Physical Server
      │
 Hypervisor
 ├── VM1
 ├── VM2
 └── VM3
```

## 장점

-   서버 통합
-   자원 활용률 향상
-   장애 격리
-   운영 비용 절감
-   DR 구축 용이

------------------------------------------------------------------------

# 2. Hypervisor

  구분        Type 1       Type 2
  ----------- ------------ -----------------
  설치 위치   HW 위        Host OS 위
  성능        높음         상대적으로 낮음
  활용        데이터센터   개발/테스트

대표 제품

**Type1** - VMware ESXi - Microsoft Hyper-V - KVM - Xen

**Type2** - VMware Workstation - Oracle VirtualBox

------------------------------------------------------------------------

# 3. 주요 가상화 플랫폼

## VMware ESXi

-   기업 데이터센터 표준
-   vMotion, HA, DRS 지원

## KVM

-   Linux Kernel 내장
-   OpenStack 기본 하이퍼바이저

## Hyper-V

-   Windows 기반
-   Azure 친화적

## Proxmox VE

-   KVM + LXC
-   웹 기반 관리
-   오픈소스

------------------------------------------------------------------------

# 4. OpenStack

오픈소스 IaaS 플랫폼

핵심 컴포넌트

  서비스     역할
  ---------- ----------------
  Nova       Compute
  Neutron    Network
  Cinder     Block Storage
  Swift      Object Storage
  Keystone   인증
  Glance     Image

------------------------------------------------------------------------

# 5. SDN / NFV

## SDN

-   Control Plane과 Data Plane 분리
-   중앙 집중형 네트워크 제어

## NFV

-   방화벽, LB 등을 VM/컨테이너로 제공

------------------------------------------------------------------------

# 6. 실무 사례

-   VMware 기반 기업 데이터센터
-   OpenStack 프라이빗 클라우드
-   Proxmox 기반 DR 센터
-   Kubernetes Worker Node는 VM 위에 배치되는 경우가 많음

------------------------------------------------------------------------

# PM 체크리스트

-   CPU VT-x/AMD-V 지원 여부
-   NUMA 고려
-   스토리지 성능
-   HA 구성
-   백업/복구
-   라이선스 비용
-   운영 자동화

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   Type1 = Bare Metal
-   Type2 = Host OS 기반
-   KVM = Linux
-   Hyper-V = Microsoft
-   ESXi = VMware
-   OpenStack = IaaS
-   SDN = 네트워크 제어 분리
-   NFV = 네트워크 기능 가상화

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중)

Hypervisor Type1의 특징은?

① Host OS 위 설치 ② Bare Metal 설치 ③ 성능이 가장 낮다 ④ VirtualBox가
대표 제품

**정답: ②**

**해설:** Type1은 하드웨어 위에 직접 설치되어 성능과 안정성이 우수하다.

------------------------------------------------------------------------

## 문제2 (중)

OpenStack에서 인증을 담당하는 서비스는?

① Nova ② Neutron ③ Keystone ④ Glance

**정답: ③**

**해설:** Keystone은 인증(Authentication)과 권한 관리 서비스를 제공한다.

------------------------------------------------------------------------

## 문제3 (상)

Kubernetes Worker Node를 구축할 때 가장 일반적인 구조는?

① 물리 서버 위 컨테이너 직접 실행 ② VM 위 Kubernetes Node 구성 ③ NAS 위
Pod 실행 ④ Router 위 Container 실행

**정답: ②**

**해설:** 대부분의 기업 환경에서는 VMware, KVM 등의 VM 위에 Kubernetes
노드를 배치한다.

------------------------------------------------------------------------

## 문제4 (상)

SDN의 핵심 개념은?

① Storage 가상화 ② Data Plane과 Control Plane 분리 ③ RAID 구성 ④ CPU
가상화

**정답: ②**

**해설:** SDN은 네트워크 제어를 중앙에서 수행하도록 제어 영역과 전달
영역을 분리한다.

------------------------------------------------------------------------

## 문제5 (중)

다음 중 오픈소스 기반 가상화 플랫폼은?

① VMware ESXi만 ② Hyper-V만 ③ Proxmox VE ④ Azure VM

**정답: ③**

**해설:** Proxmox VE는 KVM 기반의 대표적인 오픈소스 가상화 플랫폼이다.

------------------------------------------------------------------------

# TOPCIT 500점 암기노트

-   Hypervisor Type1 \> Type2 성능
-   OpenStack = Nova + Neutron + Keystone
-   Kubernetes ≠ Hypervisor
-   Container는 VM을 대체하는 것이 아니라 함께 사용되는 경우가 많다.
-   SDN과 NFV는 클라우드 데이터센터 핵심 기술이다.

------------------------------------------------------------------------

# Day 32 예고

-   Docker
-   Image
-   Registry
-   Volume
-   Network
-   Docker Compose
-   Container Runtime
