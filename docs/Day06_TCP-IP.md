# Day06 - TCP/IP

**키워드:** TCP/IP 4계층, TCP, UDP, 3-Way Handshake, Port

## 핵심 이론
- TCP/IP는 실제 인터넷에서 사용하는 통신 모델이다.
- TCP는 연결지향, 신뢰성, 순서 보장을 제공하고 UDP는 빠른 전송과 낮은 지연에 적합하다.
- TCP 연결은 SYN -> SYN+ACK -> ACK 순서로 수립된다.

## TOPCIT 복원형(유사) 문제
1. TCP 연결 첫 단계는?
   - 정답: SYN
2. UDP 특징은?
   - 정답: 비연결, 빠름
3. HTTP 기본 포트는?
   - 정답: 80
4. HTTPS 기본 포트는?
   - 정답: 443
5. DNS 기본 포트는?
   - 정답: 53

## 실무 응용 문제
1. SYN_SENT가 지속되면?
   - 모범답안: 서버/방화벽/네트워크 차단 의심
2. TCP Retransmission 증가 원인은?
   - 모범답안: 패킷 손실 또는 네트워크 혼잡