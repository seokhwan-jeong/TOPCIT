# Day08 - 라우팅

**키워드:** Static Routing, Dynamic Routing, RIP, OSPF, BGP, Default Route

## 핵심 이론
- 라우팅은 목적지 네트워크까지의 경로를 결정하는 기능이다.
- Static Routing은 관리자가 직접 경로를 설정한다.
- OSPF는 내부망 동적 라우팅, BGP는 대규모 외부 라우팅에 많이 사용된다.

## TOPCIT 복원형(유사) 문제
1. Default Route 표기는?
   - 정답: 0.0.0.0/0
2. Static Routing 장점은?
   - 정답: 단순하고 예측 가능
3. OSPF는 어떤 용도인가?
   - 정답: IGP, 내부 동적 라우팅
4. BGP는 어디에 쓰이는가?
   - 정답: AS 간 라우팅
5. Traceroute 목적은?
   - 정답: 경로 확인

## 실무 응용 문제
1. DR센터와 주센터 간 경로 설계 시 확인할 것은?
   - 모범답안: 대역폭, 지연, 이중화, 보안 정책
2. 라우팅 장애 증상은?
   - 모범답안: 특정 대역만 접속 불가