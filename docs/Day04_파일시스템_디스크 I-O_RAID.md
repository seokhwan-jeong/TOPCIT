# Day04 - 파일시스템 · 디스크 I/O · RAID

**키워드:** NTFS, ext4, XFS, IOPS, Throughput, Latency, RAID 0/1/5/10

## 핵심 이론
- 파일시스템은 데이터를 파일과 디렉터리 구조로 저장/조회하게 해주는 구조다.
- 디스크 I/O 주요 지표는 IOPS, Throughput, Latency다.
- RAID는 성능, 안정성, 용량 효율을 목적에 따라 조합하는 디스크 구성 방식이다.

## TOPCIT 복원형(유사) 문제
1. SSD의 장점은?
   - 정답: 랜덤 I/O 성능
2. RAID1 특징은?
   - 정답: Mirroring
3. RAID5 특징은?
   - 정답: Parity
4. RAID10 장점은?
   - 정답: 성능과 안정성
5. Latency 의미는?
   - 정답: 응답 지연 시간

## 실무 응용 문제
1. CPU가 낮은데 서비스가 느리면 무엇을 확인?
   - 모범답안: Disk I/O, Latency, Queue, DB Lock
2. RAID0을 운영 DB에 권장하지 않는 이유는?
   - 모범답안: 장애 복구 불가