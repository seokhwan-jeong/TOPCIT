# 📘 TOPCIT MasterBook 2026

# Day 08 - Routing · Static Routing · Dynamic Routing · RIP · OSPF · BGP · Default Gateway

> **난이도** ⭐⭐⭐⭐☆\
> **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐\
> **실무 중요도** ⭐⭐⭐⭐⭐\
> **예상 학습시간** 90분

------------------------------------------------------------------------

# 학습 목표

-   라우팅의 개념을 이해한다.
-   Static Routing과 Dynamic Routing의 차이를 설명할 수 있다.
-   RIP, OSPF, BGP의 특징을 비교할 수 있다.
-   Default Gateway의 역할을 이해한다.
-   데이터센터 및 클라우드 환경의 라우팅을 이해한다.

------------------------------------------------------------------------

# 1. Routing이란?

Routing은 패킷이 목적지까지 가장 적절한 경로를 찾아 전달되는 과정이다.

``` text
PC
 │
L3 Switch
 │
Router
 │
Internet
 │
Destination
```

라우터는 **Routing Table**을 참고하여 다음 목적지(Next Hop)를 결정한다.

------------------------------------------------------------------------

# 2. Routing Table

대표 항목

  항목          설명
  ------------- -----------------
  Destination   목적지 네트워크
  Netmask       서브넷 마스크
  Gateway       다음 홉
  Interface     전송 인터페이스
  Metric        경로 비용

Linux 확인

``` bash
ip route
route -n
```

Windows 확인

``` powershell
route print
```

------------------------------------------------------------------------

# 3. Static Routing

관리자가 직접 경로를 등록하는 방식이다.

장점

-   단순
-   예측 가능
-   소규모 환경 적합

단점

-   관리 부담
-   장애 시 자동 우회 불가

예시

``` bash
ip route add 10.10.0.0/16 via 192.168.0.1
```

------------------------------------------------------------------------

# 4. Dynamic Routing

라우터들이 서로 경로 정보를 교환한다.

장점

-   자동 장애 복구
-   대규모 환경 적합

단점

-   설정 복잡
-   CPU/Memory 사용 증가

------------------------------------------------------------------------

# 5. RIP

Routing Information Protocol

특징

-   Distance Vector
-   Metric = Hop Count
-   최대 15 Hop

장점 - 간단

단점 - 대규모 환경 부적합

------------------------------------------------------------------------

# 6. OSPF

Open Shortest Path First

특징

-   Link State
-   SPF(Dijkstra) 알고리즘
-   Area 지원
-   빠른 수렴

실무에서는 기업 내부망에서 가장 많이 사용된다.

------------------------------------------------------------------------

# 7. BGP

Border Gateway Protocol

특징

-   인터넷 라우팅 표준
-   AS(Autonomous System) 기반
-   Path Vector 방식

주요 사용처

-   ISP
-   Cloud
-   대기업 WAN

------------------------------------------------------------------------

# 8. Default Gateway

같은 네트워크가 아닌 목적지로 패킷을 보낼 때 사용하는 기본 라우터이다.

``` text
PC
 │
Default Gateway
 │
Internet
```

Gateway 설정이 틀리면 인터넷 통신이 불가능할 수 있다.

------------------------------------------------------------------------

# 9. 실무 사례

## AWS

-   Route Table
-   Internet Gateway
-   NAT Gateway
-   Transit Gateway

## Kubernetes

-   CNI
-   Pod Routing
-   Service Routing

## 데이터센터

-   ECMP
-   VRRP
-   HSRP

------------------------------------------------------------------------

# PM Note

네트워크 장애 시 확인 순서

``` text
IP
 ↓
Subnet
 ↓
Gateway
 ↓
ARP
 ↓
Routing Table
 ↓
Firewall
 ↓
Application
```

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   Static vs Dynamic Routing
-   RIP
-   OSPF
-   BGP
-   Routing Table
-   Default Gateway

------------------------------------------------------------------------

# 예상 문제

## 문제 1

Dynamic Routing의 장점은?

1.  자동 경로 갱신
2.  CPU 사용 감소
3.  메모리 사용 없음
4.  설정 불필요

**정답:** 1

### 상세 해설

Dynamic Routing은 라우터 간 경로 정보를 자동으로 교환하여 장애 발생 시
우회 경로를 선택할 수 있다.

------------------------------------------------------------------------

## 문제 2

RIP의 Metric은?

1.  Delay
2.  Cost
3.  Hop Count
4.  Bandwidth

**정답:** 3

### 상세 해설

RIP는 목적지까지 거치는 라우터 수(Hop Count)를 Metric으로 사용하며 최대
15 Hop까지만 지원한다.

------------------------------------------------------------------------

## 문제 3

기업 내부망에서 가장 널리 사용되는 Dynamic Routing Protocol은?

1.  RIP
2.  OSPF
3.  ARP
4.  ICMP

**정답:** 2

### 상세 해설

OSPF는 빠른 수렴 속도와 Area 설계가 가능하여 엔터프라이즈 네트워크에서
많이 사용된다.

------------------------------------------------------------------------

## 문제 4

BGP가 주로 사용되는 환경은?

1.  개인 PC
2.  인터넷 백본 및 ISP
3.  프린터
4.  USB

**정답:** 2

### 상세 해설

BGP는 AS 간 경로를 교환하는 인터넷 표준 라우팅 프로토콜이다.

------------------------------------------------------------------------

## 문제 5

Default Gateway의 역할은?

1.  DNS 캐시 저장
2.  다른 네트워크로 패킷 전달
3.  RAID 구성
4.  CPU 제어

**정답:** 2

### 상세 해설

목적지가 자신의 네트워크에 없으면 패킷은 Default Gateway로 전달되어 다음
네트워크로 이동한다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   Routing = 최적 경로 선택
-   Static = 수동
-   Dynamic = 자동
-   RIP = Hop Count
-   OSPF = Link State
-   BGP = 인터넷 표준
-   Gateway = 다른 네트워크로 나가는 출구

------------------------------------------------------------------------

# Day 09 예고

-   L2 Switch
-   L3 Switch
-   Switching
-   VLAN
-   STP
-   Trunk
-   Access Port
