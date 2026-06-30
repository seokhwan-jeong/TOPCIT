# Day02 - 운영체제 · 스케줄링 · 동기화 · Deadlock

**키워드:** FCFS, SJF, RR, Mutex, Semaphore, Monitor, Deadlock 4조건

## 핵심 이론
- 스케줄링은 CPU를 어떤 프로세스에 배정할지 결정하는 정책이다.
- 동기화는 공유 자원 접근 시 Race Condition을 방지하기 위한 기법이다.
- Deadlock은 상호배제, 점유대기, 비선점, 순환대기 조건이 동시에 만족될 때 발생한다.

## TOPCIT 복원형(유사) 문제
1. FCFS의 대표 단점은?
   - 정답: Convoy Effect
2. Round Robin의 핵심 변수는?
   - 정답: Time Quantum
3. Mutex의 목적은?
   - 정답: 상호배제
4. Semaphore는 무엇을 제어하는가?
   - 정답: 동시 접근 가능한 자원 개수
5. Deadlock 조건이 아닌 것은?
   - 정답: Virtual Memory

## 실무 응용 문제
1. WAS Thread Pool 고갈 시 현상은?
   - 모범답안: 응답 지연 또는 Timeout
2. DB Deadlock 확인 항목은?
   - 모범답안: Lock 대기 세션, 장기 트랜잭션, Deadlock 로그