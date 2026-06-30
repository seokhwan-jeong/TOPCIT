# 📘 TOPCIT MasterBook 2026

# Day 27 - 소프트웨어 보안 · OWASP Top 10 · SQL Injection · XSS · CSRF · Authentication · Authorization

> **난이도** ⭐⭐⭐⭐⭐ **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐ **실무 중요도**
> ⭐⭐⭐⭐⭐ **예상 학습시간** 140분

------------------------------------------------------------------------

# 학습 목표

-   소프트웨어 보안의 중요성을 이해한다.
-   OWASP Top 10의 주요 취약점을 설명할 수 있다.
-   SQL Injection, XSS, CSRF 공격과 대응 방안을 이해한다.
-   인증(Authentication)과 인가(Authorization)의 차이를 설명할 수 있다.
-   안전한 보안 코딩 원칙을 이해한다.

------------------------------------------------------------------------

# 1. 소프트웨어 보안

보안은 기밀성(Confidentiality), 무결성(Integrity),
가용성(Availability)을 보장하기 위한 활동이다.

``` text
사용자
  │
인증(Authentication)
  │
인가(Authorization)
  │
서비스 접근
```

------------------------------------------------------------------------

# 2. OWASP Top 10

대표 웹 보안 취약점

  항목                                       설명
  ------------------------------------------ --------------------
  Broken Access Control                      접근제어 실패
  Cryptographic Failures                     암호화 오류
  Injection                                  SQL Injection 등
  Insecure Design                            안전하지 않은 설계
  Security Misconfiguration                  잘못된 설정
  Vulnerable Components                      취약 라이브러리
  Identification & Authentication Failures   인증 실패
  Software & Data Integrity Failures         무결성 문제
  Logging & Monitoring Failures              로깅 부족
  SSRF                                       서버측 요청 위조

------------------------------------------------------------------------

# 3. SQL Injection

공격자가 SQL 문장을 삽입하여 DB를 조작하는 공격이다.

취약 예

``` sql
SELECT * FROM user
WHERE id='admin'
AND pw='1234';
```

대응

-   Prepared Statement
-   ORM 사용
-   입력값 검증
-   최소 권한

------------------------------------------------------------------------

# 4. XSS(Cross Site Scripting)

악성 스크립트를 브라우저에서 실행시키는 공격이다.

종류

-   Stored XSS
-   Reflected XSS
-   DOM XSS

대응

-   HTML Escape
-   입력 검증
-   CSP(Content Security Policy)

------------------------------------------------------------------------

# 5. CSRF

사용자의 인증 정보를 악용하여 의도하지 않은 요청을 수행하게 하는
공격이다.

대응

-   CSRF Token
-   SameSite Cookie
-   Referer/Origin 검증

------------------------------------------------------------------------

# 6. Authentication vs Authorization

  항목   Authentication   Authorization
  ------ ---------------- ------------------
  의미   신원 확인        권한 확인
  예     로그인           관리자 메뉴 접근

대표 기술

-   OAuth 2.0
-   OpenID Connect
-   SAML
-   JWT

------------------------------------------------------------------------

# 7. 보안 코딩 원칙

-   입력값 검증
-   출력값 인코딩
-   최소 권한
-   민감정보 암호화
-   보안 로그 기록
-   최신 패치 적용

------------------------------------------------------------------------

# 8. 실무 사례

### Spring Security

-   JWT 인증
-   Role 기반 접근 제어

### Kubernetes

-   RBAC
-   Secret
-   NetworkPolicy

### DevSecOps

-   SonarQube
-   Trivy
-   Snyk
-   OWASP Dependency Check

------------------------------------------------------------------------

# PM Note

보안 점검 순서

``` text
인증
 ↓
인가
 ↓
입력값 검증
 ↓
암호화
 ↓
로그
 ↓
취약점 점검
```

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   CIA
-   OWASP Top 10
-   SQL Injection
-   XSS
-   CSRF
-   Authentication vs Authorization

------------------------------------------------------------------------

# 예상 문제

## 문제 1

Prepared Statement가 가장 효과적인 공격은?

1.  XSS
2.  SQL Injection
3.  CSRF
4.  DDoS

**정답:** 2

### 상세 해설

Prepared Statement는 SQL과 데이터를 분리하여 SQL Injection을 효과적으로
차단한다.

------------------------------------------------------------------------

## 문제 2

Stored XSS는 어떤 공격인가?

1.  서버에 악성 스크립트를 저장해 사용자에게 전달
2.  DNS를 변조
3.  DB 암호화
4.  패킷 암호화

**정답:** 1

### 상세 해설

Stored XSS는 게시글이나 댓글 등에 스크립트를 저장하여 다른 사용자의
브라우저에서 실행되게 한다.

------------------------------------------------------------------------

## 문제 3

CSRF 방어 방법으로 가장 적절한 것은?

1.  RAID
2.  CSRF Token
3.  Bubble Sort
4.  NAT

**정답:** 2

### 상세 해설

CSRF Token은 요청이 정상 사용자로부터 생성되었는지 검증하는 대표적인
방법이다.

------------------------------------------------------------------------

## 문제 4

인가(Authorization)의 의미는?

1.  사용자 신원 확인
2.  사용자 권한 확인
3.  암호화 수행
4.  로그 삭제

**정답:** 2

### 상세 해설

인증은 '누구인가', 인가는 '무엇을 할 수 있는가'를 확인하는 과정이다.

------------------------------------------------------------------------

## 문제 5

Kubernetes에서 권한 관리를 담당하는 기능은?

1.  RBAC
2.  ReplicaSet
3.  Service
4.  ConfigMap

**정답:** 1

### 상세 해설

RBAC(Role-Based Access Control)은 사용자와 서비스 계정의 권한을 세밀하게
제어한다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   CIA = 기밀성·무결성·가용성
-   SQL Injection = Prepared Statement
-   XSS = 출력 인코딩
-   CSRF = Token
-   Authentication = 신원 확인
-   Authorization = 권한 확인

------------------------------------------------------------------------

# Day 28 예고

-   암호학 기초
-   대칭키
-   비대칭키
-   해시
-   전자서명
-   PKI
-   TLS
