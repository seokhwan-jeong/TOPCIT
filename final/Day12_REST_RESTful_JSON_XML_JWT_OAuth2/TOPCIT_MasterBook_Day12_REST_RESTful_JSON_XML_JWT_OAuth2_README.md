# 📘 TOPCIT MasterBook 2026

# Day 12 - REST API · RESTful · JSON · XML · JWT · OAuth 2.0

> **난이도** ⭐⭐⭐⭐☆
>
> **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐
>
> **실무 중요도** ⭐⭐⭐⭐⭐
>
> **예상 학습시간** 100분

------------------------------------------------------------------------

# 학습 목표

-   REST와 RESTful API를 이해한다.
-   JSON과 XML의 차이를 설명할 수 있다.
-   JWT의 구조와 인증 방식을 이해한다.
-   OAuth 2.0 인증 흐름을 설명할 수 있다.
-   API 설계 시 고려사항을 이해한다.

------------------------------------------------------------------------

# 1. API란?

API(Application Programming Interface)는 서로 다른 시스템이 기능과
데이터를 주고받기 위한 인터페이스이다.

``` text
Client
   │ HTTP
   ▼
 REST API
   │
Business Logic
   │
Database
```

대표 사례

-   모바일 앱 ↔ 서버
-   웹 ↔ WAS
-   Kubernetes API Server
-   AWS API

------------------------------------------------------------------------

# 2. REST

REST(Representational State Transfer)는 웹 기반 API 설계 아키텍처
스타일이다.

## REST의 특징

-   Client-Server
-   Stateless
-   Cacheable
-   Uniform Interface
-   Layered System

### URI 예시

``` text
GET    /users
GET    /users/100
POST   /users
PUT    /users/100
DELETE /users/100
```

------------------------------------------------------------------------

# 3. HTTP Method와 CRUD

  Method   CRUD     의미
  -------- -------- -----------
  GET      Read     조회
  POST     Create   생성
  PUT      Update   전체 수정
  PATCH    Update   일부 수정
  DELETE   Delete   삭제

------------------------------------------------------------------------

# 4. JSON

JSON(JavaScript Object Notation)은 현재 가장 많이 사용하는 데이터 교환
형식이다.

``` json
{
  "id":100,
  "name":"Kim",
  "age":30
}
```

장점

-   가볍다.
-   사람이 읽기 쉽다.
-   파싱이 빠르다.

------------------------------------------------------------------------

# 5. XML

``` xml
<user>
  <id>100</id>
  <name>Kim</name>
</user>
```

JSON보다 표현력이 좋지만 데이터 크기가 커지는 단점이 있다.

  항목        JSON        XML
  ----------- ----------- -------------
  크기        작음        큼
  가독성      좋음        보통
  현재 활용   매우 많음   일부 시스템

------------------------------------------------------------------------

# 6. JWT(JSON Web Token)

JWT는 로그인 이후 사용자 인증 정보를 전달하는 토큰이다.

구조

``` text
Header
   .
Payload
   .
Signature
```

Payload에는 사용자 정보가 저장되지만 민감한 정보는 저장하지 않는다.

장점

-   Stateless 인증
-   서버 세션 감소
-   확장성 우수

주의사항

-   HTTPS 사용
-   만료시간(exp) 설정
-   토큰 탈취 방지

------------------------------------------------------------------------

# 7. OAuth 2.0

OAuth는 비밀번호를 공유하지 않고 제3자 서비스에 권한을 위임하는
표준이다.

대표 사례

-   Google 로그인
-   GitHub 로그인
-   Kakao 로그인

기본 흐름

``` text
User
 │
Login
 │
Authorization Server
 │
Access Token
 │
Resource Server
```

주요 용어

  용어                   설명
  ---------------------- --------------
  Resource Owner         사용자
  Client                 애플리케이션
  Authorization Server   인증 서버
  Resource Server        API 서버

------------------------------------------------------------------------

# 8. REST API 설계 원칙

좋은 URI 예

``` text
/users
/orders
/products/10
```

좋지 않은 예

``` text
/getUser
/createUser
/deleteUser
```

URI는 **명사**, 행위는 **HTTP Method**로 표현한다.

------------------------------------------------------------------------

# 9. 실무 사례

## Kubernetes

-   Kubernetes API Server는 REST API 기반이다.
-   kubectl 명령은 API Server와 통신한다.

## AWS

-   대부분의 AWS 서비스는 REST API 제공
-   IAM + OAuth 기반 인증 연계 가능

## 기업 시스템

-   MSA 간 통신
-   OpenAPI(Swagger)
-   API Gateway

------------------------------------------------------------------------

# PM Note

API 장애 발생 시 확인 순서

``` text
DNS
 ↓
TCP
 ↓
TLS
 ↓
Load Balancer
 ↓
API Gateway
 ↓
Application
 ↓
DB
```

HTTP Status Code도 반드시 확인한다.

  코드   의미
  ------ -------------
  200    성공
  201    생성
  400    잘못된 요청
  401    인증 실패
  403    권한 없음
  404    리소스 없음
  500    서버 오류

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   REST 특징
-   HTTP Method
-   JSON vs XML
-   JWT 구조
-   OAuth 2.0
-   HTTP Status Code

------------------------------------------------------------------------

# 예상 문제

## 문제 1

REST API에서 리소스 조회에 사용하는 Method는?

1.  POST
2.  GET
3.  DELETE
4.  PATCH

**정답:** 2

### 상세 해설

GET은 데이터를 조회하는 메서드이다. POST는 생성, PUT/PATCH는 수정,
DELETE는 삭제에 사용된다.

------------------------------------------------------------------------

## 문제 2

JWT의 구성으로 올바른 것은?

1.  Header, Payload, Signature
2.  Header, Cookie, Session
3.  User, Password, Token
4.  Header, XML, JSON

**정답:** 1

### 상세 해설

JWT는 Header, Payload, Signature 세 부분으로 구성된다. Signature를 통해
위변조 여부를 검증한다.

------------------------------------------------------------------------

## 문제 3

OAuth 2.0의 가장 큰 목적은?

1.  RAID 구성
2.  비밀번호 공유 없이 권한 위임
3.  CPU 성능 향상
4.  DNS 조회

**정답:** 2

### 상세 해설

OAuth는 사용자 비밀번호를 제3자 서비스에 전달하지 않고 Access Token으로
권한을 위임한다.

------------------------------------------------------------------------

## 문제 4

JSON의 장점은?

1.  데이터가 매우 크다.
2.  XML보다 가볍고 처리 속도가 빠르다.
3.  반드시 HTML이 필요하다.
4.  Binary만 저장 가능하다.

**정답:** 2

### 상세 해설

JSON은 구조가 단순하고 데이터 크기가 작아 REST API에서 가장 많이
사용된다.

------------------------------------------------------------------------

## 문제 5

HTTP 401 상태 코드는 무엇을 의미하는가?

1.  성공
2.  인증 실패
3.  서버 오류
4.  리다이렉트

**정답:** 2

### 상세 해설

401은 인증(Authentication)이 실패한 상태이며, 403은 인증은 되었지만
권한(Authorization)이 없는 상태이다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   REST = 웹 API 설계 방식
-   URI는 명사, 행위는 HTTP Method
-   JSON \> XML(현대 API)
-   JWT = Header + Payload + Signature
-   OAuth = 권한 위임
-   401 = 인증 실패
-   403 = 권한 없음

------------------------------------------------------------------------

# Day 13 예고

-   Database 기초
-   RDBMS
-   SQL
-   JOIN
-   Index
-   Transaction
-   ACID
