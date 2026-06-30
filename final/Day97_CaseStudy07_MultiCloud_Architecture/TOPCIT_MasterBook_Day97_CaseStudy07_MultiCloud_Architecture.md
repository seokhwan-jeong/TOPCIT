# 📘 TOPCIT MasterBook 2026 (V4)

# Day 97 - 실전 Case Study ⑦ (멀티클라우드 아키텍처와 장애 대응)

> 목표: **TOPCIT 550\~600점**

## 프로젝트 시나리오

한 금융기업은 AWS, Azure, Private Cloud를 함께 사용하는 멀티클라우드
환경을 운영한다.

### 요구사항

-   핵심 업무는 Private Cloud
-   AI 서비스는 Public Cloud GPU 사용
-   DR은 타 CSP로 이중화
-   GitOps 기반 배포
-   서비스 무중단
-   비용 최적화(FinOps)
-   Zero Trust 적용

------------------------------------------------------------------------

## 사례 분석 과제

1.  멀티클라우드를 선택한 이유를 설명하시오.
2.  장애 발생 시 Failover 절차를 작성하시오.
3.  CSP 장애에 대비한 아키텍처를 제안하시오.
4.  FinOps 비용 절감 방안 3가지를 제시하시오.
5.  운영 KPI(SLI/SLO) 3가지를 정의하시오.

------------------------------------------------------------------------

# 연계 문제 (20문항)

1.  멀티클라우드의 가장 큰 장점은? ① CSP 종속성 감소 ② 운영 단순화만
    가능 ③ 보안 제거 ④ DR 불필요 정답:①

2.  GitOps의 Source of Truth는? ① Git Repository ② NAS ③ DB ④ DNS 정답:①

3.  Argo CD 역할은? ① Git과 클러스터 동기화 ② 빌드만 수행 ③ DB 관리 ④
    백업 정답:①

4.  Active-Active 목적은? ① 서비스 연속성 ② 백업 전용 ③ 테스트 전용 ④
    비용 증가 정답:①

5.  Active-Standby 장점은? ① 구현 단순성 ② 무조건 성능 우수 ③ DR 불필요
    ④ 비용 0원 정답:①

6.  HPA는? ① Pod 자동 확장 ② Node 자동 확장 ③ DB 확장 ④ VPC 생성 정답:①

7.  Cluster Autoscaler는? ① Node 자동 확장 ② Pod 자동 확장 ③ 로그 저장 ④
    ETL 정답:①

8.  Service Mesh의 기능은? ① mTLS와 트래픽 제어 ② DNS 관리 ③ VM 생성 ④
    RAID 정답:①

9.  API Gateway의 역할은? ① 인증·라우팅 ② 이미지 스캔 ③ 모니터링 ④
    컴파일 정답:①

10. Trivy는? ① 이미지 취약점 검사 ② Dashboard ③ Tracing ④ Backup 정답:①

11. SCA는? ① 오픈소스 취약점 분석 ② DB 성능 튜닝 ③ 암호화 ④ RAID 정답:①

12. SBOM은? ① 공급망 보안 ② VLAN ③ FTP ④ DHCP 정답:①

13. Prometheus는? ① Metrics 수집 ② DNS ③ Build ④ Storage 정답:①

14. Grafana는? ① Dashboard ② Firewall ③ VPN ④ Compiler 정답:①

15. OpenTelemetry는? ① Distributed Tracing ② RAID ③ NAT ④ Snapshot
    정답:①

16. Reserved Instance는? ① 장기 비용 절감 ② 단기 테스트 ③ DR 전용 ④ 백업
    정답:①

17. Spot Instance는? ① 저렴하지만 회수 가능 ② 항상 보장 ③ 고정요금 ④
    무중단 정답:①

18. Zero Trust 핵심은? ① Never Trust, Always Verify ② 내부 신뢰 ③ VPN만
    사용 ④ 암호화 불필요 정답:①

19. RCA의 목적은? ① 근본 원인 제거와 재발 방지 ② 로그 삭제 ③ 장비 교체만
    수행 ④ 테스트 종료 정답:①

20. 멀티클라우드 PM의 핵심 역할은? ① 비용·성능·가용성 균형 관리 ② 직접
    코딩 ③ DB 개발 ④ 서버 조립 정답:①

------------------------------------------------------------------------

## 실무 체크리스트

-   CSP 장애 대응 절차
-   Failover 테스트
-   비용 모니터링
-   GitOps 롤백 검증
-   보안 정책 일관성
-   운영 KPI 검토

# Day 98 예고

-   최종 Case Study
-   통합 아키텍처 설계
-   최고난도 TOPCIT 사례형
