# 📘 TOPCIT MasterBook 2026 (V4)

# Day 99 - Ultimate Case Study ⑨ (최종 실전 종합 사례)

> 목표: **TOPCIT 550\~600점**

## 통합 시나리오

국가 금융·공공 공동 플랫폼 구축 프로젝트가 막바지에 접어들었다.

### 프로젝트 현황

-   Kubernetes 기반 MSA 운영
-   Hybrid + Multi Cloud
-   GitOps(Argo CD)
-   API Gateway + Service Mesh
-   AI(RAG) 민원/상담 서비스
-   Active-Active DR
-   SLA 99.99%

### 현재 발생한 문제

-   신규 배포 이후 일부 서비스 응답 지연
-   SPI = 0.92
-   CPI = 0.95
-   Error Budget 80% 소진
-   GPU 사용률 96%
-   월 클라우드 비용 25% 증가

------------------------------------------------------------------------

# 사례 분석 과제

1.  프로젝트의 기술·일정·비용 리스크를 각각 3가지 이상 식별하시오.
2.  현재 장애의 원인을 우선순위별로 분석하시오.
3.  즉시 조치와 장기 개선 대책을 구분하여 작성하시오.
4.  FinOps 관점에서 비용 절감 전략을 제안하시오.
5.  프로젝트 종료 승인 전에 반드시 확인해야 할 체크리스트를 작성하시오.

------------------------------------------------------------------------

# 연계 문제 (20문항)

1.  SPI=0.92 의미는? ① 일정 지연 ② 일정 단축 ③ 비용 절감 ④ 품질 향상
    정답:①

2.  CPI=0.95 의미는? ① 비용 초과 ② 비용 절감 ③ 일정 양호 ④ 장애 없음
    정답:①

3.  Error Budget 80% 소진 시 우선 조치는? ① 신규 기능보다 안정화 우선 ②
    기능 추가 ③ 테스트 생략 ④ 서버 축소 정답:①

4.  GitOps 롤백의 기준은? ① Git의 안정 버전으로 복원 ② 운영 서버 직접
    수정 ③ DB 삭제 ④ 로그 삭제 정답:①

5.  HPA 목적은? ① Pod 자동 확장 ② Node 자동 확장 ③ DB 확장 ④ VPC 생성
    정답:①

6.  Cluster Autoscaler 목적은? ① Node 자동 확장 ② 이미지 스캔 ③ 로그
    분석 ④ 인증 정답:①

7.  Service Mesh 핵심 기능은? ① mTLS와 트래픽 제어 ② DNS 관리 ③ ETL ④
    RAID 정답:①

8.  API Gateway 기능은? ① 인증·라우팅·Rate Limiting ② Pod 생성 ③ 백업 ④
    컴파일 정답:①

9.  RAG 정확도 향상 방법은? ① 최신 문서 재색인 ② GPU만 증설 ③ 메모리만
    증설 ④ RAID 구성 정답:①

10. Vector DB 역할은? ① 유사도 검색 ② 트랜잭션 처리 ③ DNS 관리 ④ DHCP
    정답:①

11. Trivy는? ① 컨테이너 이미지 취약점 검사 ② Dashboard ③ Tracing ④ VPN
    정답:①

12. SBOM은? ① 공급망 보안 ② 로그 관리 ③ RAID ④ NAT 정답:①

13. Prometheus는? ① Metrics 수집 ② Build ③ Storage ④ Compiler 정답:①

14. Grafana는? ① Dashboard ② Firewall ③ DNS ④ Snapshot 정답:①

15. OpenTelemetry는? ① Distributed Tracing ② FTP ③ VLAN ④ Backup 정답:①

16. Active-Active 목적은? ① 서비스 연속성 ② 비용 절감만 ③ 백업만 ④
    테스트 정답:①

17. Zero Trust 핵심은? ① Never Trust, Always Verify ② 내부는 신뢰 ③
    VPN만 사용 ④ 암호화 불필요 정답:①

18. RCA의 최종 목적은? ① 재발 방지 ② 서버 교체 ③ 로그 삭제 ④ 성능 측정
    정답:①

19. EA 핵심 목표는? ① Business-IT Alignment ② CPU 증설 ③ NIC 교체 ④ RAID
    구성 정답:①

20. 인프라 PM의 최우선 역할은? ① 범위·일정·비용·품질·위험을 균형 있게
    관리 ② 직접 코딩 ③ DB 개발 ④ 장비 설치 정답:①

------------------------------------------------------------------------

# 최종 실무 체크리스트

-   □ 요구사항 충족 여부
-   □ 성능 테스트 완료
-   □ 보안 취약점 조치 완료
-   □ DR 리허설 완료
-   □ GitOps Rollback 검증
-   □ 운영 인수인계 완료
-   □ Lessons Learned 작성
-   □ 운영 승인(Cutover Sign-off)

# Day 100 예고

-   최종 리마인드
-   TOPCIT 핵심 100개 정리
-   시험 직전 체크리스트
-   실전 전략 및 시간 관리
