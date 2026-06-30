# 📘 TOPCIT MasterBook 2026

# Day 09 - L2 Switch · L3 Switch · VLAN · STP · Trunk · Access Port

> **난이도** ⭐⭐⭐⭐☆\
> **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐\
> **실무 중요도** ⭐⭐⭐⭐⭐\
> **예상 학습시간** 90분

------------------------------------------------------------------------

# 학습 목표

-   L2 Switch와 L3 Switch의 차이를 이해한다.
-   VLAN의 목적과 장점을 설명할 수 있다.
-   Access Port와 Trunk Port를 구분할 수 있다.
-   STP의 동작 원리를 이해한다.
-   데이터센터 네트워크의 기본 구조를 이해한다.

------------------------------------------------------------------------

# 1. Switching

Switch는 목적지 MAC Address를 기반으로 프레임을 전달하는 장비이다.

``` text
PC1 ─┐
PC2 ─┼── L2 Switch ── Server
PC3 ─┘
```

L2 Switch는 MAC Address Table(CAM Table)을 학습하여 목적지 포트로만
프레임을 전송한다.

브로드캐스트는 동일 VLAN 전체로 전달된다.

------------------------------------------------------------------------

# 2. L2 Switch vs L3 Switch

  항목           L2 Switch   L3 Switch
  -------------- ----------- -----------
  동작 계층      L2          L3
  주소 기준      MAC         IP
  라우팅         X           O
  VLAN 간 통신   X           O

### 실무 TIP

-   같은 VLAN 통신 → L2 Switch
-   VLAN 간 통신 → L3 Switch 또는 Router

------------------------------------------------------------------------

# 3. MAC Address Table

Switch는 Source MAC을 학습하여 CAM Table을 생성한다.

``` text
MAC Address          Port
00:11:22:33:44:55 -> Gi0/1
AA:BB:CC:DD:EE:FF -> Gi0/2
```

Unknown Unicast는 Flooding 된다.

------------------------------------------------------------------------

# 4. VLAN(Virtual LAN)

VLAN은 하나의 물리 스위치를 여러 개의 논리 네트워크로 분리하는 기술이다.

장점

-   브로드캐스트 감소
-   보안 향상
-   부서별 네트워크 분리
-   관리 편의성

예시

``` text
VLAN10 : 인사팀
VLAN20 : 개발팀
VLAN30 : 서버망
```

------------------------------------------------------------------------

# 5. Access Port와 Trunk Port

## Access Port

-   하나의 VLAN만 전달
-   PC 연결

## Trunk Port

-   여러 VLAN 동시 전달
-   Switch ↔ Switch
-   Switch ↔ Firewall
-   Switch ↔ Hypervisor

802.1Q Tag를 사용하여 VLAN 정보를 전달한다.

  구분      Access   Trunk
  --------- -------- ---------
  VLAN 수   1개      여러 개
  태그      없음     802.1Q

------------------------------------------------------------------------

# 6. STP(Spanning Tree Protocol)

L2 Loop를 방지하는 프로토콜이다.

Loop가 발생하면

-   Broadcast Storm
-   MAC Table Flapping
-   CPU 과부하

등의 문제가 발생한다.

동작 과정

``` text
Root Bridge 선출
      ↓
최단 경로 계산
      ↓
불필요한 포트 Blocking
```

------------------------------------------------------------------------

# 7. 실무 사례

## VMware

ESXi Uplink는 Trunk Port를 사용하는 경우가 많다.

## Kubernetes

Worker Node는 여러 VLAN을 사용하는 환경이 존재한다.

## 데이터센터

-   Management VLAN
-   Service VLAN
-   Storage VLAN
-   Backup VLAN

으로 분리하는 것이 일반적이다.

------------------------------------------------------------------------

# PM Note

VLAN 간 통신 장애 발생 시 확인 순서

``` text
VLAN 생성
 ↓
Access Port
 ↓
Trunk 설정
 ↓
Native VLAN
 ↓
L3 Interface(SVI)
 ↓
Routing
 ↓
Firewall
```

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   L2/L3 Switch 차이
-   VLAN
-   Access Port
-   Trunk Port
-   STP
-   Broadcast Storm

------------------------------------------------------------------------

# 예상 문제

## 문제 1

VLAN의 가장 큰 목적은?

1.  CPU 증가
2.  논리적 네트워크 분리
3.  RAID 구성
4.  메모리 증가

**정답:** 2

### 상세 해설

VLAN은 하나의 물리 스위치를 여러 개의 논리 네트워크로 분리하여 보안과
관리 효율성을 높인다.

------------------------------------------------------------------------

## 문제 2

Trunk Port에서 사용하는 VLAN 태그 표준은?

1.  IEEE 802.3
2.  IEEE 802.11
3.  IEEE 802.1Q
4.  IEEE 802.15

**정답:** 3

### 상세 해설

802.1Q는 Ethernet Frame에 VLAN Tag를 추가하여 여러 VLAN 정보를 전달한다.

------------------------------------------------------------------------

## 문제 3

STP의 목적은?

1.  DNS 성능 향상
2.  L2 Loop 방지
3.  RAID 보호
4.  CPU 사용률 감소

**정답:** 2

### 상세 해설

STP는 스위치 간 이중 경로가 있을 때 Loop를 방지하기 위해 일부 포트를
Blocking 상태로 만든다.

------------------------------------------------------------------------

## 문제 4

L3 Switch의 가장 큰 특징은?

1.  MAC만 처리
2.  라우팅 가능
3.  VLAN 미지원
4.  DHCP 서버

**정답:** 2

### 상세 해설

L3 Switch는 IP 기반 라우팅 기능을 제공하여 VLAN 간 통신을 처리할 수
있다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   L2 = MAC
-   L3 = IP + Routing
-   VLAN = 논리적 네트워크 분리
-   Access = 1개 VLAN
-   Trunk = 여러 VLAN
-   STP = Loop 방지
-   802.1Q = VLAN Tag

------------------------------------------------------------------------

# Day 10 예고

-   DNS
-   DHCP
-   ARP
-   ICMP
-   NAT 심화
-   종합 네트워크 문제
