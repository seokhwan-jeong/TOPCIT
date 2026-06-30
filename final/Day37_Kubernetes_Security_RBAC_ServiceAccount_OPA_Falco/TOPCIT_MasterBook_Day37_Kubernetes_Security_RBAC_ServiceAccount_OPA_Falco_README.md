# 📘 TOPCIT MasterBook 2026 (V2)

# Day 37 - Kubernetes Security · RBAC · ServiceAccount · Admission Controller · Pod Security · OPA Gatekeeper · Falco

> 목표: **TOPCIT 500점 대비**\
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Kubernetes 보안 모델을 이해한다.
-   RBAC와 ServiceAccount의 차이를 설명한다.
-   Admission Controller의 역할을 이해한다.
-   Pod Security Standards(PSS)를 설명할 수 있다.
-   OPA Gatekeeper와 Falco의 활용 사례를 이해한다.

------------------------------------------------------------------------

# 1. Kubernetes 보안 계층

``` text
사용자
 │
Authentication
 │
Authorization(RBAC)
 │
Admission Controller
 │
API Server
 │
Pod
```

보안은 인증 → 인가 → 정책 적용의 순서로 이루어진다.

------------------------------------------------------------------------

# 2. RBAC(Role-Based Access Control)

RBAC는 사용자와 서비스 계정의 권한을 제어한다.

구성 요소

  리소스               역할
  -------------------- ------------------
  Role                 Namespace 권한
  ClusterRole          클러스터 권한
  RoleBinding          Role 연결
  ClusterRoleBinding   ClusterRole 연결

**실무 팁:** 최소 권한 원칙(Principle of Least Privilege)을 적용한다.

------------------------------------------------------------------------

# 3. ServiceAccount

Pod가 Kubernetes API에 접근할 때 사용하는 계정이다.

-   사용자 계정과 별도
-   Pod별 권한 분리
-   토큰 기반 인증

------------------------------------------------------------------------

# 4. Admission Controller

API Server 요청을 검증하고 수정한다.

대표 기능

-   정책 검증
-   리소스 기본값 설정
-   보안 규칙 적용

------------------------------------------------------------------------

# 5. Pod Security Standards

  수준         특징
  ------------ ----------------
  Privileged   제한 거의 없음
  Baseline     일반 보안 기준
  Restricted   가장 엄격

Restricted가 운영 환경에서 권장된다.

------------------------------------------------------------------------

# 6. OPA Gatekeeper

정책(Code as Policy)을 적용하는 도구이다.

활용 예

-   privileged Pod 금지
-   latest 태그 금지
-   Resource Limit 필수

------------------------------------------------------------------------

# 7. Falco

런타임 보안 모니터링 도구

탐지 예

-   Shell 실행
-   민감 파일 접근
-   권한 상승
-   비정상 프로세스

------------------------------------------------------------------------

# 8. Secret 보안

-   Secret 암호화(Encryption at Rest)
-   KMS 연동
-   External Secret
-   HashiCorp Vault

------------------------------------------------------------------------

# 실무 사례

-   AKS + Microsoft Entra ID + RBAC
-   EKS + IAM Role for Service Account(IRSA)
-   OPA 정책으로 운영 표준 강제
-   Falco로 컨테이너 이상 행위 탐지

------------------------------------------------------------------------

# PM 체크리스트

-   Cluster Admin 최소화
-   ServiceAccount 권한 점검
-   Secret 암호화
-   Audit Log 활성화
-   Pod Security 적용
-   Gatekeeper 정책 검증

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   Authentication = 신원 확인
-   RBAC = 권한
-   ServiceAccount = Pod 계정
-   Admission = 정책
-   PSS = Pod 보안
-   OPA = 정책
-   Falco = 런타임 보안

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (난이도: 중 \| 출제가능성: ★★★★★)

Pod가 Kubernetes API를 호출할 때 사용하는 계정은?

① User ② ServiceAccount ③ ConfigMap ④ Secret

**정답: ②**

**해설:** ServiceAccount는 Pod가 API Server에 인증할 때 사용하는
계정이다.

------------------------------------------------------------------------

## 문제2 (난이도: 상 \| 출제가능성: ★★★★★)

Namespace 단위 권한을 정의하는 리소스는?

① ClusterRole ② Role ③ Node ④ PVC

**정답: ②**

**해설:** Role은 Namespace 범위, ClusterRole은 클러스터 범위 권한을
정의한다.

------------------------------------------------------------------------

## 문제3 (난이도: 상)

운영 환경에서 privileged 컨테이너 실행을 차단하려고 한다. 가장 적절한
방법은?

① ConfigMap ② OPA Gatekeeper ③ Deployment ④ HPA

**정답: ②**

**해설:** Gatekeeper는 정책을 강제하여 보안 규칙 위반 리소스를 생성하지
못하게 한다.

------------------------------------------------------------------------

## 문제4 (난이도: 상)

컨테이너 내부에서 비정상적인 Shell 실행을 탐지하는 도구는?

① Helm ② Falco ③ CoreDNS ④ etcd

**정답: ②**

**해설:** Falco는 시스템 호출을 기반으로 런타임 이상 행위를 탐지한다.

------------------------------------------------------------------------

## 문제5 (시나리오형)

개발자가 실수로 ClusterRoleBinding을 통해 모든 Pod에 cluster-admin
권한을 부여했다. 가장 큰 위험은?

① 성능 저하만 발생 ② 모든 리소스에 대한 과도한 접근 권한 ③ DNS 장애 ④ PV
자동 삭제

**정답: ②**

**해설:** 최소 권한 원칙을 위반하면 클러스터 전체가 공격에 노출될 수
있다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   RBAC = Role + Binding
-   ServiceAccount = Pod 인증
-   Admission = 정책 적용
-   PSS Restricted 권장
-   OPA = 예방
-   Falco = 탐지

------------------------------------------------------------------------

# Day 38 예고

-   Kubernetes 모니터링
-   Metrics Server
-   Prometheus
-   Grafana
-   Alertmanager
-   Loki
-   EFK
