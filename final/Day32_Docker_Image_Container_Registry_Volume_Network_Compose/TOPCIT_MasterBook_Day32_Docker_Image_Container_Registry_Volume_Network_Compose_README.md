# 📘 TOPCIT MasterBook 2026 (V2)

# Day 32 - Docker · Image · Container · Registry · Volume · Network · Docker Compose

> **목표:** TOPCIT 500점 대비\
> **난이도** ⭐⭐⭐⭐⭐ \| **출제빈도** ⭐⭐⭐⭐⭐ \| **실무 중요도**
> ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Docker의 동작 원리를 이해한다.
-   Image와 Container의 차이를 설명할 수 있다.
-   Volume과 Bind Mount를 비교할 수 있다.
-   Docker Network의 종류를 이해한다.
-   Docker Compose를 이용한 다중 컨테이너 구성을 이해한다.

------------------------------------------------------------------------

# 1. Docker란?

Docker는 애플리케이션과 실행 환경을 하나의 이미지로 패키징하여 어디서나
동일하게 실행할 수 있도록 하는 컨테이너 플랫폼이다.

``` text
Application
    │
 Docker Image
    │
 Container Runtime
    │
 Host OS
```

## 장점

-   빠른 배포
-   환경 일관성
-   높은 자원 효율
-   MSA에 적합

------------------------------------------------------------------------

# 2. Image와 Container

  항목   Image             Container
  ------ ----------------- --------------------
  의미   실행 템플릿       실행 중인 인스턴스
  변경   불변(Immutable)   상태 변경 가능
  예     Ubuntu Image      Ubuntu Container

암기: - **Image = 설계도** - **Container = 실행 객체**

------------------------------------------------------------------------

# 3. Docker Lifecycle

``` text
Dockerfile
   ↓
docker build
   ↓
Image
   ↓
docker run
   ↓
Container
```

주요 명령어

``` bash
docker build
docker images
docker ps
docker exec
docker logs
docker stop
docker rm
```

------------------------------------------------------------------------

# 4. Registry

Registry는 Docker 이미지를 저장하는 저장소이다.

대표 서비스

-   Docker Hub
-   GitHub Container Registry
-   Amazon ECR
-   Azure ACR

실무에서는 Private Registry를 많이 사용한다.

------------------------------------------------------------------------

# 5. Volume

컨테이너가 삭제되어도 데이터를 유지하기 위한 저장소이다.

  방식         특징
  ------------ -------------------------
  Volume       Docker 관리
  Bind Mount   Host 디렉터리 직접 연결
  tmpfs        메모리 저장

활용

-   Database
-   로그
-   업로드 파일

------------------------------------------------------------------------

# 6. Docker Network

대표 모드

-   Bridge
-   Host
-   Overlay
-   None

Bridge는 단일 호스트에서 가장 많이 사용된다.

------------------------------------------------------------------------

# 7. Docker Compose

여러 컨테이너를 하나의 YAML 파일로 관리한다.

예시

``` yaml
services:
  web:
    image: nginx
  db:
    image: mysql
```

활용

-   Web + WAS + DB
-   Redis
-   Kafka

------------------------------------------------------------------------

# 8. Kubernetes와 Docker

Docker는 **컨테이너 실행 플랫폼**, Kubernetes는 **컨테이너
오케스트레이션 플랫폼**이다.

``` text
Docker
   ↓
Container
   ↓
Kubernetes
   ↓
Cluster Management
```

------------------------------------------------------------------------

# 실무 사례

-   GitHub Actions → Docker Build → ACR/ECR → Kubernetes
-   Spring Boot + Redis + MySQL을 Docker Compose로 개발
-   운영 환경은 Kubernetes, 개발 환경은 Docker Compose 사용

------------------------------------------------------------------------

# PM 체크리스트

-   Image 취약점(Trivy)
-   최소 이미지 사용(Alpine)
-   Secret 분리
-   Volume 백업
-   Registry 접근 제어
-   로그 관리

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   Image ≠ Container
-   Registry = 이미지 저장소
-   Volume = 데이터 유지
-   Compose = 다중 컨테이너
-   Kubernetes \> Docker(관리)

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제 1 (중)

Docker Image의 특징은?

① 실행 중인 프로세스 ② 실행 템플릿 ③ DB 저장소 ④ VM

**정답: ②**

**해설:** Image는 Container를 생성하기 위한 읽기 전용 템플릿이다.

------------------------------------------------------------------------

## 문제 2 (중)

컨테이너 삭제 후에도 데이터를 유지하려면?

① Overlay ② Volume ③ Host Network ④ Layer Cache

**정답: ②**

**해설:** Volume은 컨테이너 생명주기와 분리되어 데이터를 보존한다.

------------------------------------------------------------------------

## 문제 3 (상)

여러 컨테이너를 하나의 설정 파일로 관리하는 기능은?

① Docker Swarm ② Docker Compose ③ Docker Buildx ④ CRI

**정답: ②**

**해설:** Compose는 YAML 기반으로 다중 컨테이너 서비스를 정의한다.

------------------------------------------------------------------------

## 문제 4 (상)

Docker Hub의 역할은?

① VM 실행 ② 이미지 저장소 ③ 로그 서버 ④ DNS 서버

**정답: ②**

**해설:** Docker Hub는 공개 Docker Registry 서비스이다.

------------------------------------------------------------------------

## 문제 5 (상)

다음 중 Kubernetes와 Docker의 관계로 가장 적절한 것은?

① Docker가 Kubernetes를 관리한다. ② Kubernetes는 컨테이너를
오케스트레이션한다. ③ 둘 다 Hypervisor이다. ④ Docker는 DBMS이다.

**정답: ②**

**해설:** Kubernetes는 여러 Docker(또는 OCI) 컨테이너를 자동
배포·확장·복구한다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   Dockerfile → build → Image → run → Container
-   Registry = Docker Hub / ECR / ACR
-   Volume = 영속성
-   Bridge = 기본 네트워크
-   Compose = 개발환경
-   Kubernetes = 운영환경

------------------------------------------------------------------------

# Day 33 예고

-   Kubernetes Architecture
-   Control Plane
-   Node
-   Pod
-   Deployment
-   Service
-   Ingress
