# 📘 TOPCIT MasterBook 2026 (V4)

# Day 98 - Ultimate Case Study ⑧ (통합 아키텍처 설계)

> 목표: TOPCIT 550\~600점

## 시나리오

금융·공공 공동 플랫폼을 구축한다.

### 요구사항

-   Hybrid + Multi Cloud
-   Kubernetes 기반 MSA
-   GitOps/Argo CD
-   API Gateway + Service Mesh
-   AI(RAG) 검색
-   Zero Trust
-   Active-Active DR
-   SLA 99.99%
-   비용 20% 절감

당신은 인프라 PM으로 최종 아키텍처를 제안한다.

## 분석 과제

1.  핵심 리스크 5가지를 식별하시오.
2.  기술 트레이드오프(Private/Public, VM/K8s)를 비교하시오.
3.  RTO 15분, RPO 5분 달성을 위한 구성안을 제안하시오.
4.  FinOps 전략 4가지를 제시하시오.
5.  운영 KPI(SLI/SLO)와 장애 대응 절차를 작성하시오.

------------------------------------------------------------------------

# 연계 문제 (20문항)

1.  Multi Cloud 주요 목적은? ① 벤더 종속성 완화 ② DB 제거 ③ VPN 제거 ④
    RAID 대체 정답:①

2.  Active-Active 핵심 장점은? ① 서비스 연속성 ② 구현 단순 ③ 비용 최소 ④
    백업 전용 정답:①

3.  RTO 의미는? ① 최대 복구시간 ② 데이터 손실 허용량 ③ 응답속도 ④ CPU
    정답:①

4.  RPO 의미는? ① 허용 데이터 손실 시점 ② 복구시간 ③ 장애횟수 ④ 메모리
    정답:①

5.  GitOps Source of Truth는? ① Git Repository ② NAS ③ DB ④ Wiki 정답:①

6.  Service Mesh 핵심은? ① mTLS·트래픽 제어 ② DNS ③ ETL ④ RAID 정답:①

7.  API Gateway 역할은? ① 인증·라우팅 ② 이미지 스캔 ③ Metrics ④ Backup
    정답:①

8.  StatefulSet 용도는? ① 상태 저장 앱 ② 정적 웹 ③ CDN ④ DHCP 정답:①

9.  HPA는? ① Pod 자동확장 ② Node 자동확장 ③ DB확장 ④ VPC생성 정답:①

10. Cluster Autoscaler는? ① Node 자동확장 ② Pod 자동확장 ③ VPN ④ DNS
    정답:①

11. Trivy는? ① 이미지 취약점 검사 ② Dashboard ③ Build ④ Compiler 정답:①

12. SBOM은? ① 공급망 보안 ② 로그관리 ③ RAID ④ NAT 정답:①

13. Prometheus는? ① Metrics 수집 ② Tracing ③ ETL ④ Backup 정답:①

14. Grafana는? ① Dashboard ② DNS ③ Firewall ④ Storage 정답:①

15. OpenTelemetry는? ① Distributed Tracing ② FTP ③ DHCP ④ Snapshot
    정답:①

16. Error Budget은? ① 100%-SLO ② EV/PV ③ EV/AC ④ BAC/CPI 정답:①

17. SPI\<1 의미는? ① 일정 지연 ② 일정 양호 ③ 비용 절감 ④ 품질 향상
    정답:①

18. CPI\>1 의미는? ① 비용 효율 양호 ② 비용 초과 ③ 일정 지연 ④ 위험 증가
    정답:①

19. RCA 목적은? ① 재발 방지 ② 서버 증설 ③ 로그 삭제 ④ 포맷 정답:①

20. EA 핵심 목표는? ① Business-IT Alignment ② CPU 증설 ③ NIC 증설 ④ RAID
    정답:①

------------------------------------------------------------------------

## 실무 체크리스트

-   요구사항 검증
-   아키텍처 리뷰
-   DR 리허설
-   보안 점검
-   성능 테스트
-   Cutover 계획
-   Rollback 검증
-   운영 인수인계

## Day99 예고

최종 Mock Interview 및 TOPCIT 종합 사례
