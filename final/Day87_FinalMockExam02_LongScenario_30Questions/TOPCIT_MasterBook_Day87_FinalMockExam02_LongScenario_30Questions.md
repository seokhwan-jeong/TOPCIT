# 📘 TOPCIT MasterBook 2026 (V3)

# Day 87 - TOPCIT 종합 모의고사 ② (장문 사례형 · 계산형 심화)

> 목표: TOPCIT 500점 이상

## 시나리오

A 금융기관이 레거시 시스템을 Kubernetes 기반 Private Cloud로 전환한다.
요구사항은 GitOps, Multi-Region DR, RAG 기반 AI 상담, DevSecOps, Zero
Trust, Prometheus/Grafana 운영, FinOps 비용 최적화이다.

------------------------------------------------------------------------

## 실전 문제 (30문항)

1.  프로젝트 착수 시 가장 먼저 수행할 활동은? ① AS-IS 분석 ② DR 전환 ③
    운영 종료 ④ 백업 삭제 정답:①

2.  GitOps의 Source of Truth는? ① Git Repository ② DB ③ NAS ④ Wiki
    정답:①

3.  Argo CD의 역할은? ① Git과 클러스터 상태 동기화 ② CI 빌드 ③ DB 백업 ④
    DNS 관리 정답:①

4.  StatefulSet이 적합한 서비스는? ① DB ② 정적 웹 ③ CDN ④ API Gateway
    정답:①

5.  외부 HTTPS 진입점은? ① Ingress ② Secret ③ ConfigMap ④ PVC 정답:①

6.  HPA는 무엇을 확장하는가? ① Pod ② Node ③ DB ④ VPC 정답:①

7.  컨테이너 이미지 취약점 스캔은? ① Trivy ② Grafana ③ Jenkins ④ Nexus
    정답:①

8.  오픈소스 의존성 분석은? ① SCA ② DAST ③ IDS ④ IPS 정답:①

9.  SBOM의 목적은? ① 공급망 보안 ② DB 성능 향상 ③ 암호화 ④ 백업 정답:①

10. RAG의 핵심 효과는? ① 최신 정보 기반 응답 ② CPU 절감 ③ RAID 구성 ④
    ETL 정답:①

11. Embedding은? ① 벡터 표현 ② 암호화 ③ 압축 ④ 로그 정답:①

12. Vector DB는? ① 유사도 검색 ② DNS ③ FTP ④ RAID 정답:①

13. Prometheus는? ① Metrics 수집 ② 로그 저장 ③ 컴파일 ④ ETL 정답:①

14. Grafana는? ① Dashboard ② 이미지 스캔 ③ CI ④ VPN 정답:①

15. Error Budget은? ① 100%-SLO ② EV/PV ③ EV/AC ④ BAC/CPI 정답:①

16. SLO 99.9%의 Error Budget은? ① 0.1% ② 1% ③ 10% ④ 0.01% 정답:①

17. RPO는? ① 허용 가능한 데이터 손실 시점 ② 복구 시간 ③ 응답시간 ④ CPU
    정답:①

18. Active-Active 목적은? ① 무중단 서비스 ② 백업 ③ 테스트 ④ 캐시 정답:①

19. Reserved Instance는? ① 장기 할인 ② 단기 테스트 ③ DR ④ 백업 정답:①

20. Spot Instance 특징은? ① 저렴하지만 중단 가능 ② 항상 보장 ③ 고정요금
    ④ 무중단 정답:①

21. Tagging Strategy 목적은? ① 비용 추적 ② 암호화 ③ 라우팅 ④ RAID 정답:①

22. SPI=0.9 의미는? ① 일정 지연 ② 일정 단축 ③ 비용 절감 ④ 품질 향상
    정답:①

23. CPI=1.1 의미는? ① 비용 효율 양호 ② 비용 초과 ③ 일정 지연 ④ 위험 증가
    정답:①

24. EAC≈? ① BAC/CPI ② EV/PV ③ EV/AC ④ AC/PV 정답:①

25. Zero Trust 핵심은? ① Never Trust, Always Verify ② 내부망 신뢰 ③
    VPN만 사용 ④ 방화벽 제거 정답:①

26. Data Lineage 목적은? ① 데이터 흐름 추적 ② 로그 삭제 ③ 백업 ④ RAID
    정답:①

27. RCA 목적은? ① 근본 원인 분석 ② 테스트 자동화 ③ 배포 ④ 성능 향상
    정답:①

28. EA 핵심은? ① Business-IT Alignment ② CPU 향상 ③ 서버 증설 ④ 회선
    증설 정답:①

29. PM 성공 요소는? ① 범위·일정·비용·품질 균형 ② CPU ③ 메모리 ④ RAID
    정답:①

30. 클라우드 Well-Architected 핵심 요소가 아닌 것은? ① 비용 최적화 ②
    운영 우수성 ③ 신뢰성 ④ 플로피 디스크 정답:④

------------------------------------------------------------------------

## 채점

27\~30 : 550점 이상 24\~26 : 500점 이상 20\~23 : 보완 필요 19 이하 :
오답노트 작성

## 계산형 암기

-   SPI = EV / PV
-   CPI = EV / AC
-   EAC ≈ BAC / CPI
-   Error Budget = 100% - SLO
-   RPO = 데이터
-   RTO = 시간

# Day 88 예고

-   최상위 난이도 사례형
-   장문 프로젝트 시나리오 + 연계 문제
