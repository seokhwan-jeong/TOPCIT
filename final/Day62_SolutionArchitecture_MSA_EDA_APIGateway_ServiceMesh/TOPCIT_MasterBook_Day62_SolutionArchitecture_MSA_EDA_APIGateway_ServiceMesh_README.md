# 📘 TOPCIT MasterBook 2026 (V2)

# Day 62 - Solution Architecture · Infrastructure Architecture · MSA · EDA · API Gateway · Service Mesh

> 목표: **TOPCIT 500점 대비**\
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Solution Architecture와 Infrastructure Architecture를 구분한다.
-   MSA와 Monolithic의 차이를 설명한다.
-   EDA(Event-Driven Architecture)를 이해한다.
-   API Gateway와 Service Mesh의 역할을 설명한다.
-   현대 클라우드 네이티브 아키텍처를 이해한다.

------------------------------------------------------------------------

# 1. Solution Architecture

Solution Architecture는 비즈니스 요구사항을 만족하는 전체 시스템 구조를
설계한다.

구성 요소 - Application - Database - Network - Security - Integration -
Infrastructure

------------------------------------------------------------------------

# 2. Infrastructure Architecture

주요 구성

-   Compute
-   Storage
-   Network
-   Virtualization
-   Kubernetes
-   Monitoring
-   Backup / DR

설계 목표 - 고가용성 - 확장성 - 보안 - 성능

------------------------------------------------------------------------

# 3. Monolithic vs MSA

  항목          Monolithic   MSA
  ------------- ------------ ----------
  배포          전체         서비스별
  장애 영향     큼           작음
  확장성        낮음         높음
  운영 복잡도   낮음         높음

MSA는 서비스 단위로 독립 개발과 배포가 가능하다.

------------------------------------------------------------------------

# 4. Event-Driven Architecture (EDA)

``` text
Producer
   │
 Kafka / RabbitMQ
   │
Consumer
```

장점 - 비동기 처리 - 확장성 - 느슨한 결합

활용 - 주문 처리 - 결제 - 알림 서비스

------------------------------------------------------------------------

# 5. API Gateway

역할

-   인증(Authentication)
-   인가(Authorization)
-   Rate Limiting
-   Load Balancing
-   API Routing
-   Logging

대표 제품 - Kong - NGINX - Apigee

------------------------------------------------------------------------

# 6. Service Mesh

Service Mesh는 서비스 간 통신을 제어한다.

기능

-   Traffic Control
-   mTLS
-   Retry
-   Circuit Breaker
-   Observability

대표 - Istio - Linkerd

------------------------------------------------------------------------

# 7. Integration Architecture

대표 기술

-   REST API
-   gRPC
-   Kafka
-   RabbitMQ
-   ESB

선택 기준 - 실시간: REST/gRPC - 비동기: Kafka/RabbitMQ

------------------------------------------------------------------------

# 실무 사례

-   Kubernetes + Istio
-   API Gateway + OAuth2
-   Kafka 기반 이벤트 처리
-   MSA 기반 금융 시스템
-   클라우드 API 통합

------------------------------------------------------------------------

# PM 체크리스트

-   AS-IS 분석
-   TO-BE 설계
-   API 표준
-   메시징 구조
-   장애 격리
-   성능 검증

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   SA = 전체 설계
-   MSA = 독립 배포
-   EDA = 이벤트 기반
-   Gateway = API 관리
-   Mesh = 서비스 통신
-   Kafka = Event Broker

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중)

서비스를 독립적으로 배포하기 가장 적합한 구조는?

① Monolithic ② MSA ③ RAID ④ VLAN

**정답:** ②

**해설:** MSA는 서비스 단위의 독립 배포와 확장을 지원한다.

------------------------------------------------------------------------

## 문제2 (상)

서비스 간 트래픽 제어와 mTLS를 제공하는 기술은?

① API Gateway ② Service Mesh ③ DNS ④ FTP

**정답:** ②

**해설:** Service Mesh는 서비스 간 통신을 제어하고 보안을 강화한다.

------------------------------------------------------------------------

## 문제3 (상)

비동기 이벤트 처리를 위한 대표 아키텍처는?

① EDA ② MVC ③ ETL ④ RAID

**정답:** ①

------------------------------------------------------------------------

## 문제4 (시나리오)

대량 주문 이벤트를 여러 시스템에 동시에 전달해야 한다. 가장 적합한
기술은?

① Kafka ② FTP ③ SMB ④ NFS

**정답:** ①

**해설:** Kafka는 대규모 이벤트 스트리밍과 비동기 처리에 적합하다.

------------------------------------------------------------------------

## 문제5 (시나리오)

외부 API 인증, 라우팅, 호출 제한을 하나의 지점에서 처리하려면?

① API Gateway ② Database ③ Hypervisor ④ SAN

**정답:** ①

**해설:** API Gateway는 API 보안과 트래픽 제어를 중앙에서 수행한다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   MSA = 독립 배포
-   EDA = Event
-   Gateway = API
-   Mesh = Service
-   Kafka = Broker
-   Istio = Mesh

------------------------------------------------------------------------

# Day 63 예고

-   Cloud Architecture
-   Well-Architected Framework
-   High Availability
-   Scalability
-   Resilience
-   Multi Region
-   Multi Cloud
