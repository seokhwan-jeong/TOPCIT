# 📘 TOPCIT MasterBook 2026 (V4)

# Day 95 - 실전 Case Study ⑤ (금융권 차세대 구축 프로젝트)

> 목표: **TOPCIT 550\~600점**

## 프로젝트 시나리오

A은행은 핵심계를 클라우드 네이티브 환경으로 전환한다.

### 요구사항

-   Kubernetes 기반 MSA
-   GitOps + Argo CD
-   API Gateway + Service Mesh
-   Active-Active DR
-   RTO 15분 / RPO 0\~5분
-   Zero Trust
-   DevSecOps
-   AI(RAG) 고객상담
-   SLA 99.99%

### 프로젝트 현황

-   일정 진척률 저하(SPI=0.88)
-   비용 증가(CPI=0.91)
-   운영 중 장애 2건 발생
-   AI 응답 지연 및 GPU 사용률 증가

------------------------------------------------------------------------

# 사례 분석 과제

1.  현재 프로젝트의 가장 큰 위험요인을 5가지 식별하시오.
2.  SPI와 CPI를 해석하고 PM의 대응 방안을 작성하시오.
3.  API Gateway와 Service Mesh를 함께 사용하는 이유를 설명하시오.
4.  Active-Active DR 채택 시 장점과 단점을 비교하시오.
5.  프로젝트 종료 후 Lessons Learned에 포함해야 할 항목을 작성하시오.

------------------------------------------------------------------------

# 연계 문제 (20문항)

1.  SPI=0.88 의미는? ① 일정 지연 ② 일정 여유 ③ 비용 절감 ④ 품질 향상
    정답:①

2.  CPI=0.91 의미는? ① 비용 초과 ② 비용 절감 ③ 일정 단축 ④ 무관 정답:①

3.  EAC 근사식은? ① BAC/CPI ② EV/PV ③ EV/AC ④ PV/AC 정답:①

4.  Active-Active의 주요 목적은? ① 무중단 서비스 ② 백업 전용 ③ 테스트 ④
    비용 절감 정답:①

5.  RPO 0\~5분 의미는? ① 데이터 손실 최소화 ② 복구시간 ③ 응답속도 ④ CPU
    사용률 정답:①

6.  API Gateway 주요 기능은? ① 인증·라우팅 ② Pod 생성 ③ DB 복제 ④ 이미지
    스캔 정답:①

7.  Service Mesh의 핵심 기능은? ① mTLS와 서비스 간 트래픽 제어 ② DNS
    관리 ③ 스토리지 관리 ④ 백업 정답:①

8.  GitOps의 Source of Truth는? ① Git Repository ② DB ③ NAS ④ Wiki
    정답:①

9.  Argo CD 역할은? ① Git과 클러스터 상태 동기화 ② CI 빌드 ③ 로그 분석 ④
    백업 정답:①

10. Trivy는? ① 컨테이너 이미지 취약점 검사 ② Dashboard ③ Tracing ④ ETL
    정답:①

11. SCA는? ① 오픈소스 취약점 분석 ② DB 튜닝 ③ 암호화 ④ VPN 정답:①

12. SBOM 목적은? ① 공급망 보안 ② RAID ③ DHCP ④ NAT 정답:①

13. Prometheus는? ① Metrics 수집 ② Build ③ Storage ④ DNS 정답:①

14. Grafana는? ① Dashboard ② Compiler ③ Firewall ④ Backup 정답:①

15. OpenTelemetry는? ① Distributed Tracing ② FTP ③ RAID ④ VLAN 정답:①

16. RAG의 핵심 효과는? ① 최신 문서 기반 정확도 향상 ② GPU 절감만 수행 ③
    로그 삭제 ④ DB 정규화 정답:①

17. Zero Trust 원칙은? ① Never Trust, Always Verify ② 내부망은 신뢰 ③
    VPN만 사용 ④ 방화벽 제거 정답:①

18. RCA의 목적은? ① 근본 원인 제거 및 재발 방지 ② 테스트 종료 ③ 배포
    자동화 ④ 로그 삭제 정답:①

19. EA 핵심은? ① Business-IT Alignment ② CPU 증설 ③ 메모리 증가 ④ 회선
    증설 정답:①

20. PM의 가장 중요한 역할은? ① 범위·일정·비용·품질 균형 관리 ② 코딩 ③ DB
    운영 ④ 장비 설치 정답:①

------------------------------------------------------------------------

## 실무 체크리스트

-   위험 등록부(Risk Register) 최신화
-   SPI/CPI 주간 점검
-   변경관리(CAB) 운영
-   DR 리허설 수행
-   SLI/SLO 모니터링
-   RCA 및 Lessons Learned 문서화

## Day 96 예고

-   공공기관 클라우드 전환 사례
-   보안·컴플라이언스
-   아키텍처 트레이드오프
