# 📘 TOPCIT MasterBook 2026 (V2)

# Day 38 - Kubernetes 모니터링 · Metrics Server · Prometheus · Grafana · Alertmanager · Loki · EFK

> 목표: **TOPCIT 500점 대비**\
> 난이도 ⭐⭐⭐⭐⭐ \| 출제빈도 ⭐⭐⭐⭐⭐ \| 실무 중요도 ⭐⭐⭐⭐⭐

------------------------------------------------------------------------

# 학습 목표

-   Kubernetes 모니터링 아키텍처를 이해한다.
-   Metrics Server와 Prometheus의 차이를 설명할 수 있다.
-   Grafana, Alertmanager의 역할을 설명할 수 있다.
-   로그 수집 구조(EFK, Loki)를 이해한다.
-   장애 발생 시 모니터링 데이터를 활용할 수 있다.

------------------------------------------------------------------------

# 1. 모니터링 아키텍처

``` text
Node/Pod
   │
Metrics Server
   │
Prometheus
   │
Alertmanager
   │
Grafana

Logs
 │
Fluent Bit
 │
Loki / Elasticsearch
 │
Grafana / Kibana
```

------------------------------------------------------------------------

# 2. Metrics Server

-   CPU/Memory 사용량 수집
-   HPA의 데이터 소스
-   장기 저장 기능 없음

------------------------------------------------------------------------

# 3. Prometheus

Prometheus는 시계열(Time Series) 데이터를 수집하는 대표 모니터링
도구이다.

기능

-   Pull 방식 수집
-   PromQL
-   Exporter 기반 확장

대표 Exporter

-   Node Exporter
-   kube-state-metrics
-   cAdvisor

------------------------------------------------------------------------

# 4. Grafana

Grafana는 시각화 도구이다.

-   Dashboard
-   Alert
-   다양한 Data Source 지원
-   운영 현황 시각화

------------------------------------------------------------------------

# 5. Alertmanager

역할

-   Alert 그룹화
-   중복 제거
-   Email/Slack/Webhook 알림

------------------------------------------------------------------------

# 6. 로그 관리

## EFK

-   Elasticsearch
-   Fluent Bit
-   Kibana

## Loki

-   Label 기반 로그 저장
-   Grafana와 통합
-   Elasticsearch보다 경량

------------------------------------------------------------------------

# 7. OpenTelemetry

Observability 표준

수집 대상

-   Metrics
-   Logs
-   Traces

대표 활용

-   Jaeger
-   Tempo

------------------------------------------------------------------------

# 8. 실무 사례

-   AKS Managed Prometheus
-   Azure Monitor
-   Amazon Managed Prometheus
-   Grafana Cloud
-   Loki + Promtail

------------------------------------------------------------------------

# PM 체크리스트

-   CPU/Memory 임계치
-   Disk 사용량
-   Pod Restart Count
-   CrashLoopBackOff
-   Node Ready
-   Alert 정책
-   로그 보존 기간

------------------------------------------------------------------------

# TOPCIT 핵심 암기

-   Metrics Server = HPA
-   Prometheus = 시계열
-   Grafana = 시각화
-   Alertmanager = 알림
-   Loki = 로그
-   OpenTelemetry = Observability

------------------------------------------------------------------------

# TOPCIT 실전 문제

## 문제1 (중 \| ★★★★★)

HPA가 주로 사용하는 메트릭 제공자는?

① Grafana ② Metrics Server ③ Loki ④ Kibana

**정답:** ②

**해설:** HPA는 Metrics Server가 제공하는 CPU/Memory 메트릭을 기반으로
Pod 수를 조정한다.

------------------------------------------------------------------------

## 문제2 (중 \| ★★★★★)

시계열 데이터를 저장하는 대표 도구는?

① Prometheus ② Jenkins ③ Argo CD ④ Harbor

**정답:** ①

------------------------------------------------------------------------

## 문제3 (상 \| ★★★★★)

다음 중 로그 분석 도구 조합은?

① Prometheus + Grafana ② Loki + Grafana ③ kubelet + etcd ④ Helm +
Kustomize

**정답:** ②

**해설:** Loki는 로그 저장, Grafana는 로그 조회 및 시각화를 담당한다.

------------------------------------------------------------------------

## 문제4 (상 \| ★★★★☆)

Pod 재시작 횟수가 급증했다. 가장 먼저 확인해야 할 것은?

① README ② kubectl logs ③ git status ④ DNS 레코드

**정답:** ②

**해설:** 로그를 확인하여 애플리케이션 오류, OOM, 설정 문제 등을 우선
파악한다.

------------------------------------------------------------------------

## 문제5 (시나리오 \| ★★★★★)

CPU 사용률이 95%인데 HPA가 동작하지 않는다. 가장 먼저 확인할 것은?

① Metrics Server 상태 ② Grafana 대시보드 ③ Helm 버전 ④ CoreDNS

**정답:** ①

**해설:** Metrics Server가 정상 동작하지 않으면 HPA는 메트릭을 수집하지
못한다.

------------------------------------------------------------------------

# 시험 직전 암기노트

-   Metrics Server → HPA
-   Prometheus → Metrics
-   Grafana → Dashboard
-   Alertmanager → Alert
-   Loki/EFK → Logs
-   OpenTelemetry → Metrics + Logs + Traces

------------------------------------------------------------------------

# Day 39 예고

-   Kubernetes 운영 및 장애 대응
-   ETCD Backup
-   Cluster Upgrade
-   Drain / Cordon
-   Backup & Restore
-   Troubleshooting
