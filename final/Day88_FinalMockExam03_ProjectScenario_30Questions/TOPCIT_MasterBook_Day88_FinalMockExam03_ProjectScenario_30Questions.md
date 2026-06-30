# 📘 TOPCIT MasterBook 2026 (V3)

# Day 88 - TOPCIT 종합 모의고사 ③ (프로젝트 시나리오 기반)

> 목표: TOPCIT 500\~600점

## 프로젝트 시나리오

공공기관이 AI 민원 서비스를 Kubernetes 기반 Private Cloud로 이전한다.

요구사항 - GitOps + Argo CD - Multi-Region DR - Zero Trust -
DevSecOps(SAST/DAST/SCA/SBOM/Trivy) - Prometheus/Grafana/OpenTelemetry -
FinOps - API Gateway + Service Mesh

------------------------------------------------------------------------

# 실전 문제 (30문항)

1.  TO-BE 설계 전 필수 작업은? ①AS-IS 분석 ②Failover ③운영종료 ④백업삭제
    정답:①

2.  GitOps Source of Truth는? ①Git Repository ②NAS ③DB ④DNS 정답:①

3.  Argo CD 역할은? ①Git-Cluster 동기화 ②빌드 ③백업 ④모니터링 정답:①

4.  Deployment 특징은? ①무상태 앱 ②DB 전용 ③DNS ④스토리지 정답:①

5.  StatefulSet은? ①상태 저장 앱 ②정적웹 ③API Gateway ④CDN 정답:①

6.  외부 HTTPS 진입점은? ①Ingress ②PVC ③Secret ④Node 정답:①

7.  Pod 자동확장은? ①HPA ②ReplicaSet ③CronJob ④CoreDNS 정답:①

8.  Node 자동확장은? ①Cluster Autoscaler ②kubelet ③Helm ④etcd 정답:①

9.  이미지 취약점 검사는? ①Trivy ②Grafana ③Jenkins ④Maven 정답:①

10. 오픈소스 취약점 분석은? ①SCA ②DAST ③IDS ④IPS 정답:①

11. SBOM 목적은? ①공급망 보안 ②압축 ③백업 ④DNS 정답:①

12. AI 최신 정보 반영은? ①RAG ②GPU 증설 ③RAM 증설 ④Scale Up 정답:①

13. Embedding 목적은? ①벡터화 ②암호화 ③압축 ④복제 정답:①

14. Vector DB는? ①유사도 검색 ②DNS ③FTP ④NAT 정답:①

15. Prometheus는? ①Metrics ②Tracing ③빌드 ④ETL 정답:①

16. OpenTelemetry는? ①Tracing 표준 ②DB ③VPN ④Storage 정답:①

17. Grafana는? ①Dashboard ②Firewall ③DNS ④Compiler 정답:①

18. Error Budget 공식은? ①100%-SLO ②EV/PV ③EV/AC ④BAC/CPI 정답:①

19. SLO=99.99%일 때 Error Budget은? ①0.01% ②0.1% ③1% ④10% 정답:①

20. Active-Active 목적은? ①무중단 서비스 ②백업 ③테스트 ④캐시 정답:①

21. RTO 의미는? ①최대 복구시간 ②데이터손실허용 ③응답시간 ④CPU 정답:①

22. Reserved Instance는? ①장기 할인 ②테스트 ③백업 ④로그 정답:①

23. Spot Instance는? ①저렴하지만 중단 가능 ②항상 보장 ③고정요금 ④무중단
    정답:①

24. Tagging Strategy 목적은? ①비용 추적 ②암호화 ③라우팅 ④RAID 정답:①

25. SPI=1.05는? ①일정 양호 ②일정 지연 ③비용 초과 ④품질 저하 정답:①

26. CPI=0.92는? ①비용 초과 ②비용 절감 ③일정 앞섬 ④무관 정답:①

27. RCA 목적은? ①재발 방지 ②배포 ③백업 ④증설 정답:①

28. Zero Trust 핵심은? ①Never Trust, Always Verify ②내부 신뢰 ③VPN만
    사용 ④방화벽 제거 정답:①

29. EA 목적은? ①Business-IT Alignment ②CPU 향상 ③회선 증설 ④메모리 증설
    정답:①

30. Well-Architected 핵심 요소가 아닌 것은? ①운영 우수성 ②보안 ③신뢰성
    ④플로피 디스크 정답:④

------------------------------------------------------------------------

## 채점

-   27\~30 : 550점 이상
-   24\~26 : 500점 이상
-   20\~23 : 약점 보완
-   19 이하 : 오답노트 필수

## 핵심 암기

-   GitOps=Git
-   HPA=Pod
-   Cluster Autoscaler=Node
-   RAG=검색+생성
-   OTel=Tracing
-   SPI\>1 일정 양호
-   CPI\<1 비용 초과
-   RTO=시간 / RPO=데이터

# Day 89 예고

-   최종 고난도 모의고사
-   장문 사례 + 연계 문제 + 계산형
