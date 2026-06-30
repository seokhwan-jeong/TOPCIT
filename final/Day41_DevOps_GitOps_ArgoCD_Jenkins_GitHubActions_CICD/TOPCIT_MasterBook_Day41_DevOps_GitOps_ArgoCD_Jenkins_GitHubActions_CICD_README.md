# 📘 TOPCIT MasterBook 2026 (V2)

# Day 41 - DevOps · GitOps · Argo CD · Flux CD · Jenkins · GitHub Actions · CI/CD

> 목표: **TOPCIT 500점 대비**\
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   DevOps와 GitOps의 차이를 이해한다.
-   CI/CD 파이프라인을 설명할 수 있다.
-   Jenkins와 GitHub Actions의 특징을 비교한다.
-   Argo CD와 Flux CD의 역할을 이해한다.
-   DevSecOps의 개념을 설명할 수 있다.

------------------------------------------------------------------------

# 1. DevOps

DevOps는 개발(Dev)과 운영(Ops)의 협업 문화를 통해 빠르고 안정적인
서비스를 제공하는 방식이다.

``` text
Plan → Code → Build → Test → Release → Deploy → Operate → Monitor
```

핵심 가치 - 자동화 - 협업 - 빠른 피드백 - 지속적 개선

------------------------------------------------------------------------

# 2. GitOps

Git 저장소를 **Single Source of Truth**로 사용하는 운영 방식이다.

``` text
Git Repository
      │
 Argo CD / Flux
      │
 Kubernetes Cluster
```

장점 - 선언적 관리 - 변경 이력 추적 - 자동 동기화

------------------------------------------------------------------------

# 3. CI/CD

  단계   주요 작업
  ------ --------------------------------
  CI     Build, Test, Static Analysis
  CD     Deploy, Rollback, Verification

대표 도구 - Jenkins - GitHub Actions - GitLab CI

------------------------------------------------------------------------

# 4. Jenkins vs GitHub Actions

  항목        Jenkins     GitHub Actions
  ----------- ----------- -------------------
  설치        자체 구축   GitHub 통합
  유지보수    필요        적음
  확장성      매우 높음   높음
  사용 사례   대기업 SI   클라우드 네이티브

------------------------------------------------------------------------

# 5. Argo CD / Flux CD

Argo CD - UI 제공 - Sync 상태 확인 - Rollback 지원

Flux CD - Git 중심 - 경량 - CNCF 프로젝트

------------------------------------------------------------------------

# 6. DevSecOps

CI/CD 단계마다 보안을 통합한다.

도구 - SonarQube - Trivy - Snyk - OWASP Dependency Check

------------------------------------------------------------------------

# 7. 실무 사례

GitHub Push ↓ GitHub Actions ↓ Docker Build ↓ ACR/ECR ↓ Argo CD ↓
AKS/EKS 배포

------------------------------------------------------------------------

# PM 체크리스트

-   Branch 전략
-   PR Review
-   Pipeline 실패 알림
-   이미지 취약점 검사
-   Rollback 절차
-   Secret 관리

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   DevOps = 문화 + 자동화
-   GitOps = Git 중심 운영
-   CI = Build/Test
-   CD = Deploy
-   Argo CD = GitOps
-   Jenkins = Pipeline
-   GitHub Actions = GitHub CI/CD

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중 \| ★★★★★)

GitOps의 Single Source of Truth는?

① Kubernetes ② Docker Hub ③ Git Repository ④ Prometheus

**정답: ③**

**해설:** Git 저장소의 선언적 설정을 기준으로 클러스터 상태를 유지한다.

------------------------------------------------------------------------

## 문제2 (상 \| ★★★★★)

CI 단계의 대표 작업은?

① 운영 모니터링 ② 코드 빌드 및 테스트 ③ 장애 복구 ④ 백업

**정답: ②**

------------------------------------------------------------------------

## 문제3 (상 \| ★★★★★)

Git 변경 내용을 자동으로 Kubernetes와 동기화하는 도구는?

① Grafana ② Argo CD ③ Loki ④ Helm

**정답: ②**

**해설:** Argo CD는 Git 변경을 감지하여 클러스터에 자동 반영한다.

------------------------------------------------------------------------

## 문제4 (상)

컨테이너 이미지 취약점 분석 도구는?

① Trivy ② CoreDNS ③ kubelet ④ etcd

**정답: ①**

------------------------------------------------------------------------

## 문제5 (시나리오 \| ★★★★★)

배포 후 장애가 발생했다. 가장 적절한 대응은?

① Git 삭제 ② Rollback 수행 후 원인 분석 ③ ETCD 삭제 ④ Pipeline 중지

**정답: ②**

**해설:** 안정 버전으로 즉시 롤백하여 서비스 영향을 최소화한 뒤 원인을
분석한다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   DevOps = 협업
-   GitOps = Git 기반 운영
-   CI = Build/Test
-   CD = Deploy
-   Jenkins = Pipeline
-   Argo CD = GitOps
-   Trivy = 이미지 보안

------------------------------------------------------------------------

# Day 42 예고

-   Infrastructure as Code
-   Terraform
-   Ansible
-   CloudFormation
-   ARM/Bicep
-   Pulumi
