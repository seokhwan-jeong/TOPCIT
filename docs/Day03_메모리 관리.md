# Day03 - 메모리 관리

**키워드:** Paging, Segmentation, Virtual Memory, Page Fault, Thrashing, LRU

## 핵심 이론
- Paging은 프로세스를 Page, 메모리를 Frame으로 나누는 방식이다.
- Segmentation은 코드, 데이터, 스택 같은 논리 단위로 메모리를 나누는 방식이다.
- Thrashing은 Page Fault가 과도해져 CPU보다 디스크 I/O에 시간을 쓰는 상태다.

## TOPCIT 복원형(유사) 문제
1. Paging의 장점은?
   - 정답: 외부 단편화 감소
2. Segmentation의 특징은?
   - 정답: 논리 단위 분할
3. Page Fault란?
   - 정답: 필요 페이지가 메모리에 없는 상황
4. LRU 교체 기준은?
   - 정답: 가장 오래 사용되지 않은 페이지
5. Thrashing 원인은?
   - 정답: 과도한 Page Fault

## 실무 응용 문제
1. Swap 사용이 많으면 무엇을 의심하는가?
   - 모범답안: 메모리 부족 및 성능 저하
2. Kubernetes OOMKilled 의미는?
   - 모범답안: 컨테이너 메모리 Limit 초과로 종료