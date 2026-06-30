# 📘 TOPCIT MasterBook 2026 (V2)

# Day 42 - Infrastructure as Code · Terraform · Ansible · CloudFormation · Bicep · Pulumi

> 목표: **TOPCIT 500점 대비**\
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   IaC(Infrastructure as Code)의 개념과 장점을 이해한다.
-   Terraform, Ansible, CloudFormation, Bicep, Pulumi를 비교할 수 있다.
-   Terraform State와 Module의 역할을 설명할 수 있다.
-   IaC 기반 운영 자동화를 이해한다.

------------------------------------------------------------------------

# 1. IaC란?

Infrastructure as Code(IaC)는 서버, 네트워크, 스토리지 등의 인프라를
코드로 정의하고 자동으로 구축·관리하는 방식이다.

``` text
Git
 │
Terraform
 │
Cloud API
 │
Infrastructure
```

장점

-   반복 작업 자동화
-   일관된 환경 구축
-   버전 관리
-   빠른 복구

------------------------------------------------------------------------

# 2. Terraform

HashiCorp에서 개발한 대표적인 IaC 도구이다.

주요 구성

-   Provider
-   Resource
-   Variable
-   Output
-   Module

주요 명령어

``` bash
terraform init
terraform plan
terraform apply
terraform destroy
```

------------------------------------------------------------------------

# 3. Terraform State

State 파일은 실제 인프라 상태를 기록한다.

-   terraform.tfstate
-   변경 사항 추적
-   Remote Backend(S3, Azure Storage 등) 권장
-   Lock 기능으로 동시 작업 방지

------------------------------------------------------------------------

# 4. Module

Module은 재사용 가능한 IaC 템플릿이다.

예시

-   VPC Module
-   AKS/EKS Module
-   VM Module

장점

-   재사용성
-   표준화
-   유지보수 향상

------------------------------------------------------------------------

# 5. Ansible

에이전트 설치 없이 SSH/WinRM 기반으로 구성 관리와 배포를 수행한다.

활용

-   패치
-   설정 변경
-   미들웨어 설치
-   운영 자동화

------------------------------------------------------------------------

# 6. CloudFormation · Bicep · Pulumi

  도구             특징
  ---------------- ----------------------------------
  CloudFormation   AWS 전용
  ARM/Bicep        Azure 전용
  Pulumi           Python, C#, Go 등 일반 언어 지원
  Terraform        멀티 클라우드 지원

------------------------------------------------------------------------

# 7. 실무 사례

-   GitHub Actions → Terraform → Azure AKS
-   Terraform Module 기반 Landing Zone 구축
-   Ansible로 OS 및 미들웨어 표준화
-   Remote State로 팀 협업

------------------------------------------------------------------------

# PM 체크리스트

-   State 백업
-   Remote Backend 사용
-   Module 표준화
-   Secret 분리
-   Code Review
-   Drift 점검

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   IaC = 코드 기반 인프라
-   Terraform = 멀티 클라우드
-   State = 현재 상태
-   Module = 재사용
-   Ansible = 구성 관리
-   Bicep = Azure
-   CloudFormation = AWS

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중 \| ★★★★★)

Terraform에서 실제 인프라 상태를 저장하는 것은?

① Provider ② Module ③ State ④ Variable

**정답:** ③

**해설:** State는 Terraform이 관리하는 리소스의 현재 상태를 기록하며
변경 계획의 기준이 된다.

------------------------------------------------------------------------

## 문제2 (상 \| ★★★★★)

멀티 클라우드 환경에 가장 적합한 IaC 도구는?

① CloudFormation ② Bicep ③ Terraform ④ EC2

**정답:** ③

**해설:** Terraform은 AWS, Azure, GCP 등 다양한 Provider를 지원한다.

------------------------------------------------------------------------

## 문제3 (상 \| ★★★★☆)

Ansible의 가장 큰 특징은?

① Hypervisor 기능 ② Agentless 방식 ③ DBMS ④ Container Runtime

**정답:** ②

------------------------------------------------------------------------

## 문제4 (시나리오 \| ★★★★★)

여러 프로젝트에서 동일한 VPC 구성을 반복 사용한다. 가장 적절한 방법은?

① State 삭제 ② Module 생성 ③ Provider 제거 ④ Output 삭제

**정답:** ②

**해설:** Module을 활용하면 재사용성과 표준화를 동시에 확보할 수 있다.

------------------------------------------------------------------------

## 문제5 (시나리오 \| ★★★★★)

팀에서 동시에 Terraform을 실행해 State 충돌이 발생했다. 가장 적절한
해결책은?

① Local State만 사용 ② Remote Backend와 State Lock 사용 ③ Module 삭제 ④
Provider 변경

**정답:** ②

**해설:** Remote Backend와 Lock 기능을 사용하면 동시 수정으로 인한
충돌을 방지할 수 있다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   IaC = 코드로 인프라 관리
-   Terraform = Provider + State + Module
-   State = 현재 상태
-   Module = 재사용
-   Ansible = Agentless
-   CloudFormation = AWS
-   Bicep = Azure

------------------------------------------------------------------------

# Day 43 예고

-   Public / Private / Hybrid / Multi Cloud
-   Landing Zone
-   Cloud Governance
-   FinOps
-   Well-Architected Framework
