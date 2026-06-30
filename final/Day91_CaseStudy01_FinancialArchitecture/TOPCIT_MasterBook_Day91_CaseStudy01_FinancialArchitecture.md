# 📘 TOPCIT MasterBook 2026 (V4)

# Day 91 - 실전 Case Study ① (차세대 금융 시스템 아키텍처)

> 목표: **TOPCIT 550\~600점**

## 실전 시나리오

A은행은 차세대 금융 플랫폼을 구축하려고 한다.

### 요구사항

-   Kubernetes 기반 Private Cloud
-   MSA 전환
-   GitOps(Argo CD)
-   AI 상담 시스템(RAG)
-   Active-Active DR
-   Zero Trust
-   DevSecOps(SAST, DAST, SCA, SBOM, Trivy)
-   OpenTelemetry + Prometheus + Grafana
-   SLA 99.95%

------------------------------------------------------------------------

# 프로젝트 과제

당신은 인프라 PM이다.

다음 사항을 판단하시오.

1.  AS-IS 분석 시 반드시 확인할 항목 3가지를 작성하시오.
2.  Active-Active를 선택해야 하는 이유를 설명하시오.
3.  RPO와 RTO 목표를 각각 제안하시오.
4.  GitOps를 적용할 때 기대 효과를 설명하시오.
5.  Kubernetes에서 StatefulSet을 사용하는 이유를 설명하시오.

------------------------------------------------------------------------

# 연계 문제 (20문항)

1.  GitOps의 Source of Truth는? ① Git Repository ② DB ③ NAS ④ DNS 정답:①

2.  Active-Active의 장점은? ① 서비스 연속성 ② 비용 증가만 ③ 백업 전용 ④
    테스트 전용 정답:①

3.  RAG의 핵심 구성요소가 아닌 것은? ① Retriever ② Generator ③ Vector DB
    ④ RAID Controller 정답:④

4.  SCA의 목적은? ① 오픈소스 취약점 분석 ② 이미지 스캔 ③ 로그 수집 ④ DB
    튜닝 정답:①

5.  Trivy는? ① 컨테이너 이미지 취약점 검사 ② 모니터링 ③ CI 서버 ④ DNS
    정답:①

6.  OpenTelemetry는? ① Distributed Tracing ② Backup ③ VPN ④ RAID 정답:①

7.  Prometheus의 역할은? ① Metrics 수집 ② 로그 분석 ③ 배포 자동화 ④
    암호화 정답:①

8.  Grafana의 역할은? ① Dashboard ② Build ③ Storage ④ Firewall 정답:①

9.  Error Budget = ? ① 100%-SLO ② EV/PV ③ EV/AC ④ BAC/CPI 정답:①

10. Zero Trust 핵심은? ① Never Trust, Always Verify ② 내부는 항상 신뢰 ③
    VPN만 사용 ④ 방화벽 제거 정답:①

11. Ingress는? ① L7 진입점 ② DB 복제 ③ Pod 생성 ④ Secret 저장 정답:①

12. HPA는? ① Pod 자동 확장 ② Node 자동 확장 ③ DB 확장 ④ VPC 확장 정답:①

13. Cluster Autoscaler는? ① Node 자동 확장 ② Pod 자동 확장 ③ 로그 저장 ④
    API 관리 정답:①

14. SPI\<1 의미는? ① 일정 지연 ② 일정 양호 ③ 비용 절감 ④ 품질 향상
    정답:①

15. CPI\>1 의미는? ① 비용 효율 양호 ② 비용 초과 ③ 일정 지연 ④ 장애
    정답:①

16. Data Lineage는? ① 데이터 흐름 추적 ② 데이터 삭제 ③ 백업 ④ 암호화
    정답:①

17. EA의 핵심은? ① Business-IT Alignment ② CPU 향상 ③ 메모리 증설 ④ RAID
    정답:①

18. FinOps의 핵심은? ① 비용 최적화 ② 서버 증설 ③ 로그 삭제 ④ 암호화
    정답:①

19. RCA의 목적은? ① 재발 방지 ② 배포 ③ 테스트 ④ 백업 정답:①

20. 프로젝트 성공의 핵심은? ① 범위·일정·비용·품질 균형 ② CPU 향상 ③ NIC
    증설 ④ RAID 변경 정답:①

------------------------------------------------------------------------

# TOPCIT 고득점 포인트

-   긴 시나리오에서 요구사항을 먼저 표시한다.
-   기능보다 "왜 이 기술을 선택했는가"를 판단한다.
-   계산형은 공식보다 해석이 중요하다.
-   PM 관점(일정·비용·위험)을 함께 고려한다.

------------------------------------------------------------------------

# Day 92 예고

-   실전 Case Study ②
-   장애 분석(RCA)
-   Kubernetes 운영 사고
-   AI 운영 시나리오
