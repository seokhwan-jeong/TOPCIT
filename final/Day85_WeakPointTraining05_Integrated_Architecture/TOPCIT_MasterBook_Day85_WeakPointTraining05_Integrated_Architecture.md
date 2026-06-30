# 📘 TOPCIT MasterBook 2026 (V3)

# Day 85 - 약점 보완 집중훈련 ⑤ (통합 아키텍처 · Kubernetes · DevSecOps · AI)

> 목표: TOPCIT 500점 이상

## 핵심 요약

### Cloud Architecture

-   Well-Architected Framework
-   Multi-AZ = 고가용성
-   Multi-Region = 재해복구

### Kubernetes

-   Deployment: 무상태
-   StatefulSet: 상태 저장
-   HPA: Pod 자동 확장
-   Ingress: L7 진입점

### DevSecOps

-   SAST: 정적 분석
-   DAST: 동적 분석
-   SCA: 오픈소스 분석
-   SBOM: 공급망 보안
-   Trivy: 이미지 스캔

### AI

-   LLM
-   RAG
-   Embedding
-   Vector DB

### 운영

-   RCA
-   SLI/SLO/SLA
-   FinOps

------------------------------------------------------------------------

# 실전 문제 (20문항)

1.  Multi-AZ의 목적은? ① 고가용성 ② 장거리 DR ③ 백업 ④ VPN 정답:①

2.  Multi-Region의 목적은? ① 재해복구 ② 캐싱 ③ NAT ④ RAID 정답:①

3.  StatefulSet이 적합한 서비스는? ① DB ② 웹 프런트 ③ CDN ④ API Gateway
    정답:①

4.  HPA는 무엇을 자동 확장하는가? ① Pod ② VM ③ DB ④ VPC 정답:①

5.  Ingress는? ① HTTP/HTTPS 라우팅 ② DNS 서버 ③ 방화벽 ④ 스토리지 정답:①

6.  Trivy는? ① 컨테이너 이미지 취약점 검사 ② 로그 분석 ③ 모니터링 ④ 백업
    정답:①

7.  SCA의 목적은? ① 오픈소스 의존성 분석 ② SQL 튜닝 ③ 암호화 ④ 라우팅
    정답:①

8.  SBOM은? ① 소프트웨어 구성요소 목록 ② 백업 정책 ③ VLAN ④ API 정답:①

9.  RAG의 효과는? ① 최신 정보 기반 답변 ② CPU 절감 ③ RAID 구성 ④ ETL
    정답:①

10. Embedding은? ① 벡터 표현 ② 암호화 ③ 압축 ④ 백업 정답:①

11. Vector DB의 용도는? ① 유사도 검색 ② DNS 관리 ③ RAID 관리 ④ VM 생성
    정답:①

12. SLI는? ① 서비스 지표 ② 계약 ③ 목표 ④ 장애 정답:①

13. SLO는? ① 서비스 목표 ② 실제 장애 ③ 로그 ④ API 정답:①

14. RCA의 목적은? ① 근본 원인 분석 및 재발 방지 ② 백업 ③ 배포 ④ 테스트
    정답:①

15. Reserved Instance는? ① 장기 사용 할인 ② 단기 테스트 ③ 백업 ④ 암호화
    정답:①

16. Spot Instance 특징은? ① 저렴하지만 중단 가능 ② 항상 보장 ③ 고정요금
    ④ DR 전용 정답:①

17. Tagging Strategy의 목적은? ① 비용 추적 ② CPU 향상 ③ RAID 구성 ④ DNS
    변경 정답:①

18. GitOps 핵심은? ① Git을 Source of Truth로 사용 ② FTP 배포 ③ 수동 운영
    ④ DB 동기화 정답:①

19. Zero Trust 핵심 원칙은? ① Never Trust, Always Verify ② 내부는 무조건
    신뢰 ③ VPN만 사용 ④ 암호화 불필요 정답:①

20. 클라우드 아키텍처의 핵심 목표는? ① 가용성·확장성·보안·비용 최적화 ②
    서버 수 증가 ③ DB 삭제 ④ 회선 증설 정답:①

------------------------------------------------------------------------

# 암기노트

-   Multi-AZ=HA
-   Multi-Region=DR
-   StatefulSet=DB
-   HPA=Pod 확장
-   Trivy=이미지
-   SBOM=공급망
-   RAG=검색+생성
-   SLI=지표
-   SLO=목표
-   RI=장기 할인

# Day 86 예고

-   TOPCIT 종합 모의고사
-   계산형 + 사례형 + 의사결정형
