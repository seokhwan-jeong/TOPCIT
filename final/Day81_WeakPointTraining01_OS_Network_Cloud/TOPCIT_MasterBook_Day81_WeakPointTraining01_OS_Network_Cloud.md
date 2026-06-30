# 📘 TOPCIT MasterBook 2026 (V3)

# Day 81 - 약점 보완 집중훈련① (운영체제 · 네트워크 · 클라우드)

> 목표: TOPCIT 500점 이상

## 학습 전략

이번 Day81은 모의고사보다 **약점 보완**에 집중한다.

### 빈출 개념

-   프로세스 vs 스레드
-   교착상태 4조건
-   TCP 3-way / 4-way
-   CIDR, NAT, VLAN
-   Docker vs VM
-   Kubernetes Deployment / Service / Ingress
-   GitOps
-   Auto Scaling

------------------------------------------------------------------------

# 핵심 요약

## 운영체제

-   Process: 독립 메모리
-   Thread: 메모리 공유
-   Deadlock 조건: 상호배제, 점유대기, 비선점, 순환대기

## 네트워크

-   L3=IP
-   L4=TCP/UDP
-   TCP=신뢰성
-   UDP=속도

## 클라우드

-   Scale Up: 성능 증가
-   Scale Out: 서버 증가
-   Multi-AZ: 가용성
-   Multi-Region: DR

------------------------------------------------------------------------

# 실전 문제 (20문항)

1.  프로세스보다 스레드 생성 비용이 낮은 이유는? ① 메모리 공유 ② CPU
    증가 ③ RAID ④ NAT 정답:①

2.  Deadlock 조건이 아닌 것은? ① 상호배제 ② 순환대기 ③ 선점 가능 ④
    점유대기 정답:③

3.  TCP가 사용하는 계층은? ① L2 ② L3 ③ L4 ④ L7 정답:③

4.  UDP 특징은? ① 연결지향 ② 신뢰성 ③ 빠른 전송 ④ 순서보장 정답:③

5.  CIDR의 목적은? ① IP 효율 사용 ② 암호화 ③ RAID ④ ETL 정답:①

6.  NAT의 역할은? ① 사설/공인 IP 변환 ② 암호화 ③ 라우팅 제거 ④ 로그 저장
    정답:①

7.  VLAN 목적은? ① 브로드캐스트 분리 ② CPU 증가 ③ 백업 ④ DR 정답:①

8.  Docker는? ① 컨테이너 플랫폼 ② DB ③ 스위치 ④ IDS 정답:①

9.  Kubernetes Service 역할은? ① Pod 노출 ② 이미지 생성 ③ 컴파일 ④ 백업
    정답:①

10. Ingress 역할은? ① HTTP/HTTPS 진입 ② 스토리지 ③ DNS 서버 ④ VPN 정답:①

11. GitOps 핵심은? ① Git 기반 운영 ② DB 운영 ③ FTP ④ RAID 정답:①

12. Argo CD는? ① Git 동기화 ② 모니터링 ③ 컴파일 ④ 백업 정답:①

13. Scale Out은? ① 서버 추가 ② CPU 교체 ③ 메모리 제거 ④ 로그 삭제 정답:①

14. Multi-AZ 목적은? ① 고가용성 ② 장거리 DR ③ 백업 ④ 테스트 정답:①

15. Multi-Region 목적은? ① 재해복구 ② 캐시 ③ RAID ④ NAT 정답:①

16. CrashLoopBackOff 시 먼저 확인? ① kubectl logs ② reboot ③ format ④
    DNS 정답:①

17. Prometheus는? ① Metrics 수집 ② 이미지 스캔 ③ ETL ④ DNS 정답:①

18. Grafana는? ① 시각화 ② 컴파일 ③ VPN ④ Backup 정답:①

19. SPI\<1 의미? ① 일정 지연 ② 비용 절감 ③ 품질 향상 ④ 일정 단축 정답:①

20. CPI\>1 의미? ① 비용 효율 양호 ② 일정 지연 ③ 장애 ④ 데이터 손실
    정답:①

------------------------------------------------------------------------

# 오답노트

-   틀린 문제:
-   원인:
-   복습 계획:

# 암기노트

-   Thread=공유
-   TCP=L4
-   NAT=주소변환
-   Service=노출
-   Ingress=HTTP
-   GitOps=Git
-   Multi-Region=DR
-   SPI\<1 일정지연
-   CPI\>1 비용양호

# Day82 예고

-   데이터베이스·AI·DevSecOps 약점 보완
