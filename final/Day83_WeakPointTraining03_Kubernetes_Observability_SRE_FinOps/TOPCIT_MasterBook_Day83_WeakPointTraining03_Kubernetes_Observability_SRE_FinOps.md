# 📘 TOPCIT MasterBook 2026 (V3)

# Day 83 - 약점 보완 집중훈련 ③ (Kubernetes · Observability · SRE · FinOps)

> 목표: TOPCIT 500점 이상

## 핵심 요약

### Kubernetes

-   Pod: 최소 배포 단위
-   Deployment: 무상태 앱 관리
-   StatefulSet: 상태 저장 앱
-   Service: Pod 노출
-   Ingress: HTTP/HTTPS 진입
-   ConfigMap: 일반 설정
-   Secret: 민감 정보
-   HPA: Pod 자동 확장
-   Cluster Autoscaler: 노드 자동 확장

### Observability

-   Metrics → Prometheus
-   Dashboard → Grafana
-   Traces → OpenTelemetry
-   Logs → 중앙 로그 시스템

### SRE

-   SLI: 측정 지표
-   SLO: 목표
-   SLA: 계약
-   Error Budget = 100% - SLO
-   RCA: 근본 원인 분석

### FinOps

-   Rightsizing
-   Reserved Instance
-   Savings Plan
-   Spot Instance
-   Tagging Strategy

------------------------------------------------------------------------

# 실전 문제 (20문항)

1.  상태 저장 워크로드에 적합한 리소스는? ① StatefulSet ② Deployment ③
    Job ④ DaemonSet 정답:①

2.  외부 HTTP 진입은? ① Ingress ② ConfigMap ③ Secret ④ PVC 정답:①

3.  민감정보 저장은? ① Secret ② ConfigMap ③ Service ④ Node 정답:①

4.  Pod 자동 확장은? ① HPA ② ReplicaSet ③ CronJob ④ Namespace 정답:①

5.  노드 자동 증설은? ① Cluster Autoscaler ② kubelet ③ etcd ④ CoreDNS
    정답:①

6.  Metrics 수집 도구는? ① Prometheus ② Grafana ③ Argo CD ④ Jenkins
    정답:①

7.  Dashboard는? ① Grafana ② Trivy ③ Helm ④ Nexus 정답:①

8.  Distributed Tracing 표준은? ① OpenTelemetry ② FTP ③ DNS ④ RAID
    정답:①

9.  SLI는? ① 서비스 지표 ② 계약 ③ 목표 ④ 장애 정답:①

10. SLA는? ① 고객 계약 ② 메트릭 ③ 로그 ④ API 정답:①

11. Error Budget 공식은? ① 100%-SLO ② EV/PV ③ AC/EV ④ SLA-SLI 정답:①

12. RCA 목적은? ① 재발 방지 ② 백업 ③ 증설 ④ 압축 정답:①

13. 장기 VM 비용 절감은? ① Reserved Instance ② Spot만 사용 ③ Scale Up ④
    Snapshot 정답:①

14. 유휴 자원 최적화는? ① Rightsizing ② RAID ③ NAT ④ VLAN 정답:①

15. 프로젝트별 비용 분석은? ① Tagging ② DHCP ③ FTP ④ ICMP 정답:①

16. Spot Instance 특징은? ① 저렴하지만 중단 가능 ② 항상 가용 ③ 고정요금
    ④ 백업용 정답:①

17. ConfigMap 용도는? ① 일반 설정 ② 비밀번호 ③ 인증서 ④ 토큰 정답:①

18. Deployment 특징은? ① 무상태 앱 관리 ② DB 클러스터 전용 ③ 스토리지
    생성 ④ DNS 관리 정답:①

19. Prometheus 질의 언어는? ① PromQL ② SQL ③ SPL ④ KQL 정답:①

20. FinOps 목표는? ① 비용 최적화 ② CPU 향상 ③ 메모리 증설 ④ 로그 삭제
    정답:①

------------------------------------------------------------------------

# 암기노트

-   StatefulSet=상태 저장
-   Secret=민감정보
-   HPA=Pod 확장
-   Prometheus=Metrics
-   Grafana=Dashboard
-   OTel=Tracing
-   SLO=목표
-   SLA=계약
-   RI=장기 할인
-   Spot=저렴·중단 가능

# Day 84 예고

-   프로젝트관리(PM)
-   EVM 계산
-   위험관리
-   EA 심화
-   종합 사례형 문제
