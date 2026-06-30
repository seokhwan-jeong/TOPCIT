# 📘 TOPCIT MasterBook 2026

# Day 06 - TCP · UDP · 3-Way Handshake · 4-Way Handshake · Port · Socket · Flow Control · Congestion Control

> **난이도** ⭐⭐⭐⭐☆\
> **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐\
> **실무 중요도** ⭐⭐⭐⭐⭐\
> **예상 학습시간** 90분

------------------------------------------------------------------------

# 학습 목표

-   TCP와 UDP의 차이를 설명할 수 있다.
-   TCP 연결 및 종료 과정을 이해한다.
-   Port와 Socket의 개념을 구분할 수 있다.
-   Flow Control과 Congestion Control을 비교할 수 있다.
-   실무에서 TCP 장애를 분석하는 기본 절차를 이해한다.

------------------------------------------------------------------------

# 1. TCP와 UDP

TCP는 연결지향(Connection-Oriented) 프로토콜이며 신뢰성 있는 데이터
전송을 제공한다.

UDP는 비연결형(Connectionless) 프로토콜이며 빠른 전송을 제공하지만
신뢰성을 보장하지 않는다.

  항목          TCP                UDP
  ------------- ------------------ ----------------------
  연결          O                  X
  신뢰성        O                  X
  순서 보장     O                  X
  속도          상대적으로 느림    빠름
  대표 서비스   HTTP, HTTPS, SSH   DNS, VoIP, Streaming

------------------------------------------------------------------------

# 2. TCP Header 주요 필드

-   Source Port
-   Destination Port
-   Sequence Number
-   Acknowledgment Number
-   Window Size
-   Checksum
-   Flags(SYN, ACK, FIN, RST)

------------------------------------------------------------------------

# 3. TCP 3-Way Handshake

TCP 연결은 세 단계로 이루어진다.

``` text
Client                 Server

SYN  -------------------->

      <------------------- SYN + ACK

ACK  -------------------->
```

### 목적

-   연결 가능 여부 확인
-   초기 Sequence Number 동기화

------------------------------------------------------------------------

# 4. TCP 4-Way Handshake

연결 종료 과정

``` text
FIN -------------------->

     <------------------- ACK

     <------------------- FIN

ACK -------------------->
```

TIME_WAIT 상태는 지연된 패킷 처리와 안전한 연결 종료를 위해 필요하다.

------------------------------------------------------------------------

# 5. Port와 Socket

## Well-known Port

     Port 서비스
  ------- --------
    20/21 FTP
       22 SSH
       23 Telnet
       25 SMTP
       53 DNS
       80 HTTP
      110 POP3
      143 IMAP
      443 HTTPS

### Socket

Socket = IP Address + Port 번호

예시

``` text
192.168.0.10:443
```

------------------------------------------------------------------------

# 6. Flow Control

수신 측의 처리 속도를 고려하여 송신 속도를 조절한다.

대표 기법

-   Sliding Window
-   Receive Window

Flow Control의 목적은 **수신 버퍼 Overflow 방지**이다.

------------------------------------------------------------------------

# 7. Congestion Control

네트워크 혼잡을 방지하기 위한 제어 방식이다.

대표 알고리즘

-   Slow Start
-   Congestion Avoidance
-   Fast Retransmit
-   Fast Recovery

Flow Control과의 차이

  항목   Flow Control   Congestion Control
  ------ -------------- --------------------
  대상   수신자         네트워크
  목적   버퍼 보호      혼잡 방지

------------------------------------------------------------------------

# 8. 실무 사례

## TCP 연결은 되지만 서비스가 느리다

확인 순서

``` text
Ping
 ↓
DNS
 ↓
TCP 3-Way
 ↓
TLS
 ↓
Application
```

## Kubernetes

-   Service Port
-   TargetPort
-   NodePort

설정 오류 시 연결 실패가 발생할 수 있다.

------------------------------------------------------------------------

# PM Note

네트워크 장애 발생 시 다음을 함께 확인한다.

-   Port Open 여부
-   Firewall 정책
-   Routing
-   DNS
-   MTU
-   Packet Drop
-   Retransmission

Wireshark에서는 SYN 재전송이 반복되면 방화벽 또는 서버 미응답을
의심한다.

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   TCP vs UDP
-   3-Way Handshake
-   4-Way Handshake
-   TIME_WAIT
-   Well-known Port
-   Socket
-   Flow Control
-   Congestion Control

------------------------------------------------------------------------

# 예상 문제

## 문제 1

TCP가 UDP보다 신뢰성이 높은 이유는?

1.  연결 설정과 ACK를 사용한다.
2.  항상 더 빠르다.
3.  Port를 사용하지 않는다.
4.  IP 주소가 없다.

**정답:** 1

### 상세 해설

TCP는 연결 설정, 순서 보장, ACK, 재전송 기능을 제공하여 신뢰성을
보장한다. UDP는 이러한 기능이 없어 빠르지만 데이터 손실 가능성이 있다.

------------------------------------------------------------------------

## 문제 2

TCP 연결을 수립하는 절차는?

1.  FIN → ACK
2.  SYN → SYN/ACK → ACK
3.  ACK → SYN
4.  SYN → FIN

**정답:** 2

### 상세 해설

3-Way Handshake는 SYN, SYN/ACK, ACK 순으로 수행되며 양측이 통신 가능한
상태인지 확인하고 초기 Sequence Number를 동기화한다.

------------------------------------------------------------------------

## 문제 3

Flow Control의 목적은?

1.  CPU 사용률 감소
2.  수신 버퍼 Overflow 방지
3.  RAID 성능 향상
4.  DNS 캐시 생성

**정답:** 2

### 상세 해설

Flow Control은 수신 측이 처리 가능한 만큼만 데이터를 받도록 조절한다.
반면 Congestion Control은 네트워크 혼잡 자체를 방지한다.

------------------------------------------------------------------------

## 문제 4

Socket을 올바르게 표현한 것은?

1.  MAC + VLAN
2.  IP + Port
3.  DNS + IP
4.  Gateway + MTU

**정답:** 2

### 상세 해설

Socket은 통신 종단점을 의미하며 일반적으로 IP 주소와 Port 번호의
조합으로 표현한다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   TCP = 연결지향 + 신뢰성
-   UDP = 비연결 + 빠른 전송
-   3-Way = 연결 수립
-   4-Way = 연결 종료
-   Socket = IP + Port
-   Flow Control = 수신자 보호
-   Congestion Control = 네트워크 보호

------------------------------------------------------------------------

# Day 07 예고

-   IPv4
-   IPv6
-   Subnet Mask
-   CIDR
-   Public / Private IP
-   NAT
