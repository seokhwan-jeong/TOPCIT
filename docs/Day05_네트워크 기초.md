# Day05 - 네트워크 기초

**키워드:** OSI 7계층, Ethernet, ARP, Switch, Router, ICMP

## 핵심 이론
- OSI는 네트워크 기능을 계층별로 나눈 모델이며 장애 분석 기준으로 유용하다.
- Switch는 L2에서 MAC 기반으로 전달하고 Router는 L3에서 IP 기반으로 경로를 결정한다.
- ARP는 같은 네트워크에서 IP 주소를 MAC 주소로 변환한다.

## TOPCIT 복원형(유사) 문제
1. L3 프로토콜은?
   - 정답: IP
2. MAC 주소는 몇 계층인가?
   - 정답: L2
3. ARP 역할은?
   - 정답: IP -> MAC 변환
4. Ping에 주로 쓰이는 프로토콜은?
   - 정답: ICMP
5. Router의 핵심 역할은?
   - 정답: Routing

## 실무 응용 문제
1. Ping은 되는데 웹 접속이 안 될 때 확인할 것은?
   - 모범답안: DNS, 방화벽, HTTP 서비스 상태
2. Switch Loop 방지 기술은?
   - 모범답안: STP