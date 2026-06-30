# 📘 TOPCIT MasterBook 2026 (V2)

# Day 64 - Observability · Monitoring · Logging · Metrics · Tracing · Prometheus · Grafana · OpenTelemetry

> 목표: **TOPCIT 500점 대비**
>
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Observability와 Monitoring의 차이를 이해한다.
-   Metrics, Logs, Traces의 역할을 설명할 수 있다.
-   Prometheus, Grafana, Alertmanager 구조를 이해한다.
-   OpenTelemetry 기반 관측 플랫폼을 설명할 수 있다.
-   Kubernetes 환경의 모니터링 아키텍처를 이해한다.

------------------------------------------------------------------------

# 1. Observability란?

Observability는 시스템 내부 상태를 외부 데이터로 추론하는 능력이다.

Monitoring은 "무슨 일이 발생했는가?"를, Observability는 "왜
발생했는가?"를 파악하는 데 초점을 둔다.

------------------------------------------------------------------------

# 2. Observability 3 Pillars

  요소      설명
  --------- -------------------------------
  Metrics   수치 데이터(CPU, Memory, TPS)
  Logs      이벤트 기록
  Traces    요청 흐름 추적

세 요소를 함께 분석하면 장애 원인(RCA)을 빠르게 찾을 수 있다.

------------------------------------------------------------------------

# 3. Golden Signals

Google SRE에서 제시한 핵심 지표

-   Latency
-   Traffic
-   Errors
-   Saturation

서비스 상태를 빠르게 판단하는 기준이다.

------------------------------------------------------------------------

# 4. RED / USE Method

RED - Rate - Errors - Duration

USE - Utilization - Saturation - Errors

RED는 서비스, USE는 인프라 모니터링에 적합하다.

------------------------------------------------------------------------

# 5. Prometheus

``` text
Exporter
    │
Prometheus
    │
Alertmanager
    │
Grafana
```

기능 - Metrics 수집 - PromQL - Alert Rule - Time Series DB

------------------------------------------------------------------------

# 6. Grafana

주요 기능

-   Dashboard
-   Alert
-   시각화
-   다중 데이터 소스

운영자가 시스템 상태를 한눈에 확인할 수 있다.

------------------------------------------------------------------------

# 7. OpenTelemetry

OpenTelemetry는 Metrics, Logs, Traces를 표준 방식으로 수집하는 오픈소스
프로젝트이다.

구성 - SDK - Collector - Exporter

장점 - 벤더 중립 - 통합 관측

------------------------------------------------------------------------

# 8. Kubernetes Monitoring

주요 구성

-   kube-state-metrics
-   node-exporter
-   cAdvisor
-   Prometheus
-   Grafana

모니터링 대상 - Node - Pod - Deployment - API Server

------------------------------------------------------------------------

# 실무 사례

-   Kubernetes 장애 분석
-   OpenTelemetry + Jaeger
-   Prometheus + Grafana 운영
-   Alertmanager Slack 연동
-   AI 추론 서버 GPU 모니터링

------------------------------------------------------------------------

# PM 체크리스트

-   SLA 지표
-   Alert 정책
-   로그 보존
-   Dashboard
-   RCA 절차
-   Capacity Trend

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   Observability = 원인 분석
-   Monitoring = 상태 확인
-   Metrics = 수치
-   Logs = 기록
-   Traces = 흐름
-   Prometheus = Metrics
-   Grafana = 시각화
-   OpenTelemetry = 표준

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중)

Observability의 3대 요소가 아닌 것은?

① Metrics ② Logs ③ Traces ④ RAID

**정답:** ④

**해설:** RAID는 스토리지 기술이며 Observability 요소가 아니다.

------------------------------------------------------------------------

## 문제2 (상)

시계열 메트릭 수집에 가장 적합한 도구는?

① Grafana ② Prometheus ③ Jenkins ④ Git

**정답:** ②

**해설:** Prometheus는 시계열 메트릭 저장과 PromQL 조회를 제공한다.

------------------------------------------------------------------------

## 문제3 (상)

분산 요청 흐름을 추적하는 데이터는?

① Metrics ② Logs ③ Traces ④ Snapshot

**정답:** ③

------------------------------------------------------------------------

## 문제4 (시나리오)

MSA 환경에서 API 호출이 어느 서비스에서 지연되는지 확인하려면?

① Distributed Tracing ② RAID10 ③ DHCP ④ FTP

**정답:** ①

**해설:** Tracing은 서비스 간 요청 경로와 지연 구간을 보여준다.

------------------------------------------------------------------------

## 문제5 (시나리오)

CPU 사용률이 95% 이상일 때 운영팀에 자동 알림을 보내려면?

① Alertmanager ② VLAN ③ SMB ④ NAT

**정답:** ①

**해설:** Alertmanager는 Prometheus 경보를 이메일, Slack 등으로
전달한다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   Metrics = 숫자
-   Logs = 기록
-   Traces = 흐름
-   RED = Rate/Errors/Duration
-   USE = Utilization/Saturation/Errors
-   Prometheus = 수집
-   Grafana = 대시보드

------------------------------------------------------------------------

# Day 65 예고

-   SRE
-   Error Budget
-   SLI / SLO / SLA
-   Incident Response
-   RCA
-   Chaos Engineering
