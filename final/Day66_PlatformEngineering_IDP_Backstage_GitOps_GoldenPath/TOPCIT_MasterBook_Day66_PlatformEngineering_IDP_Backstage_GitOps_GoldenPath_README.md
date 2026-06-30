# 📘 TOPCIT MasterBook 2026 (V2)

# Day 66 - Platform Engineering · Internal Developer Platform(IDP) · Backstage · GitOps · Golden Path

> 목표: **TOPCIT 500점 대비**
>
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐☆ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Platform Engineering의 개념을 이해한다.
-   DevOps와 Platform Engineering의 차이를 설명할 수 있다.
-   Internal Developer Platform(IDP)의 목적을 이해한다.
-   Backstage와 GitOps 기반 플랫폼을 설명할 수 있다.
-   Golden Path와 Self-Service Infrastructure를 이해한다.

------------------------------------------------------------------------

# 1. Platform Engineering

Platform Engineering은 개발자가 인프라를 쉽게 사용할 수 있도록 표준
플랫폼을 제공하는 방법론이다.

목표 - 개발자 생산성 향상 - 운영 표준화 - 셀프서비스 환경 - 자동화

------------------------------------------------------------------------

# 2. DevOps vs Platform Engineering

  항목   DevOps           Platform Engineering
  ------ ---------------- ----------------------
  대상   개발·운영 협업   플랫폼 제공
  목적   CI/CD            개발자 경험(DX)
  핵심   자동화           표준 플랫폼

------------------------------------------------------------------------

# 3. Internal Developer Platform(IDP)

IDP는 개발자가 직접 서비스, DB, Kubernetes 등을 셀프서비스로 사용할 수
있는 플랫폼이다.

구성 - Portal - Catalog - Template - API - GitOps

------------------------------------------------------------------------

# 4. Backstage

Backstage는 개발자 포털이다.

기능 - 서비스 카탈로그 - 템플릿 생성 - API 문서 - CI/CD 연계 -
Kubernetes 연동

------------------------------------------------------------------------

# 5. GitOps Platform

``` text
Developer
   ↓
Git
   ↓
Argo CD / Flux
   ↓
Kubernetes
```

장점 - 선언형 관리 - 변경 이력 - 자동 배포

------------------------------------------------------------------------

# 6. Golden Path

Golden Path는 조직에서 권장하는 표준 개발 경로이다.

예시 - 표준 프로젝트 템플릿 - 표준 CI/CD - 표준 보안 정책

------------------------------------------------------------------------

# 7. Self-Service Infrastructure

개발자가 직접 - Namespace 생성 - DB 요청 - 인증서 발급 - API 생성

을 수행할 수 있다.

효과 - 운영 업무 감소 - 배포 속도 향상

------------------------------------------------------------------------

# 8. 실무 사례

-   Spotify Backstage
-   Argo CD GitOps
-   Terraform Self-Service
-   Kubernetes Platform
-   Azure Landing Zone

------------------------------------------------------------------------

# PM 체크리스트

-   플랫폼 표준
-   템플릿 관리
-   GitOps 정책
-   RBAC
-   비용 관리
-   운영 KPI

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   Platform = 개발 플랫폼
-   IDP = 개발자 플랫폼
-   Backstage = Portal
-   GitOps = Git 기반 운영
-   Golden Path = 표준 경로
-   Self-Service = 자동 요청

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1

개발자 포털로 가장 적합한 것은?

① Backstage ② RAID ③ DHCP ④ FTP

**정답:** ①

**해설:** Backstage는 서비스 카탈로그와 개발자 포털 기능을 제공한다.

------------------------------------------------------------------------

## 문제2

Git을 단일 진실 공급원(Source of Truth)으로 사용하는 운영 방식은?

① GitOps ② DevSecOps ③ ETL ④ VPN

**정답:** ①

**해설:** GitOps는 Git 상태와 실제 환경을 지속적으로 동기화한다.

------------------------------------------------------------------------

## 문제3

Golden Path의 목적은?

① 장애 증가 ② 개발 표준화 ③ 서버 삭제 ④ 비용 증가

**정답:** ②

------------------------------------------------------------------------

## 문제4 (시나리오)

개발자가 직접 Kubernetes Namespace를 생성하고 애플리케이션을 배포하려
한다. 가장 적합한 개념은?

① Self-Service Infrastructure ② RAID5 ③ SAN ④ MPLS

**정답:** ①

**해설:** 셀프서비스 플랫폼은 개발자가 필요한 리소스를 직접 사용할 수
있도록 한다.

------------------------------------------------------------------------

## 문제5 (시나리오)

기업이 수백 개의 마이크로서비스를 표준 방식으로 관리하려 한다. 가장
적합한 플랫폼은?

① IDP + Backstage ② FTP ③ SMB ④ DNS

**정답:** ①

**해설:** IDP와 Backstage를 통해 서비스 카탈로그와 표준 템플릿을 제공할
수 있다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   Platform = 표준
-   IDP = 개발자
-   Backstage = Portal
-   GitOps = Git
-   Golden Path = Best Practice
-   Self-Service = 자동화

------------------------------------------------------------------------

# Day 67 예고

-   FinOps
-   Cloud Cost Optimization
-   Chargeback
-   Showback
-   Tagging Strategy
-   Resource Governance
