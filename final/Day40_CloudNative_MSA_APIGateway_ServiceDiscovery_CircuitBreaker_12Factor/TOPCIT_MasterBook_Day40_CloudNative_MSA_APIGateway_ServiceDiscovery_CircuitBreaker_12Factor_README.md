# 📘 TOPCIT MasterBook 2026 (V2)

# Day 40 - Cloud Native Architecture · MSA · API Gateway · Service Discovery · Circuit Breaker · 12-Factor App

> 목표: **TOPCIT 500점 대비**\
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Cloud Native Architecture의 핵심 개념을 이해한다.
-   Monolith와 MSA를 비교할 수 있다.
-   API Gateway와 Service Discovery의 역할을 설명할 수 있다.
-   Resilience Pattern(Circuit Breaker, Retry 등)을 이해한다.
-   12-Factor App 원칙을 실무에 적용할 수 있다.

------------------------------------------------------------------------

# 1. Cloud Native Architecture

Cloud Native는 클라우드 환경을 최대한 활용하여 애플리케이션을
설계·배포·운영하는 방식이다.

``` text
User
  │
API Gateway
  │
Microservices
 ├─ User
 ├─ Order
 └─ Payment
  │
Kubernetes
  │
Cloud Infrastructure
```

핵심 요소

-   Container
-   Kubernetes
-   DevOps
-   CI/CD
-   Observability
-   Automation

------------------------------------------------------------------------

# 2. Monolith vs MSA

  항목        Monolith   MSA
  ----------- ---------- -------------
  배포        전체       서비스별
  장애 영향   전체       일부
  확장        전체       서비스 단위
  복잡도      낮음       높음

MSA는 확장성과 독립성이 뛰어나지만 운영 복잡성이 증가한다.

------------------------------------------------------------------------

# 3. API Gateway

역할

-   단일 진입점
-   인증/인가
-   Rate Limiting
-   Load Balancing
-   Logging

대표 제품

-   Kong
-   NGINX
-   Spring Cloud Gateway
-   APISIX

------------------------------------------------------------------------

# 4. Service Discovery

서비스 위치를 동적으로 관리한다.

대표 기술

-   Kubernetes Service
-   CoreDNS
-   Eureka
-   Consul

------------------------------------------------------------------------

# 5. Resilience Pattern

Circuit Breaker - 장애 전파 차단

Retry - 일시적 오류 재시도

Timeout - 무한 대기 방지

Bulkhead - 장애 격리

------------------------------------------------------------------------

# 6. 12-Factor App

대표 원칙

-   Codebase
-   Config
-   Backing Services
-   Build/Release/Run
-   Stateless Process
-   Logs as Event Stream

------------------------------------------------------------------------

# 7. 실무 사례

-   Spring Boot + Kubernetes 기반 MSA
-   API Gateway + OAuth2 인증
-   Istio Circuit Breaker
-   Argo CD 기반 GitOps
-   Prometheus + Grafana 관측성

------------------------------------------------------------------------

# PM 체크리스트

-   서비스 경계 정의
-   API 버전 관리
-   장애 격리 전략
-   관측성 확보
-   배포 자동화
-   비용 최적화

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   Cloud Native = Container + Kubernetes + DevOps
-   MSA = 서비스 독립
-   API Gateway = 단일 진입점
-   Service Discovery = 위치 탐색
-   Circuit Breaker = 장애 확산 방지
-   12-Factor = Cloud Native 개발 원칙

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중 \| ★★★★★)

MSA의 가장 큰 장점은?

① 모든 서비스를 동시에 배포 ② 서비스별 독립 배포와 확장 ③ DB 제거 ④ VM
제거

**정답:** ②

**해설:** MSA는 서비스별 독립 배포와 확장이 가능하여 민첩성과 확장성이
높다.

------------------------------------------------------------------------

## 문제2 (상 \| ★★★★★)

API Gateway의 주요 역할이 아닌 것은?

① 인증 ② Rate Limiting ③ 서비스 탐색 ④ 로깅

**정답:** ③

**해설:** 서비스 탐색은 Service Discovery의 역할이다.

------------------------------------------------------------------------

## 문제3 (상 \| ★★★★★)

장애 서비스로 요청이 계속 전달되는 것을 막는 패턴은?

① Retry ② Circuit Breaker ③ Rolling Update ④ ReplicaSet

**정답:** ②

**해설:** Circuit Breaker는 실패가 일정 기준을 넘으면 호출을 차단해 장애
확산을 방지한다.

------------------------------------------------------------------------

## 문제4 (상 \| ★★★★☆)

Kubernetes에서 Service Discovery를 담당하는 구성 요소는?

① CoreDNS ② kubelet ③ etcd ④ Helm

**정답:** ①

**해설:** CoreDNS는 서비스 이름을 IP로 변환한다.

------------------------------------------------------------------------

## 문제5 (시나리오 \| ★★★★★)

주문 서비스 장애가 결제 서비스까지 전파되고 있다. 가장 적절한 대응은?

① Pod 수 감소 ② Circuit Breaker 적용 ③ PVC 삭제 ④ CoreDNS 재시작

**정답:** ②

**해설:** Circuit Breaker와 Timeout을 적용하면 장애 전파를 줄이고 전체
시스템 안정성을 높일 수 있다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   MSA = 독립 배포
-   Gateway = 인증 + 라우팅
-   Discovery = 서비스 위치
-   Circuit Breaker = 장애 차단
-   Retry = 재시도
-   12-Factor = Cloud Native 원칙

------------------------------------------------------------------------

# Day 41 예고

-   DevOps 심화
-   GitOps
-   Argo CD
-   Flux CD
-   Jenkins
-   GitHub Actions
-   CI/CD Pipeline
