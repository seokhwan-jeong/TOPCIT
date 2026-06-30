# 📘 TOPCIT MasterBook 2026

# Day 10 - DNS · DHCP · ARP · ICMP · NAT 심화 · 네트워크 종합

> **난이도** ⭐⭐⭐⭐☆\
> **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐\
> **실무 중요도** ⭐⭐⭐⭐⭐\
> **예상 학습시간** 100분

------------------------------------------------------------------------

# 학습 목표

-   DNS의 동작 과정을 설명할 수 있다.
-   DHCP의 주소 할당 과정을 이해한다.
-   ARP와 ICMP의 역할을 설명할 수 있다.
-   NAT의 종류와 실무 활용을 이해한다.
-   네트워크 장애 분석 절차를 익힌다.

------------------------------------------------------------------------

# 1. DNS(Domain Name System)

DNS는 사람이 기억하기 쉬운 도메인 이름을 IP 주소로 변환하는 시스템이다.

예시

``` text
www.google.com
        │
     DNS Query
        │
142.250.x.x
```

## DNS 조회 과정

``` text
Client
  │
Local DNS
  │
Root DNS
  │
TLD DNS (.com)
  │
Authoritative DNS
  │
IP Address 반환
```

### 주요 레코드

  레코드   설명
  -------- ----------------
  A        IPv4 주소
  AAAA     IPv6 주소
  CNAME    별칭
  MX       메일 서버
  NS       네임서버
  TXT      검증/정책 정보

------------------------------------------------------------------------

# 2. DHCP(Dynamic Host Configuration Protocol)

DHCP는 IP 주소를 자동으로 할당하는 프로토콜이다.

## DORA 과정

``` text
Discover
   ↓
Offer
   ↓
Request
   ↓
Ack
```

### DHCP가 제공하는 정보

-   IP Address
-   Subnet Mask
-   Default Gateway
-   DNS Server
-   Lease Time

------------------------------------------------------------------------

# 3. ARP(Address Resolution Protocol)

ARP는 IP 주소를 MAC Address로 변환한다.

``` text
IP
 │
ARP Request
 │
ARP Reply
 │
MAC Address 확인
```

### ARP Cache 확인

Linux

``` bash
ip neigh
arp -n
```

Windows

``` powershell
arp -a
```

------------------------------------------------------------------------

# 4. ICMP

ICMP는 네트워크 상태 확인 및 오류 메시지 전달에 사용된다.

대표 명령

``` bash
ping
traceroute
```

주요 메시지

-   Echo Request
-   Echo Reply
-   Destination Unreachable
-   Time Exceeded

------------------------------------------------------------------------

# 5. NAT 심화

## Static NAT

1개의 Private IP ↔ 1개의 Public IP

## Dynamic NAT

여러 Public IP Pool 사용

## PAT(NAPT)

여러 Private IP가 하나의 Public IP를 Port 기반으로 공유

실무에서는 PAT가 가장 많이 사용된다.

------------------------------------------------------------------------

# 6. 네트워크 장애 분석 절차

``` text
Cable
 ↓
NIC
 ↓
IP
 ↓
Subnet
 ↓
Gateway
 ↓
ARP
 ↓
DNS
 ↓
Routing
 ↓
Firewall
 ↓
Application
```

### Linux 명령어

``` bash
ip addr
ip route
ping
traceroute
nslookup
dig
arp -n
netstat -an
ss -tuln
```

------------------------------------------------------------------------

# 실무 사례

## Kubernetes

-   CoreDNS 장애
-   Service DNS 조회 실패
-   Pod 간 통신 확인

## AWS

-   Route Table
-   Security Group
-   NACL
-   NAT Gateway
-   Internet Gateway

## 데이터센터

-   DNS 이중화
-   DHCP Relay
-   Anycast DNS

------------------------------------------------------------------------

# PM Note

Ping이 성공해도 서비스가 정상이라는 의미는 아니다.

반드시 확인한다.

-   DNS 조회
-   TCP Port
-   TLS 인증서
-   방화벽 정책
-   WAS 상태

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   DNS 조회 과정
-   DORA
-   ARP
-   ICMP
-   NAT 종류
-   ping과 traceroute 차이

------------------------------------------------------------------------

# 예상 문제

## 문제 1

DNS의 주요 역할은?

1.  MAC 변환
2.  도메인을 IP로 변환
3.  IP를 MAC으로 변환
4.  파일 저장

**정답:** 2

### 상세 해설

DNS는 사람이 읽기 쉬운 도메인 이름을 IP 주소로 변환한다. ARP는 IP를
MAC으로 변환하므로 혼동하지 말아야 한다.

------------------------------------------------------------------------

## 문제 2

DHCP 주소 할당 순서로 올바른 것은?

1.  Offer → Discover → Ack
2.  Discover → Offer → Request → Ack
3.  Request → Offer → Ack
4.  Ack → Discover

**정답:** 2

### 상세 해설

DORA(Discover, Offer, Request, Ack)는 DHCP의 대표적인 출제 포인트이다.

------------------------------------------------------------------------

## 문제 3

ARP의 역할은?

1.  IP를 MAC으로 변환
2.  도메인을 IP로 변환
3.  Port를 찾는다
4.  암호화한다

**정답:** 1

### 상세 해설

같은 네트워크에서 통신하려면 목적지 MAC 주소가 필요하며 ARP가 이를
조회한다.

------------------------------------------------------------------------

## 문제 4

PAT의 특징은?

1.  하나의 Private IP만 사용
2.  Port 번호를 이용해 하나의 Public IP를 공유
3.  IPv6 전용
4.  DNS를 대체

**정답:** 2

### 상세 해설

PAT(NAPT)는 가장 널리 사용되는 NAT 방식으로 공인 IP를 절약할 수 있다.

------------------------------------------------------------------------

## 문제 5

traceroute 명령의 주요 목적은?

1.  DNS 캐시 삭제
2.  목적지까지의 경로 확인
3.  RAID 상태 확인
4.  CPU 사용률 확인

**정답:** 2

### 상세 해설

traceroute는 패킷이 목적지까지 거치는 라우터(Hop)를 확인하여 라우팅
문제를 분석하는 데 사용된다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   DNS = 도메인 → IP
-   DHCP = DORA
-   ARP = IP → MAC
-   ICMP = ping, traceroute
-   PAT = 가장 많이 사용하는 NAT
-   Ping 성공 ≠ 서비스 정상

------------------------------------------------------------------------

# Day 11 예고

-   TCP/IP 종합
-   HTTP / HTTPS
-   TLS
-   Web 통신 구조
-   Proxy
-   Load Balancer
