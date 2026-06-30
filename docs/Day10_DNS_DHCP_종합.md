# Day10 - DNS · DHCP · 종합

**키워드:** DNS, DHCP, DORA, Name Resolution, TTL, Gateway

## 핵심 이론
- DNS는 도메인 이름을 IP 주소로 변환한다.
- DHCP는 클라이언트에게 IP, Gateway, DNS 정보를 자동 할당한다.
- DHCP DORA는 Discover, Offer, Request, Ack 흐름이다.

## TOPCIT 복원형(유사) 문제
1. DNS 역할은?
   - 정답: 이름 -> IP 변환
2. DHCP DORA의 D는?
   - 정답: Discover
3. TTL 의미는?
   - 정답: 캐시 유지 시간
4. nslookup 용도는?
   - 정답: DNS 조회 확인
5. DHCP가 제공하는 정보는?
   - 정답: IP, Subnet Mask, Gateway, DNS

## 실무 응용 문제
1. DNS 장애 시 증상은?
   - 모범답안: IP 직접 접속은 되지만 도메인 접속 실패
2. DHCP 장애 시 증상은?
   - 모범답안: IP 자동 할당 실패