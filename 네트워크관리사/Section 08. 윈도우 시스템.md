# History of Window System

```ad-note
title: Dirty Operating System (DOS)

옛날옛적에, Seattle Computer Products라는 회사의 엔지니어인 Paterson씨는 **16bit Intel 8086**을 테스트 할 **QDOS (Quick and Dirty Operating System)**을 만들었다. 

빠르게 개발하기 위해 Paterson씨는 당시의 CP/M이라는 운영체제의 API를 복붙해서 개발했다. 그리고 86-DOS 라는 이름으로 판매되었다.  

[정보 출처](https://www.businessinsider.com/history-of-dos-2011-7#the-story-of-dos-begins-with-tim-paterson-1)

참고로 CP/M이라는 운영체제는 Gary Kildall 교수님이 1974년에 만든 디스크 기반 운영체제이다. 

[정보 출처](https://landley.net/history/mirror/cpm/history.html)

시간이 흘러서 어느날, IBM에서 Intel 8088칩을 돌릴 수 있는 컴퓨터 운영체제를 개발하기 위해 Bill Gates에게 연락했다. Bill Gates는 새로운 운영체제를 만들어주겠다고 하고, Paterson씨의 86-DOS를 구입했다. 1981년에 MS-DOS (Microsoft Disk Operating System)으로 출시되었다. 

아니 그러면 CP/M은 어떻게 되었냐고?

나중에 CP/M 개발사에서 DOS가 자신들의 운영체제와 비슷한것을 알게되어 IBM을 고소했다. 그리고 IBM은 CP/M과 협상을 해서 사용자들이 컴퓨터를 구매할 때 DOS 또는 CP/M을 설치할지 고를 수 있도록 하기로 했다. 어찌보면 공급계약을 맺어 CP/M도 이득이었다고 볼 수 있지만, IBM은 CP/M 설치시 200달러를 추가로 내도록해서 CP/M의 시장 지분을 잡아먹었다. 

1994년, GUI가 나오면서 Microsoft에서 MS-DOS의 배포 및 지원 중단을 선언했다. 

[정보 출처](https://www.businessinsider.com/history-of-dos-2011-7#the-story-of-dos-begins-with-tim-paterson-1)

```

# Windows System

```ad-note
title: Windows NT Server 3.1

1980년대에 Microsoft랑 IBM이랑 같이 협업해서 OS/2 라는 운영체제를 개발했다. 그러다 1988년에 Microsoft에서 NT (New Technology)라고 자체적으로 운영체제 개발을 시작했다. 시행착오 끝에 1993년 7월 27일에 Windows NT Server 3.1이 출시되었다. 

Windows NT Server 3.1에 대해 소개하자면, 

1. 32bit 시스템 
2. 프로세서 독립성 (다양한 프로세서에서도 운영체제가 호환이 되었다)
3. 선점형 멀티태스킹 (운영체제가 프로그램들의 CPU를 직접 관리했다)
4. 다중 처리 (여러 프로세서를 동시에 사용할 수 있다)


[자료 출처 - Microsoft 공식 블로그](http://antares.cs.kent.edu/~mikhail/classes/os.s03/l24windowsXP.PDF)
[자료 출처 - Tech Community](https://techcommunity.microsoft.com/blog/sbs/30-years-of-windows-server/3884810)
```


## Hardware Abstract Layer (HAL)

