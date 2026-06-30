# 📘 TOPCIT MasterBook 2026

# Day 11 - HTTP · HTTPS · TLS · Web 통신 · Proxy · Load Balancer

> **난이도** ⭐⭐⭐⭐☆
>
> **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐
>
> **실무 중요도** ⭐⭐⭐⭐⭐
>
> **예상 학습시간** 100분

------------------------------------------------------------------------

# 학습 목표

-   HTTP와 HTTPS의 차이를 설명할 수 있다.
-   TLS Handshake의 기본 과정을 이해한다.
-   Proxy와 Reverse Proxy를 구분할 수 있다.
-   Load Balancer의 역할과 알고리즘을 설명할 수 있다.
-   웹 서비스 장애 분석 절차를 이해한다.

------------------------------------------------------------------------

# 1. HTTP

HTTP(HyperText Transfer Protocol)는 웹 브라우저와 웹 서버가 데이터를
주고받는 응용계층(L7) 프로토콜이다.

## 특징

-   Stateless
-   Request / Response 방식
-   기본 Port : **80**

### 주요 HTTP Method

  Method   용도
  -------- -----------
  GET      조회
  POST     생성
  PUT      수정
  PATCH    일부 수정
  DELETE   삭제

------------------------------------------------------------------------

# 2. HTTPS

HTTPS는 HTTP에 TLS(SSL)를 적용한 보안 프로토콜이다.

기본 Port는 **443**이다.

## 장점

-   데이터 암호화
-   서버 인증
-   데이터 무결성 보장

``` text
Browser
   │
 TLS
   │
HTTPS
   │
Web Server
```

------------------------------------------------------------------------

# 3. TLS Handshake

대표적인 연결 과정

``` text
ClientHello
      ↓
ServerHello
      ↓
Certificate
      ↓
Key Exchange
      ↓
Finished
```

## 인증서 검증

브라우저는 서버 인증서의

-   유효기간
-   발급기관(CA)
-   도메인 일치 여부

를 확인한 후 통신을 시작한다.

------------------------------------------------------------------------

# 4. Proxy와 Reverse Proxy

## Forward Proxy

-   사용자 앞단
-   인터넷 접근 제어
-   캐시 기능

## Reverse Proxy

-   서버 앞단
-   보안
-   SSL 종료
-   Load Balancing

대표 제품

-   Nginx
-   Apache
-   HAProxy

------------------------------------------------------------------------

# 5. Load Balancer

Load Balancer는 여러 서버로 트래픽을 분산한다.

``` text
Client
   │
Load Balancer
 ├── Web1
 ├── Web2
 └── Web3
```

### 대표 알고리즘

  알고리즘           설명
  ------------------ ---------------------
  Round Robin        순차 분배
  Least Connection   연결 수가 적은 서버
  IP Hash            클라이언트 IP 기준
  Weighted RR        가중치 기반

------------------------------------------------------------------------

# 6. Session과 Cookie

## Cookie

브라우저에 저장되는 정보

## Session

서버에 저장되는 사용자 정보

  항목        Cookie            Session
  ----------- ----------------- ---------
  저장 위치   Browser           Server
  보안        상대적으로 낮음   높음

------------------------------------------------------------------------

# 7. 실무 사례

## Kubernetes

-   Ingress Controller
-   NGINX Ingress
-   Service(L4)
-   Ingress(L7)

## AWS

-   ALB(L7)
-   NLB(L4)
-   Route53
-   ACM 인증서

## 데이터센터

-   F5 BIG-IP
-   L4/L7 Load Balancer
-   SSL Offloading

------------------------------------------------------------------------

# PM Note

웹 서비스 장애 시 확인 순서

``` text
DNS
 ↓
TCP 443
 ↓
TLS 인증서
 ↓
Load Balancer
 ↓
Reverse Proxy
 ↓
WAS
 ↓
DB
```

TLS 인증서 만료는 실제 운영 환경에서 자주 발생하는 장애 원인이다.

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   HTTP vs HTTPS
-   TLS
-   Certificate
-   Cookie vs Session
-   Proxy vs Reverse Proxy
-   Load Balancer 알고리즘

------------------------------------------------------------------------

# 예상 문제

## 문제 1

HTTP와 HTTPS의 가장 큰 차이는?

1.  HTTPS는 TCP를 사용하지 않는다.
2.  HTTPS는 TLS를 사용하여 암호화한다.
3.  HTTP는 Port가 없다.
4.  HTTPS는 DNS를 사용하지 않는다.

**정답:** 2

### 상세 해설

HTTPS는 HTTP에 TLS를 적용하여 데이터를 암호화하고 서버 인증을 제공한다.
HTTP와 HTTPS 모두 TCP를 사용한다.

------------------------------------------------------------------------

## 문제 2

HTTPS 기본 포트는?

1.  21
2.  80
3.  443
4.  8080

**정답:** 3

### 상세 해설

HTTP는 80, HTTPS는 443 포트를 기본으로 사용한다.

------------------------------------------------------------------------

## 문제 3

Reverse Proxy의 주요 역할은?

1.  RAID 구성
2.  서버 앞단에서 요청 처리 및 보호
3.  DNS 질의
4.  메모리 관리

**정답:** 2

### 상세 해설

Reverse Proxy는 서버를 직접 노출하지 않고 보안, SSL 종료, 캐싱, 부하분산
등의 기능을 제공한다.

------------------------------------------------------------------------

## 문제 4

다음 중 Load Balancer 알고리즘이 아닌 것은?

1.  Round Robin
2.  Least Connection
3.  Weighted Round Robin
4.  Page Replacement

**정답:** 4

### 상세 해설

Page Replacement는 운영체제 메모리 관리 기법이다. 나머지는 대표적인
부하분산 알고리즘이다.

------------------------------------------------------------------------

## 문제 5

Cookie보다 Session이 상대적으로 안전한 이유는?

1.  서버에 저장되기 때문이다.
2.  반드시 암호화되기 때문이다.
3.  DNS를 사용하기 때문이다.
4.  TCP를 사용하지 않기 때문이다.

**정답:** 1

### 상세 해설

Session 데이터는 서버에 저장되며 클라이언트에는 Session ID만 전달되는
경우가 일반적이므로 보안성이 높다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   HTTP = 80
-   HTTPS = 443 + TLS
-   TLS = 암호화 + 인증
-   Cookie = Browser
-   Session = Server
-   Reverse Proxy = 서버 보호
-   Load Balancer = 부하 분산

------------------------------------------------------------------------

# Day 12 예고

-   REST API
-   JSON
-   XML
-   JWT
-   OAuth 2.0
-   RESTful 설계
