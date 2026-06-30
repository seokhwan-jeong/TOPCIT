# 📘 TOPCIT MasterBook 2026 (V3)

# Day 89 - TOPCIT 최상위 모의고사 ④ (프로젝트 의사결정형)

> 목표: TOPCIT 550\~600점

## 장문 시나리오

금융권 차세대 프로젝트에서 다음 요구사항이 제시되었다.

-   Kubernetes 기반 Private Cloud
-   GitOps + Argo CD
-   Active-Active DR
-   Zero Trust
-   DevSecOps(SAST, DAST, SCA, SBOM, Trivy)
-   AI 상담 시스템(RAG)
-   OpenTelemetry + Prometheus + Grafana
-   FinOps 비용 최적화
-   24×365 무중단 서비스

------------------------------------------------------------------------

## 실전 문제 (30문항)

1.  프로젝트 초기 산출물로 가장 적절한 것은? ① AS-IS 분석 및 요구사항
    정의 ② Failover 수행 ③ 운영 종료 ④ 백업 삭제 정답:①

2.  TO-BE 아키텍처의 핵심 목적은? ① 목표 시스템 정의 ② 백업 수행 ③
    테스트 종료 ④ 로그 삭제 정답:①

3.  GitOps에서 선언된 상태를 자동 반영하는 도구는? ① Argo CD ② Jenkins ③
    Nexus ④ Maven 정답:①

4.  상태 저장 DB는? ① StatefulSet ② Deployment ③ Job ④ DaemonSet 정답:①

5.  외부 L7 진입은? ① Ingress ② ConfigMap ③ Secret ④ PVC 정답:①

6.  Pod 자동 확장은? ① HPA ② ReplicaSet ③ kubelet ④ CoreDNS 정답:①

7.  Node 자동 확장은? ① Cluster Autoscaler ② HPA ③ Helm ④ etcd 정답:①

8.  이미지 취약점 분석? ① Trivy ② Grafana ③ Prometheus ④ SonarQube
    정답:①

9.  오픈소스 취약점 분석? ① SCA ② IDS ③ IPS ④ DHCP 정답:①

10. 공급망 보안 핵심? ① SBOM ② FTP ③ RAID ④ NAT 정답:①

11. RAG 효과는? ① 최신 문서 기반 응답 ② GPU 절감 ③ 압축 ④ 백업 정답:①

12. Embedding은? ① 벡터화 ② 암호화 ③ 로그 ④ 복제 정답:①

13. Vector DB는? ① 유사도 검색 ② DNS ③ RAID ④ FTP 정답:①

14. Prometheus는? ① Metrics 수집 ② Tracing ③ Build ④ ETL 정답:①

15. OpenTelemetry는? ① Distributed Tracing ② Backup ③ DNS ④ RAID 정답:①

16. Grafana는? ① Dashboard ② Compiler ③ DB ④ Firewall 정답:①

17. Error Budget 공식은? ① 100%-SLO ② EV/PV ③ EV/AC ④ BAC/CPI 정답:①

18. SPI=0.88 의미는? ① 일정 지연 ② 일정 양호 ③ 비용 초과 ④ 비용 절감
    정답:①

19. CPI=1.06 의미는? ① 비용 효율 양호 ② 일정 지연 ③ 품질 저하 ④ 장애
    정답:①

20. EAC 근사식은? ① BAC/CPI ② EV/PV ③ EV/AC ④ AC/PV 정답:①

21. Active-Active 목적은? ① 무중단 가용성 ② 백업 ③ 캐시 ④ 압축 정답:①

22. RTO 의미는? ① 목표 복구 시간 ② 허용 데이터 손실 ③ 응답 시간 ④ CPU
    사용률 정답:①

23. RPO 의미는? ① 허용 데이터 손실 시점 ② 복구 시간 ③ 장애 건수 ④ 처리량
    정답:①

24. Reserved Instance 장점은? ① 장기 비용 절감 ② 무조건 무중단 ③ 자동
    백업 ④ 암호화 정답:①

25. Spot Instance 특징은? ① 저렴하지만 회수 가능 ② 항상 유지 ③ 고정요금
    ④ DR 전용 정답:①

26. Tagging Strategy 목적은? ① 비용 추적 및 배분 ② 로그 삭제 ③ DB 복제 ④
    RAID 구성 정답:①

27. Zero Trust 원칙은? ① Never Trust, Always Verify ② 내부망 완전 신뢰 ③
    VPN만 사용 ④ 방화벽 제거 정답:①

28. RCA 목적은? ① 근본 원인 제거 및 재발 방지 ② 성능 테스트 ③ 배포
    자동화 ④ 백업 정답:①

29. EA 핵심은? ① Business-IT Alignment ② CPU 향상 ③ 서버 증설 ④ 회선
    증설 정답:①

30. 프로젝트 성공을 위한 최우선 요소는? ① 범위·일정·비용·품질의 균형 ②
    CPU 클럭 ③ SSD 용량 ④ NIC 속도 정답:①

------------------------------------------------------------------------

## 채점

-   28\~30 : 600점권
-   25\~27 : 550점권
-   22\~24 : 500점권
-   21 이하 : 약점 보완

## 핵심 암기

-   GitOps=Git
-   HPA=Pod
-   Cluster Autoscaler=Node
-   Trivy=이미지
-   SBOM=공급망
-   OTel=Tracing
-   SPI\<1=일정지연
-   CPI\>1=비용효율
-   RTO=시간
-   RPO=데이터

# Day90 예고

최종 종합 리허설 및 약점 진단