![[Pasted image 20250213204331.png]]
[이미지 출처](http://antares.cs.kent.edu/~mikhail/classes/os.s03/l24windowsXP.PDF)

```ad-note
title: HAL (Hardware Abstract Layer)

지금까지의 역사를 보면 항상 하드웨어(프로세서)에 맞춰서 운영체제를 개발했는데, 처음으로 다른 프로세서에도 돌아가는 운영체제가 나왔다. 이게 어떻게 가능했을까? 

Windows NT를 개발할 때 처음부터 Microsoft는 다양한 하드웨어에서 실행 가능한 운영체제를 목표했다. 이때 처음으로 HAL (Hardware Abstract Layer)가 등장한다. 하드웨어에 의존적인 코드는 따로 분리해서 관리 할 수 있는 계층을 만들었다. 하드웨어 관련된 명령어는 HAL만 통해서 동작했기에, 다른 하드웨어로 변경하면 운영체제에서 HAL 코드만 수정하면 되었다.  

처음에는 Intel i860 프로세서를 위해서 Windows NT가 개발 되었는데, 나중에는 Intel x86, MIPS(R4000/R4400)등 다양한 프로세서들이 지원되도록 확장되었다고한다. 

[자료 출처 - Microsoft 공식 블로그](https://techcommunity.microsoft.com/blog/sbs/30-years-of-windows-server/3884810)

[자료 출처 - OS2 museum](https://www.os2museum.com/wp/nt-3-1-smp/comment-page-1/)
```




```ad-claude
1. HAL (Hardware Abstraction Layer):

- 하드웨어와 운영체제 사이의 인터페이스 역할
- 다양한 하드웨어에서 동일한 방식으로 운영체제가 동작할 수 있도록 하는 추상화 계층
- 프로세서, 버스, 인터럽트 컨트롤러 등의 하드웨어 차이를 숨김

2. Micro Kernel:

- 운영체제의 핵심 기능만을 담당하는 최소한의 커널
- 기본적인 프로세스 관리, 메모리 관리, 프로세스간 통신 등을 처리
- 다른 기능들은 사용자 모드에서 실행되는 서버 프로세스로 분리

1. I/O Manager:

- 입출력 작업을 관리하고 조정
- 파일 시스템, 네트워크, 장치 드라이버와의 통신을 담당
- 통일된 I/O 요청 방식을 제공

2. Object Manager:

- 시스템의 모든 리소스를 객체로 관리
- 파일, 프로세스, 스레드, 세마포어 등을 객체로 추상화
- 객체의 생성, 삭제, 접근 권한 등을 관리

3. Security Reference Monitor:

- 시스템의 보안 정책을 실행
- 접근 권한 검사와 감사를 수행
- 객체에 대한 보안 검사를 담당

4. Process Manager:

- 프로세스와 스레드의 생성, 종료, 스케줄링을 관리
- 프로세스간 동기화를 처리
- CPU 시간 할당과 우선순위 관리

5. Local Procedure Call (LPC):

- 같은 시스템 내의 프로세스간 통신을 위한 메커니즘
- 클라이언트-서버 모델의 통신을 지원
- 고성능의 프로세스간 통신을 제공

6. Virtual Memory Manager:

- 물리적 메모리와 가상 메모리를 관리
- 페이징과 스와핑을 처리
- 메모리 보호와 공유를 관리

7. Win32/64 Subsystem:

- Windows 애플리케이션을 위한 실행 환경 제공
- Win32/64 API 구현
- 애플리케이션과 운영체제 사이의 인터페이스 역할

8. Security Subsystem:

- 사용자 인증과 권한 부여를 관리
- 보안 정책 설정과 적용
- 로그온 세션과 보안 토큰 관리
```

# Windows File System 

```ad-claude

1. FAT16 (File Allocation Table 16)
- 개발: 1984년 Microsoft가 개발
- 배경: IBM PC DOS 3.0을 위해 개발됨
- 작동원리:
  - 파일 위치를 16비트 클러스터 번호로 추적
  - 디스크를 고정 크기의 클러스터로 나누어 관리
  - FAT 테이블에 각 클러스터의 사용 상태를 기록
- 특징:
  - 최대 파티션 크기: 2GB
  - 최대 파일 크기: 2GB
  - 단순한 구조로 구현이 쉬움
  - 파일 단편화 문제 발생
  - 보안 기능 없음

2. FAT32 (File Allocation Table 32)
- 개발: 1996년 Microsoft가 개발
- 배경: FAT16의 용량 제한을 극복하기 위해 개발
- 작동원리:
  - 32비트 클러스터 번호 사용
  - FAT16과 기본 구조는 동일하나 더 큰 주소 공간 제공
- 특징:
  - 최대 파티션 크기: 2TB
  - 최대 파일 크기: 4GB
  - FAT16보다 공간 효율성 개선
  - Windows 98/ME의 기본 파일 시스템
  - 여전히 보안 기능 미흡
  - USB 드라이브 등에서 널리 사용

1. NTFS (New Technology File System)
- 개발: 1993년 Microsoft가 개발
- 배경: Windows NT를 위한 고급 파일 시스템으로 개발
- 작동원리:
  - 모든 데이터를 메타데이터 포함해 파일로 관리
  - Master File Table (MFT)로 파일 정보 관리
  - 저널링을 통한 장애 복구 지원
  - B-tree 구조로 파일 검색 최적화
- 특징:
  - 이론상 최대 용량: 16EB(엑사바이트)
  - 파일 단위 암호화 지원
  - 파일/폴더 권한 설정 가능
  - 디스크 쿼터 지원
  - 파일 압축 기능
  - 저널링으로 시스템 충돌 시 복구 가능
  - 보안 기능 강화
  - 현재 Windows의 기본 파일 시스템

각 파일 시스템의 주요 발전 포인트:
- FAT16 → FAT32: 용량 제한 극복
- FAT32 → NTFS: 보안, 안정성, 효율성 대폭 강화

현재는 상황에 따라 다르게 사용됩니다:
- NTFS: 주 운영체제 드라이브
- FAT32: 외장 저장장치, 크로스 플랫폼 호환성 필요시
- exFAT: 대용량 외장 저장장치 (FAT32의 4GB 제한 극복)
```

# Windows User 

```ad-claude
Windows의 사용자 계정 유형과 내장 계정들에 대해 설명해드리겠습니다:

# 사용자 계정 유형

1. Built-in User Account (내장 사용자 계정)
- Windows 설치시 기본으로 생성되는 계정
- Administrator와 Guest가 대표적
- 시스템 관리와 기본적인 접근을 위해 사용
- 보안을 위해 필요한 경우가 아니면 비활성화 권장

2. Local User Account (로컬 사용자 계정)
- 단일 컴퓨터에서만 사용 가능한 계정
- 해당 컴퓨터의 리소스와 파일에만 접근 가능
- 각 컴퓨터마다 독립적으로 관리
- 개인용 PC에서 주로 사용

1. Domain User Account (도메인 사용자 계정)
- Active Directory 도메인에서 관리되는 계정
- 도메인 내의 모든 컴퓨터에서 사용 가능
- 중앙집중식 관리 가능
- 기업 환경에서 주로 사용
- 네트워크 리소스 접근 권한 통합 관리

# 서버 내장형 계정

2. Administrators
- 시스템의 모든 권한을 가진 관리자 그룹
- 시스템 설정 변경, 사용자 관리 등 수행
- 보안상 일상적인 작업에는 사용하지 않는 것이 좋음

3. Guest
- 제한된 권한을 가진 임시 사용자용 계정
- 기본적으로 비활성화되어 있음
- 보안상 활성화하지 않는 것을 권장

4. IUSR_XXX
- IIS(Internet Information Services)의 익명 사용자 계정
- 웹 서버에 익명으로 접근하는 사용자를 위한 계정
- XXX는 컴퓨터 이름을 나타냄
- 웹 사이트 접근 권한 관리에 사용

5. IWAM_XXX
- IIS 웹 애플리케이션 및 서비스 실행용 계정
- 웹 애플리케이션의 격리된 실행 환경 제공
- XXX는 컴퓨터 이름을 나타냄
- 웹 애플리케이션의 보안 경계 설정에 사용

보안 관련 중요 사항:
- 내장 관리자 계정은 이름을 변경하거나 비활성화하는 것이 좋음
- Guest 계정은 기본적으로 비활성화 상태를 유지
- 서비스 계정들은 필요한 최소한의 권한만 부여
- 정기적인 암호 변경과 감사 로깅 설정 필요
- 계정 잠금 정책 설정 권장

모든 계정은 "최소 권한의 원칙"에 따라 관리하는 것이 보안상 중요합니다.
```

# Windows 그룹 관리 

```ad-claude
Windows의 기본 그룹들에 대해 설명해드리겠습니다:

1. Administrators (관리자)
- 시스템에 대한 모든 권한 보유
- 시스템 설정 변경, 소프트웨어 설치, 사용자 계정 관리 가능
- 모든 파일과 리소스에 대한 접근 권한 보유
- 보안상 일상적인 작업에는 일반 계정 사용 권장

2. Backup Operators (백업 운영자)
- 백업과 복원 작업을 위한 특별 권한 보유
- 모든 파일에 대한 읽기 권한 보유
- 백업 목적으로 파일 접근시 보안 제한 우회 가능
- 파일 시스템 백업과 복원 작업 수행 가능

1. Power Users (파워 유저)
- 일반 사용자보다 높은 권한을 가진 그룹
- 제한된 관리 작업 수행 가능
- 로컬 응용 프로그램 설치와 관리 가능
- Windows 최신 버전에서는 보안상 사용 권장하지 않음

2. Users (사용자)
- 일반적인 작업 수행을 위한 표준 권한 보유
- 응용 프로그램 실행과 개인 파일 관리 가능
- 시스템 설정 변경이나 소프트웨어 설치 제한
- 대부분의 일상적인 작업에 권장되는 그룹

3. Guests (게스트)
- 매우 제한된 권한만 가진 임시 사용자용 그룹
- 시스템과 파일에 대한 최소한의 접근만 허용
- 임시 사용자나 익명 접근용으로 사용
- 보안상 기본적으로 비활성화 권장

4. Everyone (모든 사용자)
- 시스템의 모든 사용자를 포함하는 그룹
- 모든 인증된 사용자와 게스트 포함
- 공용 리소스에 대한 접근 권한 설정에 사용
- 보안상 주의가 필요한 그룹

그룹 관리 시 주요 고려사항:
- 보안을 위해 "최소 권한의 원칙" 적용
- 필요한 최소한의 권한만 부여
- 정기적인 그룹 멤버십 검토
- 중요한 리소스에 대한 Everyone 그룹 접근 제한
- 관리자 그룹 멤버 최소화
```

# NTFS File System

```ad-claude
NTFS 파일 시스템의 주요 기능들을 설명해드리겠습니다:

1. USN (Update Sequence Number) Journal
- 파일 시스템의 변경 사항을 추적하는 로그
- 파일/디렉토리의 생성, 삭제, 수정 등을 기록
- 백업 소프트웨어나 검색 인덱싱에 활용
- 시스템 복구와 감사에 유용

2. Alternate Data Stream (ADS)
- 하나의 파일에 여러 데이터 스트림 저장 가능
- 주 데이터 외에 추가 정보 저장 가능
- 보안 위험이 될 수 있어 주의 필요
- 인터넷에서 다운로드한 파일의 출처 정보 저장 등에 사용

1. Sparse 파일
- 실제 데이터가 있는 부분만 디스크 공간 할당
- 대용량 파일의 효율적인 저장 가능
- 데이터베이스 파일 등에 유용
- 디스크 공간 절약 가능

2. 파일 압축
- 개별 파일이나 폴더 단위로 압축 가능
- 실시간 압축/해제 지원
- 디스크 공간 절약
- CPU 자원 사용 증가

3. VSS (Volume Shadow Copy Service)
- 파일 시스템의 특정 시점 스냅샷 생성
- 백업과 복원에 활용
- 이전 버전 파일 복구 가능
- 시스템 복원점 생성에 사용

4. EFS (Encrypting File System)
- 파일 단위 암호화 지원
- 사용자 인증서 기반 암호화
- 중요 데이터 보호
- 키 복구 기능 제공

5. Quotas (할당량)
- 사용자별 디스크 사용량 제한 가능
- 디스크 공간 관리
- 사용량 모니터링
- 경고 임계값 설정 가능

6. Unicode 지원
- 다국어 파일명 지원
- 255자까지 파일명 지원
- 다양한 언어의 문자 처리
- 국제화 지원

7. 동적 Bad 클러스터 할당
- 손상된 디스크 섹터 자동 감지
- Bad 클러스터 자동 관리
- 데이터 손실 방지
- 디스크 신뢰성 향상

8. 대용량 지원
- 최대 볼륨 크기: 16 엑사바이트
- 최대 파일 크기: 16 엑사바이트
- 대용량 저장장치 지원
- 효율적인 대용량 파일 처리

이런 기능들의 주요 장점:
- 데이터 보안 강화
- 저장 공간 효율성 향상
- 시스템 안정성 개선
- 관리 기능 강화
- 데이터 복구 용이

이러한 기능들은 NTFS를 기업 환경에서 선호하는 파일 시스템으로 만드는 주요 요인이 되었습니다.
```

