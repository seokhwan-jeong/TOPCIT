# 📘 TOPCIT MasterBook 2026 (V2)

# Day 43 - Cloud Governance · Landing Zone · FinOps · Well-Architected Framework · CAF

> 목표: **TOPCIT 500점 대비**\
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Public, Private, Hybrid, Multi Cloud를 비교한다.
-   Landing Zone의 목적을 이해한다.
-   Cloud Governance와 FinOps를 설명할 수 있다.
-   AWS Well-Architected Framework와 Azure CAF를 이해한다.
-   클라우드 운영 표준 수립 방법을 익힌다.

------------------------------------------------------------------------

# 1. 클라우드 배포 모델

  모델          특징             활용
  ------------- ---------------- ------------------
  Public        CSP 자원 공유    일반 서비스
  Private       전용 인프라      금융/공공
  Hybrid        Public+Private   단계적 전환
  Multi Cloud   다수 CSP         벤더 종속 최소화

------------------------------------------------------------------------

# 2. Landing Zone

Landing Zone은 안전하고 표준화된 클라우드 환경의 기반이다.

구성 요소

-   계정 구조
-   네트워크
-   IAM
-   보안 정책
-   로깅
-   모니터링
-   비용 관리

``` text
Organization
 ├─ Network
 ├─ Security
 ├─ Shared Services
 └─ Workloads
```

------------------------------------------------------------------------

# 3. Cloud Governance

목표

-   표준화
-   보안
-   규정 준수
-   운영 자동화

주요 항목

-   Tagging
-   Policy
-   RBAC
-   감사 로그
-   비용 관리

------------------------------------------------------------------------

# 4. FinOps

FinOps는 클라우드 비용을 지속적으로 최적화하는 운영 방식이다.

핵심 활동

-   리소스 분석
-   Rightsizing
-   예약 인스턴스
-   미사용 자원 제거
-   비용 예측

------------------------------------------------------------------------

# 5. AWS Well-Architected Framework

6대 핵심 기둥

1.  Operational Excellence
2.  Security
3.  Reliability
4.  Performance Efficiency
5.  Cost Optimization
6.  Sustainability

------------------------------------------------------------------------

# 6. Azure Cloud Adoption Framework

구성

-   Strategy
-   Plan
-   Ready
-   Adopt
-   Govern
-   Manage

------------------------------------------------------------------------

# 7. 실무 사례

-   Landing Zone 기반 AKS 구축
-   Azure Policy로 리소스 표준화
-   AWS Organizations + SCP 적용
-   Terraform + Policy as Code 운영
-   FinOps 월간 비용 리포트

------------------------------------------------------------------------

# PM 체크리스트

-   Naming Rule
-   Tag 표준
-   IAM 최소 권한
-   비용 대시보드
-   백업 정책
-   DR 정책
-   운영 기준 문서

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   Landing Zone = 표준 환경
-   Governance = 통제
-   FinOps = 비용 최적화
-   WAF = AWS 설계 원칙
-   CAF = Azure 도입 프레임워크

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중 \| ★★★★★)

Landing Zone의 가장 중요한 목적은?

① VM 성능 향상 ② 표준화된 클라우드 환경 구축 ③ DB 백업 ④ DNS 관리

**정답: ②**

**해설:** Landing Zone은 보안, 네트워크, IAM 등을 표준화하여 초기 기반을
제공한다.

------------------------------------------------------------------------

## 문제2 (상 \| ★★★★★)

FinOps의 핵심 목표는?

① 코드 품질 향상 ② 비용 최적화와 가시성 확보 ③ DB 튜닝 ④ 컨테이너
오케스트레이션

**정답: ②**

------------------------------------------------------------------------

## 문제3 (상 \| ★★★★★)

다음 중 AWS Well-Architected Framework의 핵심 요소가 아닌 것은?

① Reliability ② Cost Optimization ③ Security ④ Waterfall

**정답: ④**

------------------------------------------------------------------------

## 문제4 (시나리오 \| ★★★★★)

동일한 프로젝트마다 리소스 이름과 태그가 달라 관리가 어렵다. 가장 적절한
해결 방법은?

① VM 수 증가 ② Governance 정책과 Tag 표준 수립 ③ Storage 삭제 ④ CoreDNS
재시작

**정답: ②**

------------------------------------------------------------------------

## 문제5 (시나리오 \| ★★★★★)

여러 CSP를 함께 사용해 특정 업체 의존도를 줄이려 한다. 가장 적합한
전략은?

① Public Cloud ② Private Cloud ③ Hybrid Cloud ④ Multi Cloud

**정답: ④**

**해설:** Multi Cloud는 벤더 종속을 줄이고 서비스 특성에 맞는 CSP를
선택할 수 있다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   Public = 공유
-   Private = 전용
-   Hybrid = 혼합
-   Multi = 다중 CSP
-   Landing Zone = 표준 기반
-   Governance = 정책
-   FinOps = 비용

------------------------------------------------------------------------

# Day 44 예고

-   Cloud Security
-   Shared Responsibility Model
-   IAM
-   KMS
-   CSPM
-   CWPP
-   CNAPP
