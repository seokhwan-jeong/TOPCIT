# 📘 TOPCIT MasterBook 2026 (V3)

# Day 79 - TOPCIT 실전 모의고사 ⑨ (의사결정형 · 아키텍처 분석)

> 목표: **TOPCIT 500점 이상 실전 대비**

## 응시 가이드

-   권장 시간: 90분
-   목표: 17문항 이상 정답

------------------------------------------------------------------------

# 통합 시나리오

한 금융기관이 차세대 시스템을 구축하면서 다음 요구사항을 제시하였다.

-   Kubernetes 기반 Private Cloud
-   GitOps + Argo CD
-   AI(RAG) 상담 시스템
-   Active-Active DR
-   Zero Trust
-   DevSecOps(SBOM, SCA, 이미지 스캔)
-   Prometheus/Grafana
-   FinOps 운영

------------------------------------------------------------------------

# 실전 문제 (20문항)

1.  아키텍처 수립 전 가장 먼저 수행해야 하는 작업은? ① AS-IS 분석 ②
    Failover ③ 모의해킹 ④ 운영 종료 **정답:** ①

2.  GitOps에서 실제 환경과 Git 상태를 동기화하는 도구는? ① Argo CD ②
    Jenkins ③ Nexus ④ Maven **정답:** ①

3.  외부 HTTPS 트래픽을 Kubernetes 서비스로 전달하는 리소스는? ① Ingress
    ② ConfigMap ③ Secret ④ PVC **정답:** ①

4.  컨테이너 이미지 취약점 점검 도구는? ① Trivy ② SonarQube ③ Grafana ④
    Helm **정답:** ①

5.  SBOM의 주요 목적은? ① 소프트웨어 구성요소 식별 및 공급망 보안 강화 ②
    DB 성능 향상 ③ 로그 압축 ④ 백업 자동화 **정답:** ①

6.  최신 사내 규정을 반영한 AI 답변을 위해 가장 효과적인 방법은? ① RAG +
    최신 문서 색인 ② GPU 증설 ③ CPU 증설 ④ Scale Up **정답:** ①

7.  서비스 간 암호화와 트래픽 제어를 제공하는 기술은? ① Service Mesh ②
    FTP ③ NAT ④ VLAN **정답:** ①

8.  Prometheus 질의 언어는? ① PromQL ② SQL ③ SPL ④ KQL **정답:** ①

9.  Grafana의 핵심 기능은? ① 대시보드 시각화 ② 이미지 스캔 ③ 코드 컴파일
    ④ ETL **정답:** ①

10. SLO가 99.9%라면 Error Budget은? ① 0.1% ② 1% ③ 0.01% ④ 10% **정답:**
    ①

11. 거의 무중단 서비스를 위한 DR 구성은? ① Active-Active ② Cold Site ③
    Tape Backup ④ Single Site **정답:** ①

12. RPO는 무엇을 의미하는가? ① 허용 가능한 최대 데이터 손실 시점 ② 허용
    가능한 최대 복구 시간 ③ 평균 응답시간 ④ CPU 사용률 **정답:** ①

13. 장기 운영 VM의 비용 최적화에 가장 적합한 것은? ① Reserved
    Instance/Savings Plan ② Spot만 사용 ③ VM 증설 ④ Scale Up **정답:** ①

14. 데이터의 생성부터 활용까지 흐름을 추적하는 기능은? ① Data Lineage ②
    Metadata ③ Snapshot ④ RAID **정답:** ①

15. Zero Trust의 핵심 원칙은? ① Never Trust, Always Verify ② 내부망은
    항상 신뢰 ③ VPN만 사용 ④ 방화벽 제거 **정답:** ①

16. SPI=1.08의 의미는? ① 일정이 계획보다 앞섬 ② 일정 지연 ③ 비용 초과 ④
    장애 발생 **정답:** ①

17. CPI=0.88의 의미는? ① 비용 초과 상태 ② 비용 절감 ③ 일정 단축 ④ 품질
    향상 **정답:** ①

18. API Gateway의 기능이 아닌 것은? ① 컨테이너 오케스트레이션 ② 인증 ③
    라우팅 ④ Rate Limiting **정답:** ①

19. 장애 재발 방지를 위한 근본 원인 분석 활동은? ① RCA ② SLA ③ CAB ④ PMO
    **정답:** ①

20. Enterprise Architecture의 최종 목적은? ① Business-IT Alignment ②
    서버 증설 ③ 회선 증설 ④ 스토리지 증설 **정답:** ①

------------------------------------------------------------------------

# 채점 기준

-   18\~20 : TOPCIT 550점 이상 기대
-   16\~17 : TOPCIT 500점 이상 가능
-   13\~15 : 합격권
-   12 이하 : 오답노트 중심 복습

------------------------------------------------------------------------

# 오답노트

-   틀린 번호:
-   원인:
-   복습 키워드:
-   실무 적용 사례:

------------------------------------------------------------------------

# 시험 직전 핵심 암기

-   GitOps = Git Repository
-   Argo CD = Git 동기화
-   Trivy = 이미지 스캔
-   SBOM = 공급망 보안
-   RAG = 검색 + 생성
-   Service Mesh = mTLS
-   Error Budget = 100% - SLO
-   SPI \> 1 = 일정 양호
-   CPI \< 1 = 비용 초과
-   RCA = Root Cause Analysis

------------------------------------------------------------------------

# Day 80 예고

-   TOPCIT 실전 모의고사 ⑩
-   종합 최종 리허설
-   20문항 고난도 사례형 + 계산형
