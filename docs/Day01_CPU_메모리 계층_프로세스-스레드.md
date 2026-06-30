# Day01 - CPU · 메모리 계층 · 프로세스/스레드

**키워드:** CPU, ALU/CU, Register, Cache, Process, Thread, Context Switching

## 핵심 이론
- CPU는 명령어를 해석하고 실행하는 중앙처리장치이며 ALU, CU, Register, Cache로 구성된다.
- 메모리 계층은 Register -> Cache -> RAM -> SSD/HDD 순으로 속도는 느려지고 용량은 커진다.
- 프로세스는 독립 메모리를 사용하고, 스레드는 프로세스 내부 메모리를 공유한다.

## TOPCIT 복원형(유사) 문제
1. CPU Cache의 목적은?
   - 정답: 메모리 접근시간 감소
2. 프로세스와 스레드의 가장 큰 차이는?
   - 정답: 메모리 공유 여부
3. Context Switching이 잦으면?
   - 정답: 오버헤드 증가와 성능 저하
4. Virtual Memory가 필요한 이유는?
   - 정답: 물리 메모리 부족 보완
5. 멀티스레드에서 주의할 점은?
   - 정답: 동기화

## 실무 응용 문제
1. Kubernetes 노드 CPU 99%일 때 함께 확인할 항목은?
   - 모범답안: Memory, Swap, Disk I/O, Network, Thread Pool, Pod Restart/OOMKilled
2. CPU 증설 전에 확인할 사항은?
   - 모범답안: 실제 병목이 CPU인지, I/O나 Lock인지 확인