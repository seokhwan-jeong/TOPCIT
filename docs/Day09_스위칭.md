# Day09 - 스위칭

**키워드:** MAC Address, VLAN, Trunk, Access Port, STP, L2 Loop

## 핵심 이론
- Switch는 MAC Address Table을 기반으로 Frame을 전달한다.
- VLAN은 하나의 물리 스위치에서 논리적으로 네트워크를 분리하는 기술이다.
- STP는 L2 Loop를 방지하기 위한 프로토콜이다.

## TOPCIT 복원형(유사) 문제
1. Switch가 보는 주소는?
   - 정답: MAC Address
2. VLAN 목적은?
   - 정답: 논리적 네트워크 분리
3. Trunk Port는?
   - 정답: 여러 VLAN 태그 전달
4. Access Port는?
   - 정답: 하나의 VLAN 소속
5. STP 목적은?
   - 정답: Loop 방지

## 실무 응용 문제
1. VLAN 불일치 시 증상은?
   - 모범답안: 통신 불가
2. L2 Loop 발생 시 영향은?
   - 모범답안: Broadcast Storm 및 네트워크 장애