# 📘 TOPCIT MasterBook 2026 (V2)

# Day 63 - Cloud Architecture · Well-Architected Framework · HA · Scalability · Resilience · Multi-Region

> 목표: **TOPCIT 500점 대비**
>
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   클라우드 아키텍처 설계 원칙을 이해한다.
-   Well-Architected Framework의 핵심 요소를 설명한다.
-   HA, Scalability, Resilience를 구분할 수 있다.
-   Multi-AZ와 Multi-Region의 차이를 이해한다.
-   비용 최적화(FinOps)의 기본 개념을 이해한다.

------------------------------------------------------------------------

# 1. Cloud Architecture Principles

핵심 원칙

-   자동화(Automation)
-   탄력성(Elasticity)
-   확장성(Scalability)
-   가용성(Availability)
-   보안(Security)
-   관찰성(Observability)

------------------------------------------------------------------------

# 2. Well-Architected Framework

대표 6대 Pillar

  Pillar                   설명
  ------------------------ -------------
  Operational Excellence   운영 자동화
  Security                 보안
  Reliability              신뢰성
  Performance Efficiency   성능 효율
  Cost Optimization        비용 최적화
  Sustainability           지속 가능성

------------------------------------------------------------------------

# 3. High Availability

HA는 장애가 발생해도 서비스를 지속하는 구조이다.

예시

-   Active-Active
-   Active-Standby
-   Load Balancer
-   Auto Failover

------------------------------------------------------------------------

# 4. Scalability

  구분        설명
  ----------- --------------
  Scale Up    CPU/RAM 증설
  Scale Out   서버 추가

클라우드에서는 Scale Out이 일반적이다.

------------------------------------------------------------------------

# 5. Resilience & Fault Tolerance

Resilience - 장애 후 빠른 복구

Fault Tolerance - 장애 발생 중에도 서비스 지속

대표 기술 - Auto Healing - Multi-AZ - Replication

------------------------------------------------------------------------

# 6. Multi-AZ vs Multi-Region

  항목   Multi-AZ      Multi-Region
  ------ ------------- -----------------
  범위   동일 Region   다른 Region
  목적   고가용성      재해복구
  지연   낮음          상대적으로 높음

------------------------------------------------------------------------

# 7. Multi Cloud / Hybrid Cloud

Multi Cloud - 여러 CSP 사용

Hybrid Cloud - On-Prem + Cloud

장점 - 벤더 종속 감소 - 유연성 향상

------------------------------------------------------------------------

# 8. FinOps

비용 최적화 활동

-   Reserved Instance
-   Auto Scaling
-   Storage Tiering
-   미사용 자원 제거
-   비용 모니터링

------------------------------------------------------------------------

# 실무 사례

-   AWS Multi-AZ RDS
-   Azure Availability Zone
-   Kubernetes HPA
-   Active-Active 데이터센터
-   FinOps 대시보드

------------------------------------------------------------------------

# PM 체크리스트

-   SLA 목표
-   RTO/RPO
-   확장 전략
-   비용 예산
-   장애 복구 테스트
-   아키텍처 리뷰

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   HA = 고가용성
-   Scale Up = 성능 증가
-   Scale Out = 서버 증가
-   Multi-AZ = HA
-   Multi-Region = DR
-   FinOps = 비용 최적화

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1

Scale Out의 설명으로 올바른 것은?

① CPU 추가 ② 메모리 추가 ③ 서버 수 증가 ④ 디스크 포맷

**정답: ③**

**해설:** Scale Out은 여러 서버를 추가하여 처리량을 높인다.

------------------------------------------------------------------------

## 문제2

재해 복구에 가장 적합한 구조는?

① Multi-AZ ② Multi-Region ③ RAID1 ④ VLAN

**정답: ②**

**해설:** Region 전체 장애에도 대응 가능하다.

------------------------------------------------------------------------

## 문제3

Well-Architected Framework의 비용 관련 Pillar는?

① Security ② Reliability ③ Cost Optimization ④ Sustainability

**정답: ③**

------------------------------------------------------------------------

## 문제4 (시나리오)

쇼핑몰에서 블랙프라이데이 트래픽 급증에 자동 대응하려면?

① Scale Out + Auto Scaling ② 서버 종료 ③ RAID 변경 ④ DNS 삭제

**정답: ①**

**해설:** Auto Scaling은 부하에 따라 인스턴스를 자동 증감한다.

------------------------------------------------------------------------

## 문제5 (시나리오)

금융사의 DR센터를 다른 지역에 구축하려 한다. 가장 적절한 설계는?

① Single AZ ② Multi-Region Active-Standby ③ 단일 서버 ④ NAT만 추가

**정답: ②**

**해설:** 지역 단위 재해를 고려한 Multi-Region 구성이 적합하다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   HA = Availability
-   Scale Up = Vertical
-   Scale Out = Horizontal
-   Multi-AZ = HA
-   Multi-Region = DR
-   FinOps = Cost

------------------------------------------------------------------------

# Day 64 예고

-   Observability
-   Monitoring
-   Logging
-   Metrics
-   Tracing
-   Prometheus
-   Grafana
-   OpenTelemetry
