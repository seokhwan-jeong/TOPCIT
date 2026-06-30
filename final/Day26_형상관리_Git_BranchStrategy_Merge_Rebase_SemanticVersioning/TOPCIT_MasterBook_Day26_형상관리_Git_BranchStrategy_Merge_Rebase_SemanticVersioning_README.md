# 📘 TOPCIT MasterBook 2026

# Day 26 - 소프트웨어 형상관리 · Git · Branch Strategy · Merge · Conflict · Semantic Versioning

> **난이도** ⭐⭐⭐⭐☆\
> **TOPCIT 출제빈도** ⭐⭐⭐⭐⭐\
> **실무 중요도** ⭐⭐⭐⭐⭐\
> **예상 학습시간** 130분

------------------------------------------------------------------------

# 학습 목표

-   형상관리(Configuration Management)의 목적을 이해한다.
-   Git의 핵심 개념과 동작 원리를 설명할 수 있다.
-   Branch 전략을 비교할 수 있다.
-   Merge와 Rebase의 차이를 이해한다.
-   Semantic Versioning을 설명할 수 있다.

------------------------------------------------------------------------

# 1. 형상관리(Configuration Management)

형상관리는 소프트웨어 산출물의 변경을 체계적으로 관리하는 활동이다.

주요 목적

-   변경 이력 관리
-   협업 지원
-   버전 관리
-   안정적인 배포

``` text
요구사항
   ↓
소스코드
   ↓
Git Repository
   ↓
Build
   ↓
Deploy
```

------------------------------------------------------------------------

# 2. Git 기본 구조

``` text
Working Directory
      │
    git add
      ▼
Staging Area
      │
   git commit
      ▼
Local Repository
      │
   git push
      ▼
Remote Repository
```

대표 명령어

``` bash
git clone
git status
git add
git commit
git pull
git push
git branch
git merge
```

------------------------------------------------------------------------

# 3. Branch Strategy

  전략          특징            활용
  ------------- --------------- -----------------
  Git Flow      기능별 브랜치   대규모 프로젝트
  GitHub Flow   main 기반       SaaS
  Trunk-Based   짧은 브랜치     CI/CD

------------------------------------------------------------------------

# 4. Merge와 Rebase

## Merge

-   이력 보존
-   Merge Commit 생성

## Rebase

-   Commit 이력 정리
-   선형 히스토리 유지

주의: 공유 브랜치에서는 Rebase를 신중히 사용한다.

------------------------------------------------------------------------

# 5. Merge Conflict

동일 파일의 동일 영역을 여러 개발자가 수정하면 충돌이 발생한다.

해결 절차

1.  충돌 확인
2.  코드 수정
3.  테스트
4.  Commit

------------------------------------------------------------------------

# 6. Semantic Versioning

형식

``` text
MAJOR.MINOR.PATCH
```

예시

-   1.0.0
-   1.2.3
-   2.0.0

  항목    의미
  ------- --------------------
  Major   호환되지 않는 변경
  Minor   기능 추가
  Patch   버그 수정

------------------------------------------------------------------------

# 7. 실무 사례

### GitHub

-   Pull Request
-   Code Review
-   Branch Protection

### DevOps

-   GitHub Actions
-   Jenkins
-   Argo CD

### Kubernetes

GitOps 방식으로 Git 저장소를 단일 진실 공급원(Source of Truth)으로
사용한다.

------------------------------------------------------------------------

# PM Note

권장 브랜치 흐름

``` text
main
  │
develop
  ├── feature/*
  ├── release/*
  └── hotfix/*
```

------------------------------------------------------------------------

# TOPCIT 출제 포인트

-   Git Workflow
-   Branch 전략
-   Merge vs Rebase
-   Conflict
-   Semantic Versioning

------------------------------------------------------------------------

# 예상 문제

## 문제 1

Git에서 변경 내용을 임시 저장하는 영역은?

1.  Remote Repository
2.  Staging Area
3.  Branch
4.  Tag

**정답:** 2

### 해설

`git add` 명령으로 변경 내용을 Staging Area에 올린 뒤 Commit을 수행한다.

------------------------------------------------------------------------

## 문제 2

Semantic Versioning의 Patch 증가 의미는?

1.  대규모 변경
2.  신규 기능
3.  버그 수정
4.  저장소 생성

**정답:** 3

### 해설

Patch는 기존 기능을 유지하면서 버그를 수정한 경우 증가한다.

------------------------------------------------------------------------

## 문제 3

공유 브랜치에서 주의해서 사용해야 하는 기능은?

1.  Merge
2.  Rebase
3.  Clone
4.  Pull

**정답:** 2

### 해설

Rebase는 Commit 이력을 변경하므로 이미 공유된 브랜치에서는 충돌을 유발할
수 있다.

------------------------------------------------------------------------

## 문제 4

Git Flow에서 운영 배포용 브랜치는?

1.  feature
2.  develop
3.  main(master)
4.  release만

**정답:** 3

### 해설

운영에 배포되는 안정 버전은 일반적으로 main(master) 브랜치에서 관리한다.

------------------------------------------------------------------------

## 문제 5

GitHub에서 코드 검토를 위해 가장 많이 사용하는 기능은?

1.  Pull Request
2.  Fork Bomb
3.  Stash
4.  Hook

**정답:** 1

### 해설

Pull Request는 코드 리뷰와 병합 승인을 위한 핵심 기능이다.

------------------------------------------------------------------------

# 오늘의 핵심 요약

-   형상관리 = 변경 이력 관리
-   Git = 분산 버전 관리
-   Git Flow = 대규모 프로젝트
-   Merge = 이력 보존
-   Rebase = 이력 정리
-   SemVer = MAJOR.MINOR.PATCH

------------------------------------------------------------------------

# Day 27 예고

-   소프트웨어 보안
-   OWASP Top 10
-   SQL Injection
-   XSS
-   CSRF
-   인증(Authentication)
-   인가(Authorization)
