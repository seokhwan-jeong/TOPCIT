# 📘 TOPCIT MasterBook 2026 (V4)

# Day 93 - 실전 Case Study ③ (클라우드 아키텍처 의사결정)

> 목표: **TOPCIT 550\~600점**

## 시나리오

한 공공기관이 노후 데이터센터를 클라우드 기반으로 전환한다.

### 요구사항

-   24x365 서비스
-   개인정보 보호
-   예산 20% 절감
-   Kubernetes 기반 MSA
-   DR 센터 구축
-   GitOps, DevSecOps 적용
-   AI(RAG) 민원 검색

당신은 인프라 PM으로 최적의 기술을 선택해야 한다.

------------------------------------------------------------------------

## 사례 분석 과제

1.  Active-Active와 Active-Standby 중 어떤 구성을 선택할지 이유와 함께
    설명하시오.
2.  VM 기반과 Kubernetes 기반의 장단점을 비교하시오.
3.  API Gateway와 Service Mesh를 각각 언제 사용하는지 설명하시오.
4.  비용 절감을 위한 FinOps 전략 3가지를 제시하시오.
5.  프로젝트의 주요 기술 리스크와 대응 방안을 작성하시오.

------------------------------------------------------------------------

# 연계 문제 (20문항)

1.  무중단 서비스에 가장 적합한 DR 방식은? ① Active-Active ② Cold Site ③
    Tape Backup ④ Manual Recovery 정답:①

2.  비용은 낮지만 서비스 중단 위험이 있는 인스턴스는? ① Spot Instance ②
    Reserved Instance ③ Dedicated Host ④ Bare Metal 정답:①

3.  장기 운영 비용 절감에 적합한 것은? ① Reserved Instance ② Spot
    Instance ③ Auto Scaling만 사용 ④ Scale Up 정답:①

4.  Kubernetes의 가장 큰 장점은? ① 자동 확장과 오케스트레이션 ② 운영체제
    대체 ③ DB 저장 ④ 백업 정답:①

5.  GitOps의 장점은? ① 변경 이력과 자동 배포 ② 수동 운영 증가 ③ 로그
    삭제 ④ 성능 저하 정답:①

6.  API Gateway 주요 기능은? ① 인증·라우팅 ② Pod 생성 ③ 이미지 스캔 ④ DB
    복제 정답:①

7.  Service Mesh 주요 기능은? ① 서비스 간 통신 제어 및 mTLS ② DNS 관리 ③
    VM 생성 ④ RAID 정답:①

8.  Zero Trust 핵심 원칙은? ① Never Trust, Always Verify ② 내부망은 항상
    신뢰 ③ VPN만 사용 ④ 방화벽 제거 정답:①

9.  Trivy는? ① 컨테이너 이미지 취약점 검사 ② Dashboard ③ Tracing ④ Build
    정답:①

10. SCA는? ① 오픈소스 취약점 분석 ② DB 튜닝 ③ 백업 ④ 모니터링 정답:①

11. SBOM은? ① 공급망 보안 ② 암호화 ③ RAID ④ VLAN 정답:①

12. Prometheus는? ① Metrics 수집 ② 로그 삭제 ③ DNS ④ ETL 정답:①

13. Grafana는? ① Dashboard ② Build ③ Compiler ④ VPN 정답:①

14. OpenTelemetry는? ① Distributed Tracing ② Backup ③ FTP ④ DHCP 정답:①

15. Error Budget은? ① 100%-SLO ② EV/PV ③ EV/AC ④ BAC/CPI 정답:①

16. CPI\<1 의미는? ① 비용 초과 ② 일정 앞섬 ③ 장애 없음 ④ 품질 향상
    정답:①

17. SPI\>1 의미는? ① 일정이 계획보다 앞섬 ② 일정 지연 ③ 비용 초과 ④
    리스크 증가 정답:①

18. Data Lineage 목적은? ① 데이터 흐름 추적 ② CPU 향상 ③ 로그 삭제 ④
    백업 정답:①

19. EA의 핵심 목표는? ① Business-IT Alignment ② 서버 증설 ③ 회선 증설 ④
    메모리 증설 정답:①

20. 프로젝트 성공을 위한 PM의 핵심 역할은? ① 범위·일정·비용·품질 균형
    관리 ② 서버 직접 운영 ③ DB 개발 ④ 코딩 정답:①

------------------------------------------------------------------------

## TOPCIT 고득점 팁

-   기술의 **장단점과 선택 이유**를 설명할 수 있어야 한다.
-   비용, 성능, 가용성, 보안의 **트레이드오프**를 함께 고려한다.
-   PM 관점에서 위험과 일정까지 연결해 판단한다.

# Day 94 예고

-   AI·RAG 성능 최적화
-   FinOps 심화
-   실제 금융권 프로젝트 사례
